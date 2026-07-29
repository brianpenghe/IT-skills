---
title: '.fastq files and adaptors'
date: 2017-04-18T19:49:00.001-07:00
draft: false
url: /2017/04/fastq-files-and-adaptors.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


# # # http://onetipperday.blogspot.com/2012/08/three-ways-to-trim-adaptorprimer.html#uds-search-results

# # # 

# # # Three ways to trim adaptor/primer sequences for paired-end reads

# # # **1\. Understanding the adaptors** (skip this part if you're familiar with the Illumina adaptor)

Before trimming anything from the reads, let's get clear what the reads content is. 

Taking Trufseq reads (from Illumina HiSeq 2000) as example, here is the read file (fastq) looks like: 

**$ cat r1.fq ** 
@3VFXHS1:278:D13Y4ACXX:1:1101:1472:2209 1:N:0:**CGATGT** 
CTGGTATTGTCTCTTCCCACACTGAACTCTGGGGAATT**CGATGT**GTGGCACAGCCCGGCTCAGCCTGCCCGCTGGTGGGAGCCCCTGGGAAGCTGCGGCGC 
+ 
@@CFDDFFGH>CAEH:CGHIJJJJEIHJJHIJJJ?DHIDIJHGEGHJG;FHC9@B(5@6A=EH:B@B@2=>>B?BDCBD<B52<<ABD?<?B1@A9>B### 
@3VFXHS1:278:D13Y4ACXX:1:1101:1434:2224 1:N:0:CGATGT 
GGCAGAGCCAATCTTCGGACGTGGTGATTGTCTCCTCTAAGTACAAACAGCGCTATGAGTGTCGCCTGCCAGCTGGAGCTATTCACTTCCAGCGTGAAAGG 
+ 
BC@FFFFFHHHGFHIIJJIJGFHICFCGIHGFHFGGCHD@F?B?BGGHJJIG6D@EHEHHEHCD259?AACD@AC59?,(5>A,;>:@C(::(029?8>@A 
@3VFXHS1:278:D13Y4ACXX:1:1101:1712:2247 1:N:0:CGATGT 
GTACACTTGAACACATTTTTCTAACCTTAGAAAATACCTACAAGGCCTGTTGTCTTGACCCATTACTCAATTGTCCCTGGCATATTATCTGATCTTCACGT 
+ 
CCCFFFFFHHHHGJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJIJGIIJGGGDHHHIHIHHEIJIJJIIGGIIIIFEHHHHFEFFFDEEEDCEEEDEDC?A 
@3VFXHS1:278:D13Y4ACXX:1:1101:3318:2215 1:N:0:**CGATGT** 
AGATCGGAAGAGCACACGTCTGAACTCCAGTCAC**CGATGT**ATCTCGTATGCCGTCTTCTGCTTGAAAAAAAAAAGAAAAAAAAACAAGCGACAAGGACAGA 
+ 
CCCFFFFFHHHHHJJJJJIJJJJJJJJJIJGHFFHIAHIFGGIIJJIJJFIJIHJIHHHGEGFE>CFFEB############################### 
@3VFXHS1:278:D13Y4ACXX:2:1101:5344:2243 1:N:0:**ACAGTG** 
GATCGGAAGAGCACACGTCTGAACTCCAGTCAC**ACAGTG**ATCTCGTATGCCGTCTTCTGCTTGAAAAAAAAACAACAGAAAAAACAAAGCGCGAACAGTGC 
+ 
CCCFFFFFHHHHHJIJJIJIJHJJJJJJJHIGIGIHJFHFFDIIJGIIIJJJHHFIJJJJJJHCEHHFD################################ 

**$ cat r2.fq ** 
@3VFXHS1:278:D13Y4ACXX:1:1101:1472:2209 2:N:0:CGATGT 
CTGGATTTGAAATCTTTAGCGGAGCGGGAACGCCGGCGCGGAAGGGTCTCTACACAGGGCCCGGTCCGCCCTTGCGCTCTCCTTAATGNNNNNNNNNNCGC 
+ 
@CCF?EFFHHHGHHHIFGI@HGGIEHIGIJGI6@@E>B8>??:DBD++399>ACCDDDD@DBDD58@BBDDDDD@@<@BDDDDC>CDC############# 
@3VFXHS1:278:D13Y4ACXX:1:1101:1434:2224 2:N:0:CGATGT 
CCCGGGGCCTCCCATTAAGGTCGCACTTGGACCCATTGCCATAGGTCTGGCTGTGGTAGCGTTTAAGACGATGCTGCTTGGAGGCCTTGGCTGTTTCATCA 
+ 
BCCFFFFDHFFHGIHIHGJJIJJGGIIJJJIDHGJIJEIIIIIJJIIJIJHHHEEF;>DDA>BBB@CAABBBDDCDDDDDDAD@@?CDDDCCB?ACCDDC# 
@3VFXHS1:278:D13Y4ACXX:1:1101:1712:2247 2:N:0:CGATGT 
GTTACTCAGCATTTATTCATGCCTGCTGTGTACGGAAAGGGCAGTTACAAAGGAAAGCCTTGATGATTCTGCTTCCAAGAAACGTGAAGATCAGATAATAT 
+ 
CBCFFFFFHHHHHJIJJIIJJJJJIIJIHIHIJJJIJIJIJJIIIIIIJJGGIIJJJIJJJJHIJJJJHIJHGHHHHFFFFFEDECBDDDDDCCDDDCDEE 
@3VFXHS1:278:D13Y4ACXX:1:1101:3318:2215 2:N:0:CGATGT 
AGATCGGAAGAGCGTCGTGTAGGGAAAGAGTGTAGATCTCGGTGGTCGCCGTATCATTAAAAAAAAAAAAAAAACAGAAAAAGAAAGAAGGAAAGGNGAGT 
+ 
CCCFFFFFHHHHHJJJJFHHHJJJIJJGGIDGHIEIJJJIIJGIJ5@FHIB?DFFEEEDEEEDD?#################################### 
@3VFXHS1:278:D13Y4ACXX:2:1101:5344:2243 2:N:0:ACAGTG 
GGATCGGGAAAGGGGGGGGGGGGGGAAAAGGGGGGATTTCCGGGGGGGCCGGTTCTTTTAAAAAAAAAAAAAAAGAAAACAGAAACAGAAGATGGACAACA 
+ 
CCCFFFFFHHHHHJJJJFHHHJJJIJJGGIDGHIEIJJJIIJGIJ5@FHIB?DFFEEEDEEEDD?#################################### 

First of first, it's critical to understand what your reads file contain; do they contain adaptor sequences? do they contain primer sequence? I strongly recommend to read the description file here: http://genomics.med.tufts.edu/documents/protocols/TUCF\_Understanding\_Illumina\_TruSeq\_Adapters.pdf, from which we could know that the constructed dsDNA (before binding to the flow cell for sequencing) looks like: 

[![](https://1.bp.blogspot.com/-eDCkz2A8OGQ/UBiQqnsRx3I/AAAAAAAAAWI/jhwIDlK7eQ0/s640/Screen+shot+2012-07-31+at+10.12.29+PM.png)](http://1.bp.blogspot.com/-eDCkz2A8OGQ/UBiQqnsRx3I/AAAAAAAAAWI/jhwIDlK7eQ0/s1600/Screen+shot+2012-07-31+at+10.12.29+PM.png)

Where 

**Trufseq Universal Adaptor: 
5´AATGATACGGCGACCACCGAGATCTACACTCTTTCCCTACACGACGCTCTTCCGATCT3´**

\--> reverse complementary

5´AGATCGGAAGAGCGTCGTGTAGGGAAAGAGTGTAGATCTCGGTGGTCGCCGTATCATT3´ 

TruSeq Indexed Adapter: 
5´GATCGGAAGAGCACACGTCTGAACTCCAGTCAC‐NNNNNN‐ATCTCGTATGCCGTCTTCTGCTTG3´

The 6-nt "**NNNNNN**" is barcode for multiplexing. We noticed that the 3´ of Universal adaptor is reverse-complementary to the 5´ of Indexed adaptor (Why? This is to form the Y-shape adaptor. See ZZ's dUTP figure in another post). 

Combining together the "Overrepresented sequences" of FASTQC output file ([for example](http://zlab.umassmed.edu/~dongx/tracks/RNAseq/BU/Sample_3576_H_01.R1_fastqc/fastqc_report.html#M9)), we could infer that the reads are contaminated by adaptor/primers (for example the red-marked part in the fastq sequences). 

So, next step is how to remove the contamination. 

# # # **2\. Collect adaptor sequences**

To remove contamination, we first should collect all possible "contamination" sources. For our case, we collect all used barcode sequences and generated the adaptor file: 

http://zlab.umassmed.edu/~dongx/tracks/RNAseq/BU/Demultiplex\_Stats.htm

copy content and save to txt file Demultiplex\_Stats.htm

grep -v Undetermined barcode\_stat.html | awk '{print ">"$2; print "GATCGGAAGAGCACACGTCTGAACTCCAGTCAC"$4"ATCTCGTATGCCGTCTTCTGCTTG";}' > adaptor.fa

The Demultiplex\_Stats.htm file, which contains barcode information of each sample, is usually included in the output folder of sequencing. Otherwise, you can consult from the data producer. 

You may also want to append the universal adaptor:

$cat >> adaptor.fa

\>Trufseq\_Universal\_Adaptor

AATGATACGGCGACCACCGAGATCTACACTCTTTCCCTACACGACGCTCTTCCGATCT

(Ctrl+D)

A full list of commonly-used adaptors can be retrieved from the following URL (returned by Google search) by command:

curl -s http://www.omicsoft.com/downloads/ngs/contamination\_list/v1.txt 2>&1 | sed "/^\\s\\+$/d;s/\\t\\+/\\t/g;s/ /\_/g;s/,//g;s/'//g" | awk '{print ">"$1; print $2;}' > adaptors\_list.fa 

This does not include Trufseq barcodes used for smallRNA (see below), which you have to include yourself:

http://epigenome.usc.edu/docs/resources/core\_protocols/TruSeq%20index%20sequences-3.pdf

# # # **3\. Remove adaptor **

There might be many ways to remove adaptors, but specifically for PE reads (e.g. both reads are removed if one of the pairs is disqualified), I'd like to introduce three ways to do this.

**a. FastqMcf ([http://code.google.com/p/ea-utils/wiki/FastqMcf](http://code.google.com/p/ea-utils/wiki/FastqMcf))**

usage: fastq-mcf \[options\] <adapters.fa> <reads.fq> \[mates1.fq ...\] 

Options:

    -h      This help

    -o FIL  Output file (stats to stdout)

    -s N.N  Log scale for clip pct to threshold (2.2)

    -t N    % occurrence threshold before clipping (0.25)

    -m N    Minimum clip length, overrides scaled auto (1)

    -p N    Maximum adapter difference percentage (10)

    -l N    Minimum remaining sequence length (19)

    -L N    Maximum sequence length (none)

    -k N    sKew percentage-less-than causing trim (2)

    -q N    quality threshold causing trimming (10)

    -w N    window-size for quality trimming (1)

    -f      force output, even if not much will be done

    -F FIL  remove sequences that align to FIL

    -0      Set all trimming parameters to zero

    -U|u    Force disable/enable illumina PF filtering

    -P N    phred-scale (auto)

    -x N    'N' (Bad read) percentage causing trimming (20)

    -R      Don't remove N's from the fronts/ends of reads

    -n      Don't clip, just output what would be done

    -C N    Number of reads to use for subsampling (200k)

    -S FIL  Save clipped reads to file

    -d      Output lots of random debugging stuff

For example, 

fastq-mcf -o c1.fq -o c2.fq -l 16 -q 15 -w 4 -x 10 -u -P 33 adaptor.fa r1.fq r2.fq &>r.log

**b. Trimmomatic ([http://www.usadellab.org/cms/index.php?page=trimmomatic](http://www.usadellab.org/cms/index.php?page=trimmomatic))**

Paired End Mode: 
java -classpath <path to trimmomatic jar> org.usadellab.trimmomatic.TrimmomaticPE \[-threads <threads>\] \[-phred33 | -phred64\] \[-trimlog <logFile>\] <input 1> <input 2> <paired output 1> <unpaired output 1> <paired output 2> <unpaired output 2> <step 1> ... 

Step options: 

* ILLUMINACLIP:<fastaWithAdaptersEtc>:<seed mismatches>:<palindrome clip threshold>:<simple clip threshold>

* fastaWithAdaptersEtc: specifies the path to a fasta file containing all the adapters, PCR sequences etc. The naming of the various sequences within this file determines how they are used. See below.
* seedMismatches: specifies the maximum mismatch count which will still allow a full match to be performed
* palindromeClipThreshold: specifies how accurate the match between the two 'adapter ligated' reads must be for PE palindrome read alignment.
* simpleClipThreshold: specifies how accurate the match between any adapter etc. sequence must be against a read.

* SLIDINGWINDOW:<windowSize>:<requiredQuality>

* windowSize: specifies the number of bases to average across
* requiredQuality: specifies the average quality required.

* LEADING:<quality>

* quality: Specifies the minimum quality required to keep a base.

* TRAILING:<quality>

* quality: Specifies the minimum quality required to keep a base.

* CROP:<length>

* length: The number of bases to keep, from the start of the read.

* HEADCROP:<length>

* length: The number of bases to remove from the start of the read.

* MINLENGTH:<length>

* length: Specifies the minimum length of reads to be kept.

Following the above example:

java -classpath $CLASSPATH/trimmomatic-0.22.jar org.usadellab.trimmomatic.TrimmomaticPE -phred33 -trimlog r.log r1.fq r2.fq t1.fq t1.unpaired.fq t2.fq t2.unpaired.fq LEADING:3 TRAILING:3 ILLUMINACLIP:adaptor.fa:2:40:15 SLIDINGWINDOW:4:15 MINLEN:16 

These two programs give same results:

@3VFXHS1:278:D13Y4ACXX:1:1101:1472:2209 1:N:0:CGATGT

CTGGTATTGTCTCTTCCCACACTGAACTCTGGGGAATTCGATGTGTGGCACAGCCCGGCTCAGCCTGCCCGCTGGTGGGAGCCCCTGGGAAGCTGCGG

+

@@CFDDFFGH>CAEH:CGHIJJJJEIHJJHIJJJ?DHIDIJHGEGHJG;FHC9@B(5@6A=EH:B@B@2=>>B?BDCBD<B52<<ABD?<?B1@A9>B

@3VFXHS1:278:D13Y4ACXX:1:1101:1434:2224 1:N:0:CGATGT

GGCAGAGCCAATCTTCGGACGTGGTGATTGTCTCCTCTAAGTACAAACAGCGCTATGAGTGTCGCCTGCCAGCTGGAGCTATTCACTTCCAGCGTGAAAGG

+

BC@FFFFFHHHGFHIIJJIJGFHICFCGIHGFHFGGCHD@F?B?BGGHJJIG6D@EHEHHEHCD259?AACD@AC59?,(5>A,;>:@C(::(029?8>@A

@3VFXHS1:278:D13Y4ACXX:1:1101:1712:2247 1:N:0:CGATGT

GTACACTTGAACACATTTTTCTAACCTTAGAAAATACCTACAAGGCCTGTTGTCTTGACCCATTACTCAATTGTCCCTGGCATATTATCTGATCTTCACGT

+

CCCFFFFFHHHHGJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJIJGIIJGGGDHHHIHIHHEIJIJJIIGGIIIIFEHHHHFEFFFDEEEDCEEEDEDC?A

c. **HTSeq** 
([http://www-huber.embl.de/users/anders/HTSeq/doc/sequences.html#HTSeq.SequenceWithQualities.trim\_left\_end\_with\_quals](http://www-huber.embl.de/users/anders/HTSeq/doc/sequences.html#HTSeq.SequenceWithQualities.trim_left_end_with_quals))

Cite what Simon posted [here](http://seqanswers.com/forums/showthread.php?t=12171), HTSeq has facilities useful for this. 

You can write a little Python script like this: 

> import itertools 
> import HTSeq 
> in1 = iter( HTSeq.FastqReader( "mydata\_1.fastq" ) ) 
> in2 = iter( HTSeq.FastqReader( "mydata\_2.fastq" ) ) 
> out1 = open( "trimmed\_1.fastq", "w" ) 
> out2 = open( "trimmed\_2.fastq", "w" ) 
> for read1, read2 in itertools.izip( in1, in2 ): 
>    read1.trim\_right\_end( "ACGGTC" ) 
>    read2.trim\_left\_end( "TTCGAC" ) 
>    read1.write\_to\_fastq\_file( out1 ) 
>    read2.write\_to\_fastq\_file( out2 ) 
> out1.close() 
> out2.close()

I've not figured out how to apply a fasta file of adaptor.

#FastQC #Trimmomatic #HTSeq #FastqMcf #Python #RNA-seq #demultiplexing #TroubleshootNotes #BloggerPublishedNonAcademicNotes
