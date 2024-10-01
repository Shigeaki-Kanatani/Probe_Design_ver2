# In situ HCR_Probe_Design_ver2

## Introduction
This program is version 2 of the probe design script used for the whole brain in situ hybridization method (Kanatani S et al., biorxiv, 2022). It has a more convenient probe design workflow than version 1.  

The overall workflow of the script is
1.	Obtain reference sequence from NCBI
2.	Perform BLAST and remove similar sequences
3.	Run the script here to have probe sequences

Here, we show the practical example of how to use this script below using a mouse Gad1 and Tph2 mRNA. (The example was done on 2024-May-30)

## Example 

### 1. Obtain reference sequence from NCBI

- Visit NCBI Gene page and search the reference sequences of your target mRNAs.  
   - https://www.ncbi.nlm.nih.gov/gene

- Download the FASTA sequences of your targets. The followings are the example of Gad1 and Tph2 from mouse (Mus musculus).

- Make a folder structure as below and save the FASTA sequence(.fasta).
   - Main folder: Gene_name_organism
   - Save the fasta file with the corresponding accession ID ended in .fasta
   - Subfolder: Blast
    
#### Mouse Gad1 gene 
It had 10 isoform at mRNA level. Here we picked the longest one which was 
mRNA reference sequence NM_001420099, 3561 bp

https://www.ncbi.nlm.nih.gov/nuccore/NM_001420099.1

FASTA sequence:

