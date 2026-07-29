---
title: 'PCR bias '
date: 2015-12-27T21:56:00.003-08:00
draft: false
url: /2015/12/pcr-bias.html
---

> **Archived note — originally created: 2015-12-27 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


# # # Abstract

Despite the ever-increasing output of Illumina sequencing data, loci with extreme base compositions are often under-represented or absent. To evaluate sources of base-composition bias, we traced genomic sequences ranging from 6% to 90% GC through the process by quantitative PCR. We identified PCR during library preparation as a principal source of bias and optimized the conditions. Our improved protocol significantly reduces amplification bias and minimizes the previously severe effects of PCR instrument and temperature ramp rate.

# # # Background

The Illumina sequencing platform [](https://www.blogger.com/null)\[[1](http://genomebiology.com/2011/12/2/R18#B1)\], like other massively parallel sequencing platforms [](https://www.blogger.com/null)[](https://www.blogger.com/null)\[[2](http://genomebiology.com/2011/12/2/R18#B2),[3](http://genomebiology.com/2011/12/2/R18#B3)\], continues to produce ever-increasing amounts of data, yet suffers from under-representation and reduced quality at loci with extreme base compositions that are recalcitrant to the technology[](https://www.blogger.com/null)[](https://www.blogger.com/null)[](https://www.blogger.com/null)[](https://www.blogger.com/null)\[[1](http://genomebiology.com/2011/12/2/R18#B1),[4](http://genomebiology.com/2011/12/2/R18#B4)\-[6](http://genomebiology.com/2011/12/2/R18#B6)\]. Uneven coverage due to base composition necessitates sequencing to excessively high mean coverage for _de novo _genome assembly [](https://www.blogger.com/null)\[[7](http://genomebiology.com/2011/12/2/R18#B7)\] and for sensitive polymorphism discovery [](https://www.blogger.com/null)[](https://www.blogger.com/null)\[[8](http://genomebiology.com/2011/12/2/R18#B8),[9](http://genomebiology.com/2011/12/2/R18#B9)\]. Although loci with extreme base composition constitute only a small fraction of the human genome, they include biologically and medically relevant re-sequencing targets. For example, 104 of the first 136 coding bases of the retinoblastoma tumor suppressor gene _RB1 _are G or C.

```
Traditional Sanger sequencing has long been known to suffer from problems related to the base composition of sequencing templates. GC-rich stretches led to compression artifacts. Polymerase slippage in poly(A) runs and AT dinucleotide repeats caused mixed sequencing ladders and poor read quality. Processes upstream of the actual sequencing, such as cloning, introduced bias against inverted repeats, extreme base-compositions or genes not tolerated by the bacterial cloning host. Gaps due to unclonable sequences had to be recovered and finished by PCR [](https://www.blogger.com/null)\[[10](http://genomebiology.com/2011/12/2/R18#B10)\], or, in some cases, by resorting to alternative hosts [](https://www.blogger.com/null)\[[11](http://genomebiology.com/2011/12/2/R18#B11)\]. Cloning bias hindered efforts to sequence the AT-rich genomes of _Dictyostelium _[](https://www.blogger.com/null)\[[12](http://genomebiology.com/2011/12/2/R18#B12)\] and _Plasmodium _[](https://www.blogger.com/null)\[[13](http://genomebiology.com/2011/12/2/R18#B13)\] and excluded the GC-rich first exons of about 10% of protein-coding genes in the dog (K Lindblad-Toh, personal communication) from an otherwise high-quality reference genome assembly [](https://www.blogger.com/null)\[[14](http://genomebiology.com/2011/12/2/R18#B14)\].
```

```
New genome sequencing technologies [](https://www.blogger.com/null)[](https://www.blogger.com/null)[](https://www.blogger.com/null)[](https://www.blogger.com/null)[](https://www.blogger.com/null)[](https://www.blogger.com/null)\[[1](http://genomebiology.com/2011/12/2/R18#B1)\-[3](http://genomebiology.com/2011/12/2/R18#B3),[15](http://genomebiology.com/2011/12/2/R18#B15)\-[17](http://genomebiology.com/2011/12/2/R18#B17)\] no longer rely on cloning in a microbial host. Instead of ligating DNA fragments to cloning vectors, the three major platforms currently on the market (454, Illumina and SOLiD) involve ligation of DNA fragments to special adapters for clonal amplification _in vitro _rather than _in vivo_. Due to the massively parallel nature of the process, standardized reaction conditions must be applied to amplify and sequence complex libraries of fragments that comprise a wide spectrum of sequence compositions. All three platforms display systematic biases and unevenness as the observed coverage distributions are significantly wider than the Poisson distribution expected from unbiased, random sampling [](https://www.blogger.com/null)\[[18](http://genomebiology.com/2011/12/2/R18#B18)\].
```

```
The Illumina sequencing process consists of i) library preparation on the lab bench, ii) cluster amplification, sequencing-by-synthesis and image analysis on proprietary instruments, followed by iii) post-sequencing data processing. Bias can be introduced at all three stages. For example, high cluster densities on the Illumina flowcell suppress GC-rich reads. Changes to sequencing kits, protocols and instrument firmware can affect the base composition of sequencing data. Moreover, bias is known to vary between laboratories, from run to run or even from lane to lane on the same flowcell. Such variability and instability in the system confound comparative studies [](https://www.blogger.com/null)[](https://www.blogger.com/null)\[[19](http://genomebiology.com/2011/12/2/R18#B19),[20](http://genomebiology.com/2011/12/2/R18#B20)\] and render systematic bias investigations difficult.
```

http://genomebiology.com/2011/12/2/R18

#color-code #TroubleshootNotes #BloggerPublishedNonAcademicNotes
