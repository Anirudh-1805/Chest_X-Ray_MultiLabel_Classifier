# Chest_X-Ray_MultiLabel_Classifier

I built a multi‑label chest X‑ray classifier that can detect five common thoracic pathologies. To get there, I:

1. **Prepared the Data**  
   I loaded real NIH chest X‑ray images and their labels, then carefully split them into training, validation, and test sets—making sure no patient appears in more than one split to avoid data leakage.

2. **Handled Class Imbalance**  
   Some diseases are much rarer than others, so I computed class frequencies and derived per‑class weights. I integrated those weights into a custom loss function so that the model pays appropriate attention to under‑represented conditions.

3. **Fine‑Tuned DenseNet121**  
   Using Keras’s pre‑trained DenseNet121 as a backbone, I replaced its top layer to output five probabilities. I froze most of the convolutional layers at first, then gradually unfroze and fine‑tuned the entire network to adapt it to medical images.

4. **Evaluated with ROC & AUC**  
   After training, I plotted ROC curves for each pathology and calculated the AUC to quantify how well the model separates positive from negative cases.

5. **Visualized with Grad‑CAM**  
   To peek inside the “black box,” I implemented Grad‑CAM heatmaps that show which regions of an X‑ray the model focuses on when predicting each disease.

---

**P.S.**
The code files in this repository were developed as part of the AI for Medical Diagnosis course on Coursera. All work was implemented and tested using the course’s provided backend environment.

