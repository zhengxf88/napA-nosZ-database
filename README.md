# napA gene database, nosZ gene database,dsrB gene database, soxB gene database
denitrification function gene taxonomy annotation reference database

sulfur cycling gene taxonomy annotation reference database

The napA, nosZ,dsrB, and soxB databases belong to a larger functional gene database called the Carbon, Nitrogen, Phosphorus, and Sulfur Functional Gene Database. The construction protocol for this database is as follows:

Construction of Carbon, Nitrogen, Phosphorus, and Sulfur Functional Database

1. The GTDB database (https://gtdb.ecogenomic.org/, Version R207) (Parks et al., 2020) was downloaded, comprising 317,542 genomic datasets and defining a total of 65,703 species reference genomes.
2. Utilizing the Prodigal software (Version 2.6.3) (Hyatt et al., 2010), protein-coding gene structures of the 317,542 genomic datasets were predicted, resulting in the corresponding amino acid and nucleotide sequences.
3. The predicted amino acid sequence set was de-duplicated by species classification at 100% similarity using UCLUST (Edgar, 2010), obtaining 331,685,519 sequences. Together with GTDB's species classification system, an amino acid sequence index library compatible with MMseqs easy-taxonomy (Mirdita et al., 2021) was built, which can be used for amplicon or metagenomic functional gene species classification.
4. From the KEGG database (Kanehisa et al., 2016), 356 prokaryotic functional genes related to carbon, nitrogen, phosphorus, and sulfur were retrieved. Additionally, HMM profiles and annotation files were acquired from the KEGG KOfams database (downloaded in June 2021) (Aramaki et al., 2020). This facilitated the construction of the GEOCYC database, encompassing 154 functional genes related to carbon, 70 to nitrogen, 104 to sulfur, and 49 to phosphorus.
5. The ko-search tool (Version 0.0.1, https://github.com/jameslz/ko-search) was employed to individually scan the amino acid sequences of the 317,542 genomes, identifying genes corresponding to each HMM profile. This elucidated the distribution of functional genes indexed in GEOCYC across genomes and species.
6. For each functional gene, de-duplication was performed on the nucleotide sequences within the same species using UCLUST (Edgar, 2010) at 100% similarity, forming a Usearch compatible sequence library.
   
References:

Aramaki, T., Blanc-Mathieu, R., Endo, H., Ohkubo, K., Kanehisa, M., Goto, S., and Ogata, H. (2020).    
KofamKOALA: KEGG Ortholog assignment based on profile HMM and adaptive score threshold. Bioinformatics 36, 2251-2252.    
Edgar, R.C. (2010). Search and clustering orders of magnitude faster than BLAST. Bioinformatics 26, 2460-2461.    
Hyatt, D., Chen, G.-L., LoCascio, P.F., Land, M.L., Larimer, F.W., and Hauser, L.J. (2010). Prodigal: prokaryotic gene recognition and translation initiation site identification. BMC Bioinformatics 11, 119.   
Kanehisa, M., Sato, Y., Kawashima, M., Furumichi, M., and Tanabe, M. (2016). KEGG as a reference resource for gene and protein annotation. Nucleic Acids Research 44, D457-D462.   
Mirdita, M., Steinegger, M., Breitwieser, F., Söding, J., and Levy Karin, E. (2021). Fast and sensitive taxonomic assignment to metagenomic contigs. Bioinformatics 37, 3029-3031.   
Parks, D.H., Chuvochina, M., Chaumeil, P.-A., Rinke, C., Mussig, A.J., and Hugenholtz, P. (2020). A complete domain-to-species taxonomy for Bacteria and Archaea. Nature Biotechnology 38, 1079-1086.    

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



How to use these datadabase

you can Uses the SINTAX algorithm to predict taxonomy for query sequences  in FASTA or FASTQ format.

Example

usearch -sintax reads.fastq -db 16s.udb -tabbedout reads.sintax \
  -strand both -sintax_cutoff 0.8

  further informaion about the sintax algorithm can be found https://www.drive5.com/usearch/manual/cmd_sintax.html



How to cite this database

Citation: Zheng X, Yan Z, Zhao C, He L, Lin Z and Liu M (2023) Homogeneous environmental selection mainly determines the denitrifying bacterial community in intensive aquaculture water. Front. Microbiol. 14:1280450. doi: 10.3389/fmicb.2023.1280450


These database constructed by Zhang Lei from from Logic Informatics Co.,Ltd., Jinan, China. Email: zhanglei@logictek.cn

  
