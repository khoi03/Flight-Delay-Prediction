# Flight-Delay-Prediction
<sub> [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ltSXkWcSd0PhbP-w-7Kc4x7ENixPJRva?usp=sharing)
</sub>

In this research, we have utilized a range of machine learning algorithms, such as Decision Tree (DT), Random Forest (RF), XGBoost (XGB), and K-nearest neighbors (KNN), in combination with data augmentation technique (ADASYN) and Bayesian Optimization to enhance prediction accuracy.
A majority of the processing part is modified from [Kaggle](https://www.kaggle.com/code/fabiendaniel/predicting-flight-delays-tutorial/notebook) and you can download the dataset from [Kaggle](https://www.kaggle.com/datasets/usdot/flight-delays?datasetId=810&sortBy=voteCount&select=airlines.csv).

## Distribution of classes
The prevalence of class 0 over class 1 in the dataset, indicating a significant imbalance in class distribution. Therefore, to ensure the accuracy of our model is not skewed by imbalances between class 1 and class 0, we implemented the ADASYN (Adaptive Synthetic) technique to augment our dataset. By employing ADASYN, we aim to create a more balanced and representative dataset that enables our model to make accurate predictions across both classes.

<table align="center">
    <tr>
        <td align="center"> <img src="https://github.com/khoi03/Flight-Delay-Prediction/assets/80579165/ba67e98d-a688-4216-9af7-16ed327aa8b5"></td>
    </tr> 
</table>

## Analyze experimental results

<table align="center">
    <tr>
        <td align="center"></td>
        <td align="center" colspan="4"> F1-Score</td>
    </tr> 
    <tr>
        <td align="center" rowspan="2"> Algorithm</td>
        <td align="center" colspan="2"> w.o ADASYN</td>
        <td align="center" colspan="2"> ADASYN</td>
    </tr> 
    <tr>
        <td align="center"> Normal</td>
        <td align="center"> Optimized</td>
        <td align="center"> Normal</td>
        <td align="center"> Optimized</td>
    </tr> 
    <tr>
        <td align="center"> KNN </td>
        <td align="center"> 0.65 </td>
        <td align="center"> 0.66 </td>
        <td align="center"> 0.71 </td>
        <td align="center"> 0.72 </td>
    </tr>
    <tr>
        <td align="center"> DT </td>
        <td align="center"> 0.55 </td>
        <td align="center"> 0.65 </td>
        <td align="center"> 0.59 </td>
        <td align="center"> 0.68 </td>
    </tr>
    <tr>
        <td align="center"> RF </td>
        <td align="center"> 0.51 </td>
        <td align="center"> 0.63 </td>
        <td align="center"> 0.64 </td>
        <td align="center"> 0.71 </td>
    </tr>
    <tr>
        <td align="center"> XGB </td>
        <td align="center"> 0.65 </td>
        <td align="center"> 0.66 </td>
        <td align="center"> 0.73 </td>
        <td align="center"> 0.75 </td>
    </tr>
</table>

It can be seen from the table above, after applying data augmentation technique (ADASYN) the results are significant improved at both normal and optimized state. With ADASYN, in the normal state, the algorithm with the highest F1-score is XGBoost (0.73), followed closely by KNN (0.71), RF (0.64), and DT (0.59). After applying optimization techniques to fine-tune the algorithms, noticeable improvements in the F1-scores were observed. XGBoost achieved the highest F1-score (0.75) in the optimized state, demonstrating the effectiveness of the optimization process. These results highlight the importance of a balanced dataset and algorithm optimization in enhancing model performance.

## Optimized time of each algorithm
![op_time](https://github.com/khoi03/Flight-Delay-Prediction/assets/80579165/252721cd-bf7e-4dff-ae37-6338a1d5fd0d)

The findings indicate that XGBoost necessitates a substantial tuning time, but it yields the highest performance. Contrary to other algorithms, Decision Tree demonstrates a shorter tuning time of just 1 minute. Despite this, it manages to achieve a substantial improvement in accuracy, nearly 10%. Therefore, it is crucial to consider the trade-off between tuning time and performance when selecting a machine learning algorithm.