>NM_001420099.1 Mus musculus glutamate decarboxylase 1 (Gad1), transcript variant 3, mRNA
 CTTCTTCAGGCTCTCCCGTGCCGGACCAGGGATCGTGCAAGCAAGGAAGCAGCCCTGGGGTGACACCCAG
 CACGTACTCCTGTGACAGAGCCGAGCCCAGCCCAGCCCCGGGACGCTTCGCAGAGGAGTCGCGGGAGGGT
 CCAGCTCGCTGTCGCTGAACCGAGGTGGGTAAATACCGGATCGCCCGGACTTGCCAGAGCCCCGCCTCGG
 TTATTCAACCCGGTGCCCTCAGCCTGCGGCTTCTTGTCCAGCCCTTTGCCTCACCCCACCAGCACGCGCC
 TGTCGCCCACCTTCCACAGCCGAGTGCTTCCCGCCAGTCCTGTCGCAGCTGTGGTTTGGCGCACCCATCC
 CCTACCCTCCTCGCTCTTGAAACCCTTATCAATTTCATTCGGGAGGACACATAAGGGCTGAAGTGACCCC
 AGAGCCATTTTTTGCCTGCGCTTGGGGGATCGGAGCTCACGGCTGTCGGATACGCGCCTGGGTAGCAGCG
 GCAGAAGCCTGTTCCTGCGCCCAGTCTGCGGGGGACCCTTGAACCGTAGAGACCCCAAGACCACCGAGCT
 GATGGCATCTTCCACTCCTTCGCCTGCAACCTCCTCGAACGCGGGAGCGGATCCTAATACTACCAACCTG
 CGCCCTACAACGTATGATACTTGGTGTGGCGTAGCCCATGGATGCACCAGAAAACTGGGCCTGAAGATCT
 GTGGCTTCTTACAAAGGACCAATAGCCTGGAAGAGAAGAGTCGTCTTGTGAGCGCCTTCAGGGAGAGGCA
 GTCCTCCAAGAACCTGCTTTCCTGTGAAAACAGTGACCAGGGTGCCCGCTTCCGGCGCACAGAGACCGAC
 TTCTCCAACCTGTTTGCTCAAGATCTGCTTCCAGCTAAGAACGGGGAGGAGCAAACTGCGCAGTTCTTGC
 TGGAAGTGGTAGACATACTCCTCAACTATGTCCGCAAGACATTTGATCGCTCCACCAAGGTTCTGGATTT
 CCACCACCCACACCAGTTGCTGGAAGGCATGGAAGGCTTTAATTTGGAGCTGTCTGACCACCCCGAGTCT
 CTGGAGCAGATCCTGGTTGACTGTAGAGACACCCTGAAGTACGGGGTTCGCACAGGTCACCCTCGATTTT
 TCAACCAGCTCTCTACTGGTTTGGATATCATTGGTTTAGCTGGTGAATGGCTGACATCGACTGCCAATAC
 CAATATGTTCACATATGAAATTGCACCCGTGTTTGTTCTCATGGAACAGATTACTCTTAAGAAGATGAGA
 GAGATCGTTGGATGGTCAAATAAAGATGGTGATGGGATATTTTCTCCTGGGGGAGCCATATCCAATATGT
 ACAGCATCATGGCTGCTCGTTACAAGTACTTCCCAGAAGTGAAGACAAAAGGCATGGCGGCTGTGCCCAA
 ACTGGTCCTCTTCACCTCAGAACACAGTCACTATTCCATAAAGAAAGCCGGGGCTGCGCTTGGCTTTGGA
 ACCGACAATGTGATTTTGATAAAGTGCAATGAAAGGGGGAAGATAATTCCGGCTGATTTAGAGGCAAAAA
 TTCTTGATGCCAAACAAAAGGGCTATGTTCCCCTTTATGTCAATGCAACCGCAGGCACGACTGTTTACGG
 AGCATTCGATCCAATCCAGGAAATTGCGGACATATGTGAGAAATACAACCTTTGGCTGCATGTGGATGCT
 GCCTGGGGTGGTGGACTGCTCATGTCCCGGAAGCACCGCCACAAACTCAGCGGCATAGAAAGGGCCAATT
 CAGTCACCTGGAACCCTCACAAGATGATGGGCGTGCTGCTCCAGTGCTCTGCCATTCTGGTCAAGGAAAA
 GGGTATACTCCAAGGATGCAACCAGATGTGTGCAGGCTACCTCTTCCAGCCAGACAAGCAGTATGACGTC
 TCCTATGACACCGGGGACAAGGCGATTCAGTGTGGCCGCCATGTGGACATCTTCAAGTTCTGGCTGATGT
 GGAAAGCAAAGGGCACCGTGGGATTTGAAAACCAGATCAACAAATGCCTGGAGCTGGCTGATTACCTCTA
 CGCCAAGATTAAAAACAGAGAAGAGTTTGAGATGGTTTTCGATGGTGAGCCTGAGCACACAAATGTCTGT
 TTCTGGTACATTCCACAAAGCCTTCGAGGGGTTCCAGATAGCCCTGAGCGACGAGAAAAGCTACACAGGG
 TGGCTCCCAAGATCAAAGCTCTGATGATGGAGTCAGGAACAACCATGGTGGGCTACCAGCCTCAAGGGGA
 CAAGGCCAACTTCTTCCGGATGGTCATCTCTAACCCAGCCGCCACCCAGTCTGACATCGATTTCCTCATT
 GAGGAGATAGAGAGGTTGGGTCAGGATCTGTAATCCCTCTTTACAGAACCAGAATCATCGGCCATGCTTG
 TGCCCCTCTGGTACCCTAGAGCACAGCTCTGTCAGTAGCTGACACATCTAGGCCATCTCACTGAAGGAAA
 TTACAATCTCTTAAAGAATATTTGTCACATTTCACATAAGCTTGTTTGTTAGAGCTAGTGGGGAAATAAT
 GTTCTTTTTAAAAAATTGCACATTAGAAACACAGTATATATGTACAGTTATATATACCTCTCTCTATGTA
 CATGTATGTATAGTGACTGTGGCTTAGTCCTAGACCATAGCATGTTGCTCGTCCCCAGGAAATTAGCCTT
 ACCCCCAGCAATTACTAAGAGGCTAAACCATCTCGCAAGCAACTACAGGGCGGATGGTATCCCTACTGCA
 GTGTCCTAGGGACCCAGGGAAAGGCTGTTGGTGGGAGGCTACCTCCCTGCTAGAGCTGTTCCCACGTGAA
 GGGATGATGGATGACAGATGTACCAGTAAATGACAAATGTCACACCCTCCCTGTTAGTACCCTGCTAGGG
 GAAATAGTAGCAGTCTTTGTCACAATTGTGCTTTGCTGTGTTTTAGAGATTAATCTGTGTAAACTGTGTA
 CATTGCCATTGTCTATCTTTGGGCAGGGGGAAGTGCATATAATGATTAAATTGTATGTCAGTGAGATATC
 TGCTTATTTATATTCAAATATATACCATGTTAAAGAGACATCTTGTATTTTCTTCCCATTTGTAATGTAT
 CTTATTTATATATTAATGGAGTAAGTTCTGGATACTGTTTATGGTATTTTCGTGCATTTGTGAGCCAAAG
 AGAAAAGATGAAAATTAGTGAGATTTGCATTTATATTAGAGTGCCCTTAACATAATGATTTGAACATATG
 TGTACTGTCTGGAAAAGAATTCTGATACTGTACATAGAGTCATGTTATGGAAATCTTGCTTCAGTAGCCT
 TCGCTCTTCTCTTTCCCCCCTCAGGCTGTATGTCAGATGTTCTCAAAGCTTTTCTAGTAACTGTTGAATA
 ATAATAACTAGATCTCCTGTAATTTTGTAGTAGTATATGACCAATCTCTGTGACTCGCTTAGCTGAAACC
 TAAGGCAATGTTTCTGAAGACCTCCGATACACTGACCAGTCCCACAAGTGTTTTTGAAGACATGAAACCC
 ACACTGTGCATTTAGGGTGTGCAAGAAGAATATAAATAAAATAAAAAATATTCTCCATGAA'

