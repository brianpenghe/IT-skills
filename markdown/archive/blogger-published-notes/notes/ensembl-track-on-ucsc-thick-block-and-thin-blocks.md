---
title: 'Ensembl Track on UCSC thick block and thin blocks'
date: 2017-04-18T19:46:00.001-07:00
draft: false
url: /2017/04/ensembl-track-on-ucsc-thick-block-and.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


**Question: ** 
"What is the significance of the thinner blocks displayed at the beginning and end of a gene in the browser?"

**Response:** 
The varying thickness of features in the Genome Browser gene tracks denotes the various structural features of a gene, such as exons, introns, and untranslated regions (UTRs). The thickest parts of the track indicate the coding exon regions within the gene. The slightly thinner portions at the leading and trailing ends of the gene track show the 5' and 3' UTRs. Introns are depicted as lines with arrows indicating the direction of transcription.

Some aspects of the graphical representation are inevitably lost upon rescaling. For example, coding exons are given preference at coarse scales. For single exon genes, there is no place to put the strand orientation wedges, and therefore the feature's detail page must be consulted.

For more information about annotation track display conventions within the Genome Browser, consult the [User's Guide](https://genome.ucsc.edu/goldenPath/help/hgTracksHelp.html).

#UCSC-Genome-Browser #TroubleshootNotes #BloggerPublishedNonAcademicNotes
