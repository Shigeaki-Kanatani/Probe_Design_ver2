# In situ HCR_Probe_Design_ver2

## 1. Introduction
This program is version 2 of the probe design script used for the whole brain in situ hybridization method (Kanatani S et al., biorxiv, 2022). It has a more convenient probe design workflow than version 1.  

The overall workflow of the script is
1.	Obrain reference sequence from NCBI
2.	Perform BLAST and remove similar sequences
3.	Run the script here to have probe sequences

Here, we show the practical example of how to use this script below using a mouse Gad1 and Tph2 mRNA. (The example was done on 2024-May-30)

## Example1, Mouse Gad1 gene, 
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
ACACTGTGCATTTAGGGTGTGCAAGAAGAATATAAATAAAATAAAAAATATTCTCCATGAA

## Example2, Tph2 gene, mRNA reference sequence NM_173391.3, 2626 bp

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

## 2. Make a folder structure as below:

   Main folder: Gene_name_organism
      Save the fasta file with the corresponding accession ID ended in .fasta
      Subfolder: Blast
   
2. Perform BLAST sequence similarity check:

### 2.1. Go to NCBI gbast home page: https://blast.ncbi.nlm.nih.gov/Blast.cgi  
### 2.2. Scroll down to the section for "BLAST Genomes" and type the organism which you are interested in (in this case it is Mus musculus (Mouse).  
### 2.3. After typing the Mouse, another webpage opens which brings you to the blast webpage:  
### 2.4. https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastSearch&BLAST_SPEC=OGP__10090__9559&LINK_LOC=blasthome  
### 2.5. Paste a fasta sequence that you obtained from step 1 in "Enter Query Sequence" section.  
   2.5.1. Then, under the "Choose Search Set" -> Database tab, choose RefSeq RNA.  
   2.5.2. Under the "Program Selection" tab, choose "Somewhat similar sequences (blastn)" algorithm.  
   Optional: you can mark on "Show results in a new window". This opens your blast results in another window.  
### 2.6. Other setting is default

<img width="1288" alt="Screenshot 2024-05-30 at 15 17 26" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/2334032a-5d88-4e1c-91cd-4a9c8a8c6d0f">

3. From "Alignments" tab, click on Download on the right corner of the window and download hit table files both in txt and csv in sub-folder Blast (step-2). Also save the html file as the record in that folder.

3.1. First page that appears (by default Discription Tab):

<img width="1295" alt="Screenshot 2024-05-30 at 15 22 23" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/4d4e4927-d2aa-4c33-a7f0-5734bc2607d4">

3.2. After clicking on the "Alignments" tab:

<img width="1295" alt="Screenshot 2024-05-30 at 15 22 23" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/327106bc-f5c3-402f-b543-439e56ca2cab">


5. specify the regions which are not used for probe design:
   
   5.1. In the html file (or blast result page step: 3.2.) Check the column specifies the percent identity and look down and find the rows that are below 100%:
   
<img width="1015" alt="Screenshot 2024-05-30 at 15 51 21" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/556d0489-2a5e-4e6e-99c2-9f0e60cc879f">

   5.2. Mark them or highlight them in csv file you downloaded earlier in step 3, then save the file for the record in the same folder with the name of highlighted version in .xls
   5.3. Confirm what transcripts you want to remove.
   5.4. Copy pase this region in another Excel sheet and save it in csv in the main folder with the name of ExcludeRegion.csv (step 1).
   
<img width="987" alt="Screenshot 2024-05-30 at 16 00 23" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/c36a6f91-c6f5-4a01-b009-307b22211e05">

   5.3. The ExcludeRegion.csv file should look like this:
   
   <img width="220" alt="Screenshot 2024-05-30 at 16 22 17" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/4054981f-1105-4b2a-8a99-4ce174a79a41">

   
6. Specify the block by opening a an Excel sheet type B(number from 1 to 5), e.g. B1, and then save the file in csv format with the name of B((number from 1 to 5)).csv
   
   <img width="264" alt="Screenshot 2024-05-30 at 16 13 44" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/adc955f8-1cad-44e0-8566-f1fd7aebf09a">

Final folder strucure should look like this:

<img width="661" alt="Screenshot 2024-05-30 at 16 14 39" src="https://github.com/Shigeaki-Kanatani/Probe_Design_ver2/assets/40339288/cb2b1a6d-36c0-4055-8003-4377d14a116f">

7. Run the MATLAB script and make a table




### Reference
Whole-Brain Three-Dimensional Imaging of RNAs at Single-Cell Resolution
Shigeaki Kanatani, Judith C. Kreutzmann, Yue Li, Zoe West, Danai Vougesi Nikou, Jacob Lercke Skytte, Lea Lydolph Larsen, Daisuke H. Tanaka, Dagmara Kaczynska, Keishiro Fukumoto, Naofumi Uesaka, Tsutomu Tanabe, Ayako Miyakawa, Urmas Roostalu, Jacob Hecksher-Sørensen, Per Uhlén  
  
bioRxiv 2022.12.28.521740; doi: https://doi.org/10.1101/2022.12.28.521740  

   