#### Mouse Tph2 gene  
mRNA reference sequence NM_173391.3, 2626 bp

https://www.ncbi.nlm.nih.gov/nuccore/NM_173391.3

FASTA sequence:

>NM_173391.3 Mus musculus tryptophan hydroxylase 2 (Tph2), mRNA
CACTGCTCTTCAGCACCAGGGTTCTGGACAGCGCCCCGAGCAGGCAGCTGCCACTGCAGTTCCTCCTTCA
TCTCTGCCAAGGCCGCCCCTCTGGTCCCCCCTGCTGCTGAGAAAGAAAATTACATCGGGAGCCATGCAGC
CCGCAATGATGATGTTTTCCAGTAAATACTGGGCCAGGAGAGGGTTGTCCTTGGATTCTGCTGTGCCAGA
AGATCATCAGCTACTTGGCAGCTTAACACAAAATAAGGCTATCAAAAGCGAGGACAAGAAAAGCGGCAAA
GAGCCCGGCAAAGGCGACACCACAGAGAGCAGCAAGACAGCGGTAGTGTTCTCCTTGAAGAATGAAGTTG
GTGGGCTGGTGAAAGCACTTAGACTATTCCAGGAAAAACATGTCAACATGCTTCATATCGAATCCAGGAG
GTCCCGACGAAGAAGTTCTGAAGTCGAAATCTTCGTGGACTGCGAATGTGGCAAAACGGAATTCAATGAG
CTCATCCAGTTGCTGAAATTTCAGACCACCATTGTGACCCTGAATCCGCCTGAGAGCATTTGGACGGAGG
AAGAAGATCTCGAGGATGTGCCGTGGTTCCCTCGGAAGATCTCTGAGTTAGACAGATGCTCTCACCGAGT
CCTCATGTACGGCACCGAGCTTGATGCCGACCATCCAGGATTTAAGGACAATGTCTATCGACAGAGGAGG
AAGTATTTTGTGGATGTGGCCATGGGCTATAAATATGGTCAGCCCATTCCCAGGGTCGAGTACACAGAAG
AAGAGACTAAAACTTGGGGTGTTGTGTTCCGGGAGCTCTCCAAACTCTACCCGACTCATGCTTGCCGGGA
GTACCTGAAAAACCTCCCCCTGCTGACCAAGTACTGTGGCTACAGGGAAGACAACGTGCCGCAACTGGAA
GACGTCTCCATGTTTCTGAAAGAGCGATCTGGCTTCACAGTGAGACCAGTGGCTGGCTACCTGAGCCCAA
GAGACTTCCTGGCGGGCCTGGCCTACAGAGTATTCCACTGCACCCAGTACGTGCGGCATGGCTCCGACCC
CCTCTACACCCCGGAACCAGATACATGCCATGAACTCTTGGGACACGTGCCACTGCTTGCGGATCCCAAG
TTTGCTCAGTTTTCCCAAGAGATAGGCTTAGCGTCTCTGGGAGCCTCAGATGAGGACGTTCAGAAACTAG
CCACGTGCTATTTCTTCACAATCGAGTTCGGCCTTTGCAAGCAAGAGGGTCAACTGCGGGCGTATGGAGC
AGGGTTACTTTCGTCCATCGGAGAATTGAAGCATGCTCTTTCCGACAAGGCGTGTGTGAAATCCTTTGAC
CCAAAGACGACCTGCTTGCAGGAATGCCTAATCACCACCTTTCAGGACGCTTACTTTGTTTCGGACAGTT
TTGAAGAAGCCAAAGAAAAGATGAGGGACTTTGCAAAGTCAATTACCCGTCCCTTCTCGGTATACTTCAA
CCCCTACACGCAGAGCATTGAAATTCTGAAAGACACCAGAAGTATTGAGAATGTGGTGCAGGACCTGCGC
AGTGATTTGAACACAGTGTGTGATGCCTTGAATAAAATGAACCAATATCTGGGGATTTGATGCCTAGAAC
CAGAGTTATTGTCAGCATGAGCTCTTGGGGGGTGTAGCAACAATGCAGTCAATGTTATCCAACATCAACA
ACTTTCTGTGTCATGGTTGGCTAGTAAGCATGCAATTCTGTATGTCCATACCTCTGTGTAACTTAATAAC
ACAAAAATGCTCTAAAGAACCCATGCAGATAACCACTCACCATTTGAAAGATTGTGATCCTATTTGGACA
TCTCAAGTAGAGTTGACATTTCTGATTAGCGAACAAACTGTTAACTTAAGCAAACTGTGACTTTGAAATC
TGTAGCAAACATTCCTCGCACAATTCCAGTCGGTGAGTTGTGGAACTTTTCTTCCTTGGACCTGAGACTT
TCCTCTGTGTTCATTAGATAAAATGAAAATAGTTGGGAGGTGGTTTCTATTTTCAATAGTATCCGTGTTA
TTTGAGATAAACTAGAGTTGCTCCACGCTTTGCATCACAGCAACAAAGGATTTAATATTCTACTTCAGAA
GCTGTTCAGAAACACAGCAGTTGGGATGGATGTAGACTGAGTGTTCAGACAATGCAAGCAAAGAAAAGTT
TTGATAAACAGGATATATAGGTTGTACTGACCTCGTTGAAACCAATTTGTGGCAAGCTTCCTGAAGAGCT
TCTGGAAGGAAACACTTGAACAAAGAATATTCGGGAAGCTTAAACAGAAGGGATGAAAATCTTGGAACTG
TGAATGTATTGTTAGGATAGAGTGAATTATCACTGCAGGCTTTTGACTCCTTTTGCTTAGACTGAGAACC
TCAAATCCCACAGGGATGTAAATACCATCTCTGATTCCAAAGAGTTGGAGACGGAGTCGTAGAGAAACAA
AGGGATTTGCTTCAGTTAGGTCTGATGAGATGTGCCATGGTCATAAGCCACTGCCCTTTTATGTTGGACA
TCTGACAAGTCTACTGTAGTGTACATGCATGTTTATGTATTGACACAGAAAGAAAATTATTGCTTATAAA
ATGAATGCTTCTCAATAAACAGAATCTTGCCCCCAA

