---
title: 'unzip, decompress, extract the files form gz tar zip'
date: 2017-04-18T15:49:00.005-07:00
draft: false
url: /2017/04/unzip-decompress-extract-files-form-gz.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


tar -xvf GSE108097\_RAW.tar 

Using gunzip command:

`$ gunzip -k file.gz 
$ ls file`

Using gzip -d command: 
`$ gzip -d file.gz 
$ ls file`

If file extension is tar.gz, type the command: 
`$ tar -zxvf file.tar.gz` 
Please note that gunzip can currently decompress files created by gzip, zip, compress, compress -H or pack programs.

# # # Compressing files

**Syntax**

**Description**

**Example(s)**

[](https://www.blogger.com/null)gzip {filename}

Gzip compress the size of the given files using Lempel-Ziv coding (LZ77). Whenever possible, each file is replaced by one with the extension .gz.

gzip mydata.doc 
gzip \*.jpg 
ls -l

[](https://www.blogger.com/null)bzip2 {filename}

bzip2 compresses files using the Burrows-Wheeler block sorting text compression algorithm, and Huffman coding. Compression is generally considerably better than that achieved by bzip command (LZ77/LZ78-based compressors). Whenever possible, each file is replaced by one with the extension .bz2.

bzip2 mydata.doc 
bzip2 \*.jpg 
ls -l

[](https://www.blogger.com/null)zip {.zip-filename} {filename-to-compress}

zip is a compression and file packaging utility for Unix/Linux. Each file is stored in single .zip {.zip-filename} file with the extension .zip.

zip mydata.zip mydata.doc 
zip data.zip \*.doc 
ls -l

[](https://www.blogger.com/null)tar -zcvf {.tgz-file} {files} 
tar -jcvf {.tbz2-file} {files}

The GNU tar is archiving utility but it can be use to compressing large file(s). GNU tar supports both archive compressing through gzip and bzip2. If you have more than 2 files then it is recommended to use tar instead of gzip or bzip2. 
**\-z**: use gzip compress 
**\-j**: use bzip2 compress

tar -zcvf data.tgz \*.doc 
tar -zcvf pics.tar.gz \*.jpg \*.png 
tar -jcvf data.tbz2 \*.doc 
ls -l

# # # Decompressing files

**Syntax**

**Description**

**Example(s)**

gzip -d {.gz file} 
gunzip {.gz file}

Decompressed a file that is created using[gzip](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#gzip) command. File is restored to their original form using this command.

gzip -d mydata.doc.gz 
gunzip mydata.doc.gz

bzip2 -d {.bz2-file} 
bunzip2 {.bz2-file}

Decompressed a file that is created using[bzip2](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#bzip2) command. File is restored to their original form using this command.

bzip2 -d mydata.doc.bz2 
gunzip mydata.doc.bz2

unzip {.zip file}

Extract compressed files in a [ZIP](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#zip) archive.

unzip file.zip 
unzip data.zip resume.doc

tar -zxvf {.tgz-file} 
tar -jxvf {.tbz2-file}

Untar or decompressed a file(s) that is created using [tar](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#tar) compressing through[gzip](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#gzip) and [bzip2](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#bzip2) filter

tar -zxvf data.tgz 
tar -zxvf pics.tar.gz \*.jpg 
tar -jxvf data.tbz2

# # # List the contents of an archive/compressed file

Some time you just wanted to look at files inside an archive or compressed file. Then all of the above command supports file list option.

**Syntax**

**Description**

**Example(s)**

gzip -l {.gz file}

List files from a [GZIP](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#gzip) archive

gzip -l mydata.doc.gz

unzip -l {.zip file}

List files from a [ZIP](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#zip) archive

unzip -l mydata.zip

tar -ztvf {.tar.gz} 
tar -jtvf {.tbz2}

List files from a [TAR](http://www.cyberciti.biz/howto/question/general/compress-file-unix-linux-cheat-sheet.php#tar) archive

tar -ztvf pics.tar.gz 
tar -jtvf data.tbz2

#Linux #TroubleshootNotes #BloggerPublishedNonAcademicNotes
