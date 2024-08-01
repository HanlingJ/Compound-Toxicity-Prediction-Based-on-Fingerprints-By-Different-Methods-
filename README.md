# Compound-Toxicity-Prediction-Based-on-Fingerprints-By-Different-Methods-
Using Random Forest algorithm and other deep learning models to predict the 12 toxicity features of compounds, with 12,509 retrieving SMILES strings and the ECFP features of compounds through PubChem and Tox21 dataset. Most of the prediction accuracy are higher than 95.0%.

Introduction:
The aim of our project is to predict the level of harm a particular molecule may inflict on human organs. The reasons for selecting this project are clear. High-precision predictive models for toxin-induced damage can prevent health hazards, decrease the expenses associated with medical research, and shorten the timeline for environmental and chemical safety evaluations\cite{lindon2003contemporary}. Identifying a substance as toxic before it becomes widespread can prevent the costly process of post-market control and containment and predictive models can determining the likelihood of a substance being hazardous before its widespread use.

Our project employed both traditional machine learning and deep learning models, trained on the TOX21 dataset (Toxicology in the 21st Century)\cite{richard2020tox21}. For traditional machine learning, we used a Random Forest classifier. For deep learning methods, we explored models with fully connected networks, progressive networks, robust networks, and Keras networks.

Dataset and data processing:
The TOX21 dataset comprises 12,708 compounds, each associated with 12 binary labels representing the outcomes (active/inactive) of various toxicological experiments. We successfully retrieved 12,509 SMILES strings through PubChem's API and then converted these SMILES strings into Extended-Connectivity Fingerprints (ECFP), which enabled the models to extract meaningful features from the compounds. As illustrated in Figure 1, the dataset contains many blank results for the toxicological experiments, so our models skip the blank results.

Methods:
We employed the Random Forest\cite{rigatti2017random} algorithm from scikit-learn to predict the toxicity of compounds based on their ECFP features. First, we created 12 CSV files, each corresponding to a specific toxicology test. For each test, we removed any data points with missing or blank results to ensure the data was clean. The molecular fingerprints generated from the SMILES strings were used as features, represented as fixed-length arrays that served as input for the model. The Random Forest classifier then processed these features to predict the toxicological experiment result of each compound for the given toxicology test.

Next, we trained deep learning models using ECFP as the feature representation, which consists of a single array of 1,024 elements. We experimented with four different models: a fully connected network, a progressive network, a robust network, and a Keras network to generate predictions for the task. The data was loaded using the DeepChem library\cite{Intro7}, which is specifically designed for machine learning and deep learning tasks in molecular chemistry. 

