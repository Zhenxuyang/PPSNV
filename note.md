SIFT:SIFT predicts substitutions with scores less than 0.05 as deleterious

PolyPhen-2 uses eight sequence-based and three structure-based predictive features 

probably damaging above 0.85
possibly damaging above 0.15
benign remaining


MutationAssessor 1.9

Precomputed scores from MutationAssessor release 2 (hg19) were downloaded from http://mutationassessor.org/. We used its functional impact combined score as our MutationAssessor score, which ranges from -5.545 to 5.975; the larger the score the more likely it will be deleterious. MutationAssessor provides four types of predictions (to be functional): high, medium, low and neutral. To form binary predictions, we treat high and medium predictions as “deleterious” and low and neutral predictions as “tolerated”.

VEST 3.0 scores range from 0 to 1 with a higher score indicating a higher likelihood to be deleterious. VEST does not provide binary predictions. Multiple scores are separated by “;” and the corresponding transcript IDs are presented in the Transcript_id_VEST3 column.

LRT D deleterious N neutral U unknown

MutationTaster A and D deleterious N and p neutral

FATHMM 
These score ranges from -18.09 to 11.0; the smaller the score the more likely it will be deleterious. Binary prediction is also provided and the threshold separating “deleterious” and “tolerated” is -1.5. In case there are more than one FATHMM scores for the same nsSNV due to isoforms, we took the smallest score (most deleterious) as our FATHMM score.

CADD
What are the scores in the files and which score cutoff should I use?
The last column of the provided files is the PHRED-like (-10*log10(rank/total)) scaled C-score ranking a variant relative to all possible substitutions of the human genome (8.6x10^9). Like explained above, a scaled C-score of greater of equal 10 indicates that these are predicted to be the 10% most deleterious substitutions that you can do to the human genome, a score of greater or equal 20 indicates the 1% most deleterious and so on.

The second to last column is the raw score of the model. Due to the high mislabeling in our training data, it does not have any interpretation (even the sign does not have an interpretation). The higher the raw C score the more predicted to be deleterious. If you want to do a non-parametric test between sets of variants, we recommend using this raw C-score (see above). If you want to put a cutoff on deleteriousness, we recommend the last column (scaled C-score) as it has some interpretation by relating the raw C-score to the raw C-scores of all possible substitutions in the human genome.

If you would like to apply a cutoff on deleteriousness, e.g. to identify potentially pathogenic variants, we would suggest to put a cutoff somewhere between 10 and 20. Maybe at 15, as this also happens to be the median value for all possible canonical splice site changes and non-synonymous variants in CADD v1.0. However, there is not a natural choice here -- it is always arbitrary. We therefore recommend integrating C-scores with other evidence and to rank your candidates for follow up rather than hard filtering.

radialsvm <0 tolerated >0 deleterious



