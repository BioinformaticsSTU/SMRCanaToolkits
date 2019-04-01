----------------------------
## get_AS.py: calculate the proportion of each alternative splicing event in different samples and create graphs.
----------------------------

### Input files

An annotation file in GTF format is required (see e.g. http://mblab.wustl.edu/GTF22.html):

```
chr14 Ensembl exon  73741918  73744001  0.0 - . gene_id "ENSG00000000001"; transcript_id "ENST00000000001.1"; 
chr14 Ensembl exon  73749067  73749213  0.0 - . gene_id "ENSG00000000001"; transcript_id "ENST00000000001.1";  
chr14 Ensembl exon  73750789  73751082  0.0 - . gene_id "ENSG00000000001"; transcript_id "ENST00000000001.1"; 
chr14 Ensembl exon  73753818  73754022  0.0 - . gene_id "ENSG00000000001"; transcript_id "ENST00000000001.1"; 

```

### usage
```
python3 get_AS.py subcommand options

```
List of options available:

- **-i**  | **--input-file**: a GTF format file containing at least "exon" lines

The command line to generate local AS events will be of the form:

```
python3 get_AS.py -i <input-file.gtf> -o <output-file> -f ioe -e <list-of-events>
```

### Output files

AS.txt
```
	A3	A5	AF	AL	MX	RI	SE
sample1	2131	2224	4850	1050	330	2652	4608
sample2	2638	2737	5562	1170	462	3130	5397
sample3	1689	1628	2911	431	261	2104	3267
sample4	2849	2666	6876	954	389	3851	4870
```
![bar.png](https://bitbucket.org/repo/4gEBMd/images/3120745382-Slide1.jpg)
bar.png

![barh_align.png](https://bitbucket.org/repo/4gEBMd/images/3120745382-Slide1.jpg)
barh_align.png
----------------------------
## get_score_D.py: calculate score_D of each gene.
----------------------------







----------------------------
## get_GO.py: select top 500 genes and make GO enrichment analysis
----------------------------















