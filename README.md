# ML Challenge

## Short Description about the implementations
I have implemented two methods, one of which includes training a CNN network and the other using variation of laplacian.

### CNN implementation
In the first implementation, a resnet with 101 layered deep network was used on the training dataset. After running for 20 epochs the accuracy got saturated and was stopped because of the problem of overfitting. The accuracy of the training dataset came out to be 65.8% and the evaluation data showed an accuracy of 55.4%. There might be room of improvement in this but the training instance took a lot of time so I moved on to more image processing approach instead of deep learning.

### Variation of Laplacian
Thus in my second implementation, I used variation of Laplacian. A well focused image is expected to have a high variation in grey levels. Thus it will be identifiable by the contrast in variance for images which are not blurry and have clear edges. The limitation to this approach is probably if the image itself even though clear has really few edges, it has high probability of being classified as blurry. The accuracy of 87.57% was reached in this, and the reason for the ~13% loss is probably because of the reason discussed previously. The threshold was set to 435 as it was experimentally found to be suitable for our application.

One important thing to note here is, apart from the accuracy we also notice that the precision and recall of the model is also very high. With high precision we can safely say that the algorithm returns more relevant results than irrelevant ones, and with high recall we understand that the algorithm returns most of the relevant results.

## How to run it from your end
### For the CNN implementation (accuracy: 55.4%):
- Open Srivatsav_Raghu_55.ipynb
- Here I used Google Colab for training purposes, so if you are going to run from PC make sure to change the directories of the datasets.
- In the dataset, I have merged both Artifical and Natural blurred folders into one single folder named Blurred. So make the changes in your end too.
- In the zip file I have attached the checkpoint file which needs to be loaded (again make sure to put the right path for the checkpoint location).
- Once this is done you can run from the "Preprocessing data" and "Start testing from here" sections mentioned in the notebook.
- After few minutes you can see the training and testing accuracy in the last cell.

### For variation of laplacian implementation (accuracy: 87.57%)
- Open Srivatsav_Raghu_87.ipynb
- There is no model or a pickle file downloaded as it works on run time. Thus after opening the notebook make sure to change the directories appropriately and run the notebook.
- The accuracy, precision and recall will be displayed in the last cell.

## Possible things which could have been done
The concept of fast fourier transform could have been applied and followed by creating 5-bin histogram and then training the final vector with a SVM classifier. The related implementation was done on a paper named No-reference blur assessment in natural images using Fourier transform and spatial pyramids. In this paper they used advanced image processing concepts and partitioned image in 9 equal parts for better edge values. I got few hiccups while implementing this and would try to implement in near future.
