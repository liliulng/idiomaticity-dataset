## Assessing BERT’s sensitivity to idiomaticity

This is a dataset for assessing CamemBERT’s sensitivity to idiomaticity.   

The dataset contains data extracted from the French Lexical Net-work (LN-fr), a handcrafted lexical resource containing 3,127 idioms, 22,551 free lexemes, and 47,395 contextual sentences for these entries.  

The original data is downlowadable at https://www.ortolang.fr/market/lexicons/lexical-system-fr/v1?lang=en


This dataset comprises five CSV files with a total of 12 columns and 59,092 rows. Below is an explanation of the main information contained in each column:

- **ID** : id of lexical units (simple lexeme or idioms) in LN-Fr.

- **entry** : disambiguated simple lexemes and idioms

- **POS** : part of speech of simple lexemes and idioms.

- **idiomaticity** : free lexeme, weak idiom, semi-idiom and strong idiom, classification according to Meaning-Text Theory of Igor Mel'čuk, the related paper in listed in the references.

- **token** : token to be masked. For free lexemes, the token masked is the lexeme itself. For idioms, idioms are seperated by space and punctuations then every of their tokens.

- **token_POS** : part of speech of the masked token 

- **sentence**: example sentence 

- **sentence_tokens** : list of tokens obtained by tokenizing sentence with CamemBERT Tokenizer.

- **subtoken_index** : index of subtokens of token in "sentence_tokens". Some tokens are tokenized as several subtokens.

- **sentence_tokens_masked** : list of tokens of sentence where tokens or subtokens of tokens are masked, replaced by index for "\<mask\>" : 32004.

- **token_score** : prediction score returned for the correct prediction (prediction same as the masked token).

- **R1** : binary value, True or False, indicating wether the correct prediction is the best prediction, the first prediction returned, the prediction at rank 1 (R1). This represents a high confidence of CamemBERT for this prediction.

## References

Veronika Lux-Pogodalla, Alain Polguère. Construction of a French Lexical Network: Methodological Issues. *First International Workshop on Lexical Resources*, WoLeR 2011, Aug 2011, Ljubljana, Slovenia. pp. 54-61, 2011.

Analyse et traitement informatique de la langue française - UMR 7118 (ATILF) (2017). *Réseau Lexical du Français (RL-fr)* [Lexique]. ORTOLANG (Open Resources and TOols for LANGuage) - www.ortolang.fr, v1, https://hdl.handle.net/11403/lexical-system-fr/v1.

Igor A. Mel’čuk. 2023. *General phraseology: Theory and practice*. John Benjamins.

Igor A. Mel’čuk. 2006. Parties du discours et locutions. *Bulletin de la Société de Linguistique de Paris*, 101:29–65.
