# Parfume recomendation
#### made by Pelmeshek

Let's imagine a situation, a perfumery company has asked us for help to increase online sales. We decided to make a recommendation system for its customers. The essence of it will be that the system will recommend to the customer a perfume that is similar to his last. As data, the company provided us with a text file containing all the perfumes that this company sells.

### In this project I will use Sentence-BERT
    Sentence-BERT is a modification of the BERT framework for enabling large-scale semantic similarity comparison, clustering, and information retrieval.

Sentence-BERT, or SBERT, uses siamese and triplet network structures to derive semantically meaningful sentence embeddings that can be compared using cosine-similarity. A siamese network consists of two or more identical subnetworks, where the two subnetworks share the same weights. Weights updating is mirrored across the subnetworks during training. The following is a diagram of the SBERT architecture with classification objective function:

![alt text](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-GPXX068IEN/images/SBERT.png)
It's apparent that SBERT uses two "twin" BERT models and adds a pooling operation to the outputs of the two BERT models. The pooling layers create the fixed-size sentence embeddings for the input sentences.

------------------------------------

Data that I used - [parfume dataset from Kaggle](https://www.kaggle.com/datasets/nandini1999/perfume-recommendation-dataset?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkGuidedProjectsIBMGPXX068IEN1371-2022-01-01)


Data that I use for test recomendation:
| № |Name|Notes|
|---|----|-----|
|0|Jo Malone - English Pear & Freesia|Pear, Melon, Freesia, Rose, Musk, Patchouli, R ...|
1 |	Jo Malone - Myrrh & Tonka |	Lavender, Myrrh, Tonka Bean, Vanilla, Almond |
2 |	Jo Malone - Oud & Bergamot |	orange, bergamot, lemon, cedar and oud. |
3 |	Guerlain - Néroli Outrenoir	| Petitgrain, Bergamot, Tangerine, Lemon, Grapef...|
4 |	Guerlain - Épices Volées | Coriander, Lemon, Artemisia, Bergamot, Clove, ... |
5 |	Guerlain - Aqua Allegoria Nerolia Vetiver Eau ... |	Basil, Vetiver, Fig Accord, Neroli |
6 |	Chloe Eau de Parfum	 | Peony, Litchi, Freesia, Rose, Lily-of-the-Vall... |

Recomendation that I collect: 
----------------------------
Recommended for Jo Malone - English Pear & Freesia:
 1. Alexandre. J - Silver Ombre Eau de Parfum (Score: 0.80)
 2. Montale - Starry Nights Eau de Parfum (Score: 0.79)
 3. BDK Parfums - Bouquet de Hongrie Eau de Parfum (Score: 0.79)
 4. Jovoy Paris - Psychedelique Eau de Parfum (Score: 0.79)
 5. L'Artisan Parfumeur - Champ de Fleurs Eau de Cologne (Score: 0.78)


Recommended for Jo Malone - Myrrh & Tonka:
 1. Parfum d'Empire - Fougere Bengale Eau de Parfum (Score: 0.86)
 2. Tauer Perfumes - Une Rose Vermeille Eau de Parfum (Score: 0.84)
 3. Xerjoff - 1861 - Naxos Eau de Parfum (Score: 0.83)
 4. PARFUMS DE NICOLAI - Amber Oud Eau de Parfum (Score: 0.83)
 5. Reims Parfums - L'Eau des Sacres (Score: 0.80)


Recommended for Jo Malone - Oud & Bergamot:
 1. Comme des Garcons: Cologne - Citrico (Score: 0.85)
 2. The House Of Oud - Cypress Shade Eau de Parfum (Score: 0.76)
 3. Xerjoff - Blue Hope Eau de Parfum (Score: 0.76)
 4. L'Artisan Parfumeur - Au Bord De L'Eau Eau de Cologne (Score: 0.76)
 5. Gravel - Across The Ocean Eau de Parfum (Score: 0.76)


Recommended for Guerlain - Néroli Outrenoir:
 1. MEMO - Winter Palace Eau de Parfum (Score: 0.83)
 2. ANFAS - Purple Sakan (Score: 0.83)
 3. The House Of Oud - Just Before Eau de Parfum (Score: 0.83)
 4. Penhaligons - Halfeti Eau de Parfum (Score: 0.83)
 5. Parfums MDCI - Le Barbier de Tanger Eau de Parfum (Score: 0.83)


Recommended for Guerlain - Épices Volées:
 1. Costume National - Homme Eau de Parfum (Score: 0.86)
 2. Roja Parfums - Creation-E Parfum Cologne (Score: 0.85)
 3. Parfums MDCI - Les Indes Galantes Eau de Parfum (Score: 0.84)
 4. Boadicea the Victorious - Ardent Eau de Parfum (Score: 0.83)
 5. Timothy Han Edition Perfumes - She Came to Stay Eau de Parfum (Score: 0.83)


Recommended for Guerlain - Aqua Allegoria Nerolia Vetiver Eau de Toilette:
 1. Liquides Imaginaires - Tellus Eau de Parfum (Score: 0.61)
 2. BYREDO - Oud Immortel Eau de Parfum (Score: 0.61)
 3. Vilhelm Parfumerie - Basilico & Fellini Eau de Parfum (Score: 0.60)
 4. Nanadebary - Green Eau de Parfum (Score: 0.60)
 5. Reims Parfums - L'Eau de Reims (Score: 0.58)


Recommended for Chloe Eau de Parfum:
 1. Caron - French Cancan - Eau de Parfum (Score: 0.77)
 2. Ormonde Jayne - Frangipani Eau de Parfum (Score: 0.76)
 3. Floris London - 1962 Eau de Parfum (Score: 0.74)
 4. Parfums MDCI - Rose de Siwa Eau de Parfum (Score: 0.73)
 5. PARFUMS DE NICOLAI - Rose Oud Eau de Parfum (Score: 0.73)

For score I used Cosine similarity
