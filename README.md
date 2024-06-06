## Assessing BERT’s sensitivity to idiomaticity

This is a dataset for assessing CamemBERT’s sensitivity to idiomaticity.

The dataset contains data extracted from the French Lexical Network (LN-fr), a handcrafted lexical resource containing 3,127 idioms, 22,551 free lexemes, and 47,395 contextual sentences for these entries.

The original data is downloadable [here](https://www.ortolang.fr/market/lexicons/lexical-system-fr/v1?lang=en)

This dataset is a TSV file comprising a total of 9 columns and 59,092 rows. Below is an explanation of the main information contained in each column:

- **ID** : id of lexical units (simple lexeme or idioms) in LN-Fr.
- **entry** : disambiguated simple lexemes and idioms
- **POS** : part of speech of simple lexemes and idioms.
- **idiomaticity** : free lexeme, weak idiom, semi-idiom and strong idiom, classification according to Meaning-Text Theory of Igor Mel'čuk, the related paper in listed in the references.
- **token** : token to be masked. For free lexemes, the masked token is the lexeme itself. For idioms, idioms are seperated by space and punctuations then every of their tokens are masked one at a time.
- **token_POS** : part of speech of the masked token 
- **sentence**: example sentence with the token masked, replaced by "\<mask\>". Some tokens are tokenized by CamemBERT Tokenizer as several subtokens, each subtoken is masked one at a time.
- **token_score** : prediction score returned for the correct prediction (prediction same as the masked token). For tokens tokenized as subtokens, their prediction score is the product of their subtokens' scores.
- **R1** : binary value, True or False, indicating wether the correct prediction is the best prediction, the first prediction returned, the prediction at rank 1 (R1). This represents a high confidence of CamemBERT for this prediction.


## Citation

If you use this dataset, please cite this paper:

Li Liu and Francois Lareau. 2024. [Assessing BERT’s sensitivity to idiomaticity](https://aclanthology.org/2024.mwe-1.4). In *Proceedings of the Joint Workshop on Multiword Expressions and Universal Dependencies (MWE-UD) @ LREC-COLING 2024*, pages 14–23, Torino, Italia. ELRA and ICCL.

## References

Lux-Pogodalla, V. and Polguère, A. 2011. Construction of a French Lexical Network: Methodological Issues. In *First International Workshop on Lexical Resources*, WoLeR 2011, Aug 2011, Ljubljana, Slovenia. pp. 54-61.

Analyse et traitement informatique de la langue française - UMR 7118 (ATILF) (2017). *Réseau Lexical du Français (RL-fr)* [ORTOLANG (Open Resources and TOols for LANGuage)](https://hdl.handle.net/11403/lexical-system-fr/v1).

Mel’čuk, I.A. 2023. *General phraseology: Theory and practice*. John Benjamins.

Mel’čuk, I.A. 2006. Parties du discours et locutions. *Bulletin de la Société de Linguistique de Paris*, 101: 29–65.

## Licence

This data is distributed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) licence.
