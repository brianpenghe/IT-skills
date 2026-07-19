# SKILL: 古籍 PDF OCR、校勘与 Searchable PDF 工作流（Cursor Agent + PaddleOCR + ChatGPT）

## 概述

本 Skill 总结了一套结合 Cursor Agent、PaddleOCR 与 ChatGPT
的古籍数字化流程。

## 一、角色分工

### Cursor Agent

-   自动安装 PaddleOCR（Python 3.12 venv、PaddlePaddle、PaddleOCR）
-   运行 OCR
-   输出每页 `*_res.json`
-   构建 searchable PDF
-   根据 OCR_PATCH.json 自动修补 OCR JSON
-   重新生成 searchable PDF
-   添加 PDF Bookmarks

### PaddleOCR

-   对扫描 PDF 做 OCR
-   推荐 `lang="chinese_cht"`
-   输出：
    -   `*_res.json`
    -   `*_ocr_res_img.png`
    -   合并全文 txt

### ChatGPT

-   OCR 人工校勘（20 页一批）
-   输出勘误 TXT
-   汇总 OCR_PATCH.json
-   设计 Bookmarks
-   全流程 QC

## 二、工作流程

1.  扫描 PDF
2.  Cursor Agent 安装并运行 PaddleOCR
3.  生成 `*_res.json`
4.  构建 searchable PDF（仅增加隐藏文字层，不修改扫描图像）
5.  ChatGPT 分批校勘（20 页/组）
6.  汇总为 `OCR_PATCH.json`
7.  Cursor 自动应用 Patch 至 `*_res.json`
8.  重新生成 searchable PDF
9.  添加章节 Bookmarks
10. 最终质量检查

## 三、OCR Patch 设计

推荐格式：

``` json
{
  "page_rules":[
    {"page":165,"find":"己已霹靂火","replace":"己丑霹靂火"}
  ],
  "global_rules":[
    {"find":"緝要","replace":"輯要"}
  ]
}
```

优先 page_rules，再执行 global_rules。 不要依赖 box_index。

## 四、校勘原则

-   仅修改高置信度 OCR 错误
-   不修改古籍异体字
-   不校卷心、书口、页码
-   不修改扫描图像
-   始终修改 OCR 文本层

## 五、Bookmarks

最后统一生成： - 地理大全輯要 - 地理大全入門要訣（卷一～卷七） -
點穴大全 - 鉛彈子 - 金彈子 - 玉彈子 - 陽宅大全（卷一～卷四）

## 六、Best Practices

-   保留原始 PDF
-   保留全部 `*_res.json`
-   Patch 与 OCR 解耦，可重复应用
-   图像不变，只更新隐藏文字层
-   保留所有中间文件，确保流程可重建

## 七、来源

本流程综合： - Cursor Agent 自动安装与运行 PaddleOCR 的实践，包括建立
Python 3.12 虚拟环境、运行 335 页 OCR、生成 searchable PDF 等。\
- ChatGPT 对 OCR 结果进行分批校勘、生成勘误、OCR Patch、Bookmarks 与
QC。参考 Cursor 安装与运行记录。
