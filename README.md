# 3D reconstruction of porous polymer membranes

# 1. Experiments with Synthetic Data

This project demonstrates the reconstruction of 3D target structures using a Bayesian optimization algorithm. The goal is to generate a set of synthetic 3D structures using a custom statistical generation method and then reconstruct these structures similar to synthetic data. The experiment compares the effectiveness of two different reconstruction methods:

1. **Reconstruction using all slices of the target structure**.
2. **Reconstruction using only 10 slices of the target structure**.

To validate the effectiveness of the reconstruction methods, both 2D and 3D porosity, as well as specific surface area, were used as metrics.

### Files

Since two different reconstruction methods were employed, the results are saved in four CSV files:

1. **`Synthetic Data 1-result_df.csv`**: Contains the reconstruction results using the first method (all slices).
2. **`Synthetic Data 1-evaluate.csv`**: Contains the validation results (porosity and specific surface area) for the first method.
3. **`Synthetic Data 2-result_df.csv`**: Contains the reconstruction results using the second method (10 slices).
4. **`Synthetic Data 2-evaluate.csv`**: Contains the validation results for the second method.

These files show the experimental results and the validation of these results using independent properties of the porous polymer membrane.



# 2. Experiments with Real Images

## 2.1 Image Loading and Preprocessing

We begin by loading the real images that will be used in the experiments. The first preprocessing step is applying Otsu's binarization method to convert the images into binary form. However, due to the presence of noise, additional denoising procedures are necessary. These procedures include removing white noise on black backgrounds and black noise on white backgrounds to ensure clean and accurate input data for the subsequent reconstruction process.

## 2.2 Bayesian Optimization for Reconstruction

The core of our reconstruction approach relies on Bayesian optimization. For each iteration, the Bayesian optimization generator creates a 3D structure. Each slice of this generated 3D structure undergoes a distance transform histogram comparison with the corresponding slice of the target data. The objective is to maximize a similarity score between the histograms of the generated and target slices.

The Bayesian optimization algorithm iteratively adjusts the parameters (specifically sigma and quantile) to maximize this score, guiding the generator toward the optimal parameter set that best reconstructs the target data.

## 2.3 Evaluation of Reconstruction Quality

Once the optimal parameter set and the corresponding reconstructed structure are obtained, the quality of the reconstruction is evaluated using porosity and specific surface area measurements. 

The optimal parameters found and the results of evaluating the generated quality will be stored in these two files respectively: *"Real data-results.csv"* and*"Real data-evaluate.csv"*



# 3. Visualization of the reconstruction results and input target images of Original SEM-2 (Fig _4b)

Due to insufficient memory, the3D visualization only selects a certain range of volume for display

### 3.1 Visualization of the original target image of SEM2 (Fig _4b(poi) ) and the first slice of its reconstructed structure

![image-20240826011506363](C:\Users\18375\AppData\Roaming\Typora\typora-user-images\image-20240826011506363.png)

### 3.2 Visualization using plotly

The results of reconstructing the original SEM-2 (Fig_4b) using plotly are as follows

![image-20240826014622165](C:\Users\18375\AppData\Roaming\Typora\typora-user-images\image-20240826014622165.png)

![image-20240826015253183](C:\Users\18375\AppData\Roaming\Typora\typora-user-images\image-20240826015253183.png)

## 3.3 Volume visualization with Mayavi

![image-20240826015525203](C:\Users\18375\AppData\Roaming\Typora\typora-user-images\image-20240826015525203.png)



# 4. Three groups of experimental results and evaluation of experimental results

In this document（"Three groups of experimental results and evaluation of experimental results"）, you can see the results of three sets of experiments, as well as the verification of the results using porosity and specific surface area.
