---
title: 'SAMTOOLS SAMFILE tags'
date: 2015-11-05T13:19:00.001-08:00
draft: false
url: /2015/11/samtools-samfile-tags.html
---

> **Archived note — originally created: 2015-11-05 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


[SAM format summary](http://blog.kokocinski.net/index.php/sam-format-summary?blog=2)
------------------------------------------------------------------------------------

The Sequence Alignment/Map (SAM) format is a generic alignment format for storing read alignments against reference sequences. It is a text format for storing sequence data in a series of tab delimited ASCII columns and is commonly used in next-generation sequencing data processing. It is the (non-binary) human-readable version of the BAM format and contains information about the read and the aligned position in the genome. It was developed by Heng Li in Richard Durbins group and others, their paper is [here](http://www.ncbi.nlm.nih.gov/pubmed/19505943).

After a header section the alignment section describes all results of the aligned read data. The format is best explained with an example line:

Code

`1:497:R:-272+13M17D24M  113  1  497  37  37M  15  100338662  0  CGGGTCTGACCTGAGGAGAACTGTGCTCCGCCTTCAG  0;==-==9;>>>>>=>>>>>>>>>>>=>>>>>>>>>>  XT:A:U  NM:i:0  SM:i:37  AM:i:0  X0:i:1  X1:i:0  XM:i:0  XO:i:0  XG:i:0  MD:Z:37`

```
Fieldname description Example-data 
QNAME read name 1:497:R:-272+13M17D24M 
FLAG alignment flag 113 
RNAME alignment chromosome 1 
POS alignment start position 497 
MAPQ overall mapping quality 37 
CIGAR alignment CIGAR string 37M 
MRNM/RNEXT name of next alignm. in group (mate) 15 
MPOS/PNEXT pos. of next alignm. in group (mate) 100338662 
ISIZE/TLEN observed Template LENgth 0 
SEQ sequence CGGGTCTGACCTGAGGAGAACTGTGCTCCGCCTTCAG 
QUAL quality per base 0;==-==9;>>>>>=>>>>>>>>>>>=>>>>>>>>>> 
TAGs further tags with alignment info 
XT:A:U NM:i:0 SM:i:37 AM:i:0 X0:i:1 X1:i:0 XM:i:0 XO:i:0 XG:i:0 MD:Z:37
```

The tags are optional and might vary between alignment programs. Shown are examples from BWA. Important for filtering are usually the tags X0:i (numbers of genome alignments of this read) and XM:i (number of mismatches in alignment).

```
 Tag Meaning 
 NM Edit distance 
 MD Mismatching positions/bases 
 AS Alignment score 
 BC Barcode sequence 
 X0 Number of best hits 
 X1 Number of suboptimal hits found by BWA 
 XN Number of ambiguous bases in the reference 
 XM Number of mismatches in the alignment 
 XO Number of gap opens 
 XG Number of gap extensions 
 XT Type: Unique/Repeat/N/Mate-sw 
 XA Alternative hits; format: (chr,pos,CIGAR,NM;)\* 
 XS Suboptimal alignment score 
 XF Support from forward/reverse alignment 
 XE Number of supporting seeds
```

The read name (at least from Illumina machines) are constructed as:

```
\[instrument-name\]:\[run ID\]:\[flowcell ID\]:\[lane-number\]:\[tile-number\]: 
\[x-pos\]:\[y-pos\] \[read number\]:\[is filtered\]:\[control number\]: 
\[barcode sequence\] 

```

example:

```
@M01117:25:000000000-A37B9:1:1101:14984:1386 1:N:0:4
```

Sources: 
[genome.sph.umich.ed](http://genome.sph.umich.edu/wiki/SAM) with further useful details, [full specs](http://samtools.sourceforge.net/SAM1.pdf).

![](http://www.gravatar.com/avatar/388e579ab5d4d607d749d77407ea0121?size=32&default=http%3A%2F%2Fblog.kokocinski.net%2Fmedia%2Fshared%2Fglobal%2Favatars%2Fdefault_avatar_unknown.jpg)

#XT-Type #SAMtools #BWA #NIH #TroubleshootNotes #BloggerPublishedNonAcademicNotes
