# Probe_Design_ver2
Probe_Design_ver2. More convenient probe design workflow

1. Obtain reference sequence from NCBI
   If more than one sequence for a transcipt exists, pay attention to pick the longest sequence (varient).
   Always give a priority to the reviewed one is this one exist, if it is not exist, then pick from predicted one.
   
Example1, Mouse Gad1 gene, 
It has 10 isoform at mRNA level, so pick the longest one which is 
mRNA reference sequence NM_001420099, 3561 bp

https://www.ncbi.nlm.nih.gov/nuccore/NM_001420099.1
FASTA sequence

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

