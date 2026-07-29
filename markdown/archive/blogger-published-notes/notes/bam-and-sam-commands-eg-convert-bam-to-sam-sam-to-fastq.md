---
title: 'bam and sam commands e.g. Convert Bam to Sam, sam to fastq'
date: 2017-04-18T19:45:00.005-07:00
draft: false
url: /2017/04/bam-and-sam-commands-eg-convert-bam-to.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


```
convert bam to sam:  $ samtools view -h -o out.sam in.bam
``````
convert sam to bam:  $ samtools view -bT .faFILE samfile
``````
```
sort the bam:  $ samtools sort Example.bam Example.sorted
```
``````
view a specific region(must be properly indexed while indexing depends on sorting):
``````
$ samtools view Example.bam chr17:220-300
```

`Print the header of bam`

`samtools view -H in.bam` 

The end of sam file has the bowtie parameters used. 

sam to fastq 
```
cat samplename.nomapping.sam | grep -v ^@ | awk '{print "@"$1"\\n"$10"\\n+\\n"$11}' > unmapped/samplename.fastq
```

#Bowtie #SAMtools #TroubleshootNotes #BloggerPublishedNonAcademicNotes
