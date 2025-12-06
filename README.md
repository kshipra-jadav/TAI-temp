# Order In Which These Notebooks Have To Be Run

1. `dataset_exploration.ipynb` $\rightarrow$ This notebook will download all the necessary data and generate the annotated `json` for `train`, `val` and `test`
2. `baseline_model.ipynb` $\rightarrow$ This notebook will take the data which is generated in earlier step and will train the `Resnet50` model on that on just the `train` and `val` set. Finally, it will also report model and dataset leakage metrics for basline model
3. `debiasing@conv5.ipynb` $\rightarrow$ This notebook will train `Resnet50` Model on the Debiased Resnet 50 with the `adv@conv5` type debiasing. Additionally, it will also report model and dataset leakage for the debiased model.
4. `debiasing@conv4.ipynb` $\rightarrow$ This notebook will train `Resnet50` Model on Debiased Resnet 50 with the `adv@conv4` type debiasing. Additionally, it will also report model and dataset leakage for the debiased model.

> Optional: `upload_files.ipynb` $\rightarrow$ Used to upload the trained model to an external API so that it can be useful later.


## ResNet 50 Results

| Model | Dataset Leakage ($\lambda_D$) | Model Leakage ($\lambda_M$) | Bias Amplification ($\Delta$) |
| :--- | :---: | :---: | :---: |
| **Baseline** | 68.18% | 73.78% | 5.60% |
| **adv@conv4** | 68.09% | 67.58% | -0.52% |
| **adv@conv5** | 68.21% | 65.35% | -2.86% |

## VGG 16 Results
| Model | Dataset Leakage ($\lambda_D$) | Model Leakage ($\lambda_M$) | Bias Amplification ($\Delta$) |
| :--- | :---: | :---: | :---: |
| **Baseline** | 68.24% | 71.22% | 2.99% |
| **adv@conv4** | 68.24% | 64.14% | -4.09% |
| **adv@conv5** | 68.24% | 64.10% | -4.14% |