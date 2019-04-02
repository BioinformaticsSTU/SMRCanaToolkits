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
python3 get_AS.py options
```
List of options available:

- **-n**  | **--names**: names of GTF format file/files containing at least "exon" lines

- **-p**  | **--prefix**: prefix of output files

The command line to generate local AS events will be of the form:

```
python3 get_AS.py -n <names> -p <prefix>
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

<img src="https://github.com/BioinformaticsSTU/SMRCanaToolkits/blob/master/CDZ/bar.png" width = "400" height = "400"  />
bar.png

<img src="https://github.com/BioinformaticsSTU/SMRCanaToolkits/blob/master/CDZ/barh_align.png" width = "400" height = "400"  />
barh_align.png

----------------------------
## get_score_D.py: calculate score_D of each gene.
----------------------------

### Input files

ioi file contains the transcript "events" in each gene.

### usage
```
python3 get_score_D.py options
```
List of options available:

- **-c**  | **--control**: name of control sample

- **-t**  | **--treated**: name of treated sample

The command line to generate local AS events will be of the form:

```
python3 get_score_D.py -c <control> -t <treated>
```

### Output files

score_D.txt
```
	control_transcripts	treated1_transcripts	treated1_score	treated2_transcripts	treated2_score	
ENSG00000151466	ENST00000281142,ENST00000506368	ENST00000281142,ENST00000511426	0.667	ENST00000506368,ENST00000511426	0.667	1.334
ENSG00000128059	ENST00000264220	ENST00000264220	0	ENST00000264220	0	0
ENSG00000033178	ENST00000322244,ENST00000429659	ENST00000322244,ENST00000429659	0	ENST00000322244,ENST00000429659	0	0
ENSG00000145414	ENST00000274054	ENST00000274054	0	ENST00000274054	0	0
ENSG00000138767	ENST00000504123,ENST00000512485	ENST00000504123,ENST00000512485	0	ENST00000504804	1	1
```

To quantify the differential isoform usage between cells, we defined the score D of each gene as follows:

$$\sum_{i=1}^{4} \frac{c_i}{d}   whereas c = a \quad \bigcup b; d = a \quad \bigcup b


$$\sum_{i=1}^n \frac{1}{i^2} \quad and \quad \prod_{i=1}^n \frac{1}{i^2} \quad and \quad \bigcup_{i=1}^{2} R$$


where gene j has isoform set a , and set b respectively in cell line X and Y ; c is the number of isoform intersection for set a and set b; d is the number of isoform union for set a and set b. Thus D sums up scores when comparing the control sample and treated samples.

----------------------------
## get_GO.py: select top 500 genes and make GO enrichment analysis
----------------------------















