# Brain Tumor Segmentation using Unet

## About Data 
Brain Tumor Segmentation Challenge 2018 (BraTS) Data.


### Data Description BRATS
BraTS 2018 is a dataset which provides multimodal 3D brain MRIs and ground truth brain tumor segmentations annotated by physicians, consisting of 4 MRI modalities per case (T1, T1c, T2, and FLAIR). Annotations include 3 tumor subregions—the enhancing tumor, the peritumoral edema, and the necrotic and non-enhancing tumor core. The annotations were combined into 3 nested subregions—whole tumor (WT), tumor core (TC), and enhancing tumor (ET). The data were collected from 19 institutions, using various MRI scanners
  

### Task
Segmentation of gliomas in pre-operative MRI scans. 


### Dice Coefficient & Dice Coefficient Loss Function

  ```
  def dice_coef(y_true, y_pred, epsilon=1e-6):
      intersection = K.sum(K.abs(y_true * y_pred), axis=-1)
      return (2. * intersection) / (K.sum(K.square(y_true),axis=-1) + K.sum(K.square(y_pred),axis=-1) + epsilon)
  ```
  ```
  
  def dice_coef_loss(y_true, y_pred):
      return 1-dice_coef(y_true, y_pred)
  ```
## Results Obtained
- HGG Result Samples

   ![](https://github.com/Purav0788/Unet_Brain_tumour_segmentation/blob/72ff0688fc223ca6622b16f491ceac1d6b468dc2/Samples/HGG-1.png)
   ![](https://github.com/Purav0788/Unet_Brain_tumour_segmentation/blob/72ff0688fc223ca6622b16f491ceac1d6b468dc2/Samples/HGG-2.png)
   ![](https://github.com/Purav0788/Unet_Brain_tumour_segmentation/blob/72ff0688fc223ca6622b16f491ceac1d6b468dc2/Samples/HGG-3.png)
   
- LGG Result Samples

  ![](https://github.com/Purav0788/Unet_Brain_tumour_segmentation/blob/72ff0688fc223ca6622b16f491ceac1d6b468dc2/Samples/LGG-1.png)
  ![](https://github.com/Purav0788/Unet_Brain_tumour_segmentation/blob/72ff0688fc223ca6622b16f491ceac1d6b468dc2/Samples/LGG-2.png)
  
## Metrics
| Test Data|Dice Coefficient| 
|-------------|:-------------:| 
| HGG Set-1   |   0.9234   |
| HGG Set-2   |   0.9189   |
| HGG Set-3   |   0.9376   |
| LGG         |   0.9287   |
