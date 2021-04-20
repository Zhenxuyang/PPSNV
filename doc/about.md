# 突变打分

## 已有模型

名称|实现方法|备注
-----|-----|-----
PolyPhen-2||
SIFT||
FatHMM||
MutationTaster-2||
MutationAssessor||
CADD||
LRT||
phyloP||
GERP++||

## 数据集

数据集|阳性数据|阴性数据|备注
-----|-----|-----|-----
HumVar| UniProtKB中所有的致病突变| MAF>1%的常见nsSNPs| <http://genetics.bwh.harvard.edu/pph2/dokuwiki/overview>
ExoVar|在分子功能上导致孟德尔疾病的5340个等位基因|4,752 rare (alternative/derived allele frequency <1%) nsSNVs with at least one homozygous genotype for the alternative/derived allele in the 1000 Genomes Project| <http://www.plosgenetics.org/article/info%3Adoi%2F10.1371%2Fjournal.pgen.1003143>
VariBench| 从PhenCode、IDBases 、LSDBS数据库中获取的19335个致病错义突变| 从dbSNP中获取的21170个中性和同义SNP |  <http://structure.bmc.lu.se/VariBench/tolerance_dataset1.php>
predictSNP|从SwissProt, HGMD, HumVar, Humsavar, dbSNP, PhenCode, IDbases, and 16 individual locus-specific databases中获取的致病突变 | 从同样的数据库中获取的非致病突变|<http://www.ploscompbiol.org/article/info%3Adoi%2F10.1371%2Fjournal.pcbi.1003440>
SwissVar| 在病人和文献中发现和疾病关联| 没有被报告过和疾病关联的变异| <http://swissvar.expasy.org/cgi-bin/swissvar/documentation>


Datasets | Deleterious variants(D) | Neutral variants (N) | Total | Ratio (D:Total) | Tools potentially trained on data (fully or partly) | Removed variants overlapping with
-----|-----|-----|-----|-----|-----|-----
HumVar | 21,090 | 19,299 | 40,389 | 0.52 | MT2, MASS, PP2,FatHMM-W | CADD training data
ExoVar | 5,156 | 3,694 | 8,850 | 0.58 | MT2, MASS, PP2, FatHMM-W | CADD training data
VariBenchSelected | 4,309 | 5,957 | 10,266 | 0.42 | MT2 | CADD training data, HumVar, ExoVar
predictSNPSelected | 10,000 | 6,098 | 16,098 | 0.62 | MT2 | CADD training data, HumVar, ExoVar VariBench
SwissVarSelected | 4,526 | 8,203 | 12,729 | 0.36 |  MT2 | CADD training data, HumVar, ExoVar VariBench, predictSNP

## 特征

CADD使用的特征

![img](.\img\features_cadd1.png)
![img](.\img\features_cadd2.png)