### 2. Perform BLAST sequence similarity check

Here, we run BLAST using the FASTA sequence downloaded. The following steps are described below.
- Run Blast
- Download results
- Extract the sequence regions excluded for probe design

#### Run Blast
- Go to NCBI Blast home page: https://blast.ncbi.nlm.nih.gov/Blast.cgi  
- Scroll down to the section for "BLAST Genomes" and type the organism which you are interested in (in this case it is Mus musculus (Mouse).  
- After typing the Mouse, another webpage opens which brings you to the blast webpage:  
- https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastSearch&BLAST_SPEC=OGP__10090__9559&LINK_LOC=blasthome  
- Paste a fasta sequence that you obtained from step 1 in "Enter Query Sequence" section.  
   - Then, under the "Choose Search Set" -> Database tab, choose RefSeq RNA.  
   - Under the "Program Selection" tab, choose "Somewhat similar sequences (blastn)" algorithm.  
   - Optional: you can mark on "Show results in a new window". This opens your blast results in another window.  
- Other settings are default

<img width="1288" alt="Screenshot 2024-05-30 at 15 17 26" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/2334032a-5d88-4e1c-91cd-4a9c8a8c6d0f"><br>

### Download results

- From "Alignments" tab, click on Download on the right corner of the window and download hit table files both in txt and csv in sub-folder Blast (see folder structure in step No.1). Also save the entire web page as html file for the record in that folder.

<img width="1295" alt="Screenshot 2024-05-30 at 15 22 23" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/4d4e4927-d2aa-4c33-a7f0-5734bc2607d4"><br>

### Extract the sequence regions excluded for probe design

Here, we specify the regions that are excluded from probe design due to similarity:
   
- In the HTML file or blast result, check the column specifies the percent identity and look down and find the rows that are below 100%:
   
<img width="1015" alt="Screenshot 2024-05-30 at 15 51 21" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/556d0489-2a5e-4e6e-99c2-9f0e60cc879f"><br>

<img width="987" alt="Screenshot 2024-05-30 at 16 00 23" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/c36a6f91-c6f5-4a01-b009-307b22211e05"><br>

- In the csv file downloaded earlier, highlight the corresponding regions of the query transcript that show allignment (columns G and H in the csv file). These are the regions we want to exclude from being targeted during probe design, to prevent non-specific probe binding.
- For good record keeping, save this highlighted file within the Blast folder as an xls file and a txt file. 
- Confirm which transcript sequences you want to remove (columns G and H for 
- Copy and paste this region into another Excel sheet and save it in the csv file in the main folder with ExcludeRegion.csv (step 1).   
- The ExcludeRegion.csv file should look like this:
   
   <img width="220" alt="Screenshot 2024-05-30 at 16 22 17" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/4054981f-1105-4b2a-8a99-4ce174a79a41"><br>

- Specify the hairpin type by making an Excel sheet having e.g. B1, and then save the file in csv format with the name of B((number from 1 to 5)).csv as shown in the image below.
   
   <img width="264" alt="Screenshot 2024-05-30 at 16 13 44" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/adc955f8-1cad-44e0-8566-f1fd7aebf09a"><br>

- The final folder structure should look like this:

<img width="661" alt="Screenshot 2024-05-30 at 16 14 39" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/cb2b1a6d-36c0-4055-8003-4377d14a116f"><br>

- NOTE: in MacOS the csv file from the Hit Allignment may open incorrectly in Excel - where the columns are not separated. In this case, select column A and go to data > text to columns > Delimited > comma > general > finish. This should open the data in the correct format, but check the formatting is as you expect.
- NOTE: when choosing the RefSeq transcript, mutliple results may come up for a particular transcript, that differ in annotation status. A transcript that begins with the  "NM_" prefix indicates that it has been reviewed and is well-supported by experimental data. A transcript that begins with the "XM_" prefix is a computationally predicted variant based on genomic data but has not been experimentally confirmed. Therefore, always choose the "NM" transcript if available. This means that "XM" predicted variants of the transcripts may have longer sequences and therefore less than 100% identity with the query transcript, but these regions of allignment should not be excluded from probe design. Therefore, when downloading the Hit Allignment file, it is best to deselect these transcripts, as shown:


## 3. Run the script here to have probe sequences

## Authors

Shigeaki Kanatani  
Razieh Karamzadeh

## Reference
Whole-Brain Three-Dimensional Imaging of RNAs at Single-Cell Resolution
Shigeaki Kanatani, Judith C. Kreutzmann, Yue Li, Zoe West, Danai Vougesi Nikou, Jacob Lercke Skytte, Lea Lydolph Larsen, Daisuke H. Tanaka, Dagmara Kaczynska, Keishiro Fukumoto, Naofumi Uesaka, Tsutomu Tanabe, Ayako Miyakawa, Urmas Roostalu, Jacob Hecksher-Sørensen, Per Uhlén  
  
bioRxiv 2022.12.28.521740; doi: https://doi.org/10.1101/2022.12.28.521740  



   
