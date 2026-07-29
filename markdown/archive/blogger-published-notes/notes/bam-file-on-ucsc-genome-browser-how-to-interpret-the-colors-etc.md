---
title: 'Bam file on UCSC genome browser: How to interpret the colors etc'
date: 2017-04-18T19:52:00.001-07:00
draft: false
url: /2017/04/bam-file-on-ucsc-genome-browser-how-to.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


http://genome.ucsc.edu/goldenpath/help/hgBamTrackHelp.html 

alignments on the reverse strand are colored dark red, alignments on the forward strand are colored dark blue. 

For the full explanation: 

**Configuring BAM tracks**

Genome Browser BAM tracks may be configured in a variety of ways to highlight different aspects of the displayed information. The configuration options are described here and related to custom track settings that can alter the default appearance of the custom track. Click [here](http://genome.ucsc.edu/goldenpath/help/bam.html) for more information on BAM custom track creation.

* **Attempt to join paired end reads by name**: This checkbox appears only if pairEndsByName is included in the track settings. When checked, SAM/BAM records with the same name will be joined into pairs for display, with a line drawn between them.
* **Minimum alignment quality**: Exclude alignments with quality less than the given number. The default is 0, unless changed by the track setting minAliQual.
* **Color track by bases**: By default, mismatching bases are highlighted in the display. Change the selection to "item bases" to see all base values from the query sequence, or "OFF" to ignore query sequence.
* **Additional coloring modes**: Other aspects of the alignments can be displayed in color or grayscale. The default mode is 'Color by strand' (bamColorMode=strand), unless the bamColorMode track setting specifies gray, tag or off.
 * **Color by strand**: alignments on the reverse strand are colored dark red, alignments on the forward strand are colored dark blue.
 * **Grayscale**: items are shaded according to the chosen method: alignment quality, base qualities, or unpaired ends. Items' alignment qualities are shaded on a scale of 0 (lightest) to 99 (darkest). Base qualities are shaded on a scale of 0 (lightest) to 40 (darkest). When "unpaired ends" is selected, items that were paired in sequencing but whose mate was not mapped are colored gray, while singletons and properly paired items are black. Alignment quality is the default (bamGrayMode=aliQual) unless bamGrayMode track setting is baseQual or unpaired.
 * **Use R,G,B colors specified in user-defined tag**: SAM/BAM may include user-defined tags, whose names begin with X, Y or Z and include one other letter or number. The user-defined tag named here specifies red, green and blue (RGB) intensities as a zero-terminated string (tag type Z) containing comma-separated triples of numbers from 0-255. For example, if a SAM/BAM record includes the tag YC:Z:255,0,0, then the item is colored red;YC:Z:0,0,255 makes the item blue. By default, the tag is "YC" unless changed using the track setting bamColorTag.
 * **No additional coloring**

When you have finished making your configuration changes, click the _Submit_ button to return to the annotation track display page.

#UCSC-Genome-Browser #TroubleshootNotes #BloggerPublishedNonAcademicNotes
