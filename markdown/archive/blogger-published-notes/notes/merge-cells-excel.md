---
title: 'Merge cells---Excel'
date: 2017-04-18T19:28:00.002-07:00
draft: false
url: /2017/04/merge-cells-excel.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


**IMPORTANT **  Only the data in the upper-left cell of a [range](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx) of selected cells will remain in the merged cell. Data in other cells of the selected range will be deleted.

1. If the data that you want to display in the merged cell is not in the upper-left cell, do the following:

1. Select the data that you want to display in the merged cell, and then click **Copy** ![Button image](https://officeimg.vo.msecnd.net/en-us/files/523/831/ZA006044679.gif) on the **Standard**toolbar.
2. Select the upper-left cell of the range of adjacent cells that you want to merge, and then click **Paste** ![Button image](https://officeimg.vo.msecnd.net/en-us/files/622/726/ZA006044682.gif) on the **Standard** toolbar.

3. Select the cells that you want to merge.

** NOTE **  The cells that you select must be adjacent.

1. On the **Formatting** [toolbar](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx), click **Merge and Center** ![Button image](https://officeimg.vo.msecnd.net/en-us/files/222/962/ZA006045006.gif).

The cells will be merged in a row or column, and the cell contents will be centered in the merged cell.

** NOTE **  If the **Merge and Center ![Button image](https://officeimg.vo.msecnd.net/en-us/files/222/962/ZA006045006.gif)** button is unavailable, the selected cell may be in editing mode. To cancel editing mode, press ENTER.

1. To change the text alignment in the merged cell, select the cell, and then click **Align Left** ![Button image](https://officeimg.vo.msecnd.net/en-us/files/169/107/ZA006044736.gif) or **Align Right** ![Button image](https://officeimg.vo.msecnd.net/en-us/files/189/197/ZA006044737.gif) on the **Formatting** toolbar.

[![Top of Page](https://officeimg.vo.msecnd.net/en-us/files/206/661/ZA010077668.gif)](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx#top) [TOP OF PAGE](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx#top)

[](https://www.blogger.com/null)Split merged cells
--------------------------------------------------

You can split only cells that were previously merged.

1. Select the merged cell.

When you select a merged cell, the **Merge and Center** button ![Button image](https://officeimg.vo.msecnd.net/en-us/files/222/962/ZA006045006.gif) also appears [selected](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx) on the **Formatting**toolbar.

1. To unmerge cells, click **Merge and Center** ![Button image](https://officeimg.vo.msecnd.net/en-us/files/222/962/ZA006045006.gif).

** NOTE **  When the merged cell is split, the contents of the merged cell will appear in the upper-left cell of the range of split cells.

[![Top of Page](https://officeimg.vo.msecnd.net/en-us/files/206/661/ZA010077668.gif)](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx#top) [TOP OF PAGE](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx#top)

[](https://www.blogger.com/null)Merge the contents of multiple cells into one cell
----------------------------------------------------------------------------------

You can use a formula with the ampersand (&) operator to combine text from multiple cells into one cell.

1. Select the cell in which you want to combine the contents of other cells.
2. To start the formula, type **\=(**
3. Select the first cell that contains the text that you want to combine, type **&" "&** (with a space between the quotation marks), and then select the next cell that contains the text that you want to combine.

To combine the contents of more than two cells, continue selecting cells, making sure to type **&" "&** between selections. If you don't want to add a space between combined text, type **&** instead of **&" "&**. To insert a comma, type **&", "&** (with a comma followed by a space between the quotation marks).

1. To finalize the formula, type **)**
2. To see the results of the formula, press ENTER.

**Tip**    You can also use the [CONCATENATE](http://office.microsoft.com/en-us/excel-help/redir/HP005209020.aspx?CTT=5&origin=HP005251021) function to combine text from multiple cells into one cell.

# # # Example

The following example worksheet shows the available formulas that you can use. The example may be easier to understand if you copy it to a blank worksheet.

[![Show](https://officeimg.vo.msecnd.net/en-us/files/785/945/ZA079005000.gif)Copy the example to a blank worksheet](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx)

**1**

**2**

**3**

**A**

**B**

**First Name**

**Last Name**

Nancy

Davolio

Andrew

Fuller

**Formula**

**Description (Result)**

\=A2&" "&B2

Combines the names above, separated by a space (Nancy Davolio)

\=B3&", "&A3

Combines the names above, separated by a comma (Fuller, Andrew)

\=CONCATENATE(A2," ",B2)

Combines the names above, separated by a space (Nancy Davolio)

** NOTE **  The formula inserts a space between the first and last names by using a space enclosed within quotation marks. Use quotation marks to include any literal text — text that does not change — in the result.

[![Top of Page](https://officeimg.vo.msecnd.net/en-us/files/206/661/ZA010077668.gif)](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx#top) [TOP OF PAGE](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx#top)

[](https://www.blogger.com/null)Split the contents of cells across multiple cells
---------------------------------------------------------------------------------

You cannot split a cell or [range](http://office.microsoft.com/en-us/excel-help/merge-and-unmerge-cells-HP005251021.aspx) of cells that was not previously merged. You can, however, divide the contents of unmerged cells and display them across other cells.

1. Select the cell, the range of cells, or the entire column that contains the text values that you want to divide across other cells. A range can be any number of rows tall, but no more than one column wide.

** IMPORTANT **  Unless there are one or more blank columns to the right of the selected column, the data to the right of the selected column will be overwritten.

1. On the **Data** menu, click **Text to Columns**.
2. Follow the instructions in the Convert Text to Columns Wizard to specify how you want to divide the text into columns.

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
