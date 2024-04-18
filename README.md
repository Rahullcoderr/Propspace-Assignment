# Propspace-Assignment
The problem statement given here was an unsupervised model as labels were not given. 
## Preprocessing:
After discovering the data I came to know that the sizes of images were different and some of the images cant be used to train our model as it was completely white which meant they were covered by clouds during taking pics through satellite. In some pics they were partially white thourugh which we can actually predict the output by seeing but the white colour was more. I used PILLOW module to preprocess the data as all were TIF images and normal methods didnt work. I scaled down the image to 64*64 so that preprocessing could be done. When the size was 128*128 preprocessing resulted in an error as my laptop capacity was less. THen I normalised the image. I loaded all into a dataset for further processing.
## Clustering
As it didnt have any labels we have to cluster the images into 4 classes which should probably cluster into groups out of which one should contain lush crops other growing, another as no crop and last as bad images which would probably have clouds. Firstly I used normal K clusteirng and separated the images into batches for doing K clustering as the dataset was huge and my laptop didnt have the capacity to cluster all in one go. So I separated into 20 subsets and clustered all of these. Then I joined the images based on the label so that all lush came into one group, similarly for all. ( But finally I faced a problem because of that which I found out only the next day ). So now I have images in under labels in which one is lush, one is growing, one is no crop and the other is cloudy.
## CNN
Now I used CNN for image classification using three labels and removing the images under the label cloudy. Using pretrained model for CNN was another idea but I didnt try it because our data is very different from normal images so pretrained model cant classify it like the one especially made for this( I didnt try it just an idea ). My accuracy score after CNN classification was poor only nearly 30 percent. The actual mistake was in clustering due to subsets. Problem was like if in subset 1 Lush crops were under label 0 in another cluster lush crops were under label 2. So when I segregated based on label again it got randomized. If I segregate properly my model would give better results.

## Alternate Solution
Another solution is to use a pretrained model on this and use the weights of last layer for clustering. I could have used PCA for extracting the main features and to visulize the clusters we obtained.
I had another idea for K clustering to use the maximum colour in the image for clustering as while seeing the data we can tell colour maximums are present in every image and if both green and brown are present it is in growing stage.

## Problem
My trained model which is submitted is not fully as I lost my code due to memory leak but at last I have tested my model by uploading a single image and checking the prediction. THats the only proof I have to tell I have done the model and due to quiz and lab endsems I couldnt spend more time on this. I have actually learnt a lot in short time and I am really passionate about this and I want to continue this. I can learn things quickly and will learn more advanced stuff soon. 

## New File Q3
I have uploaded this file on 18th after trying a new method. I used pre trained model on the data and used the weights of last hidden layer to cluster the images. Then I used the clustered images for image classification. The accuracy came 85 percent. The classification worked well but the problem here was still image clustering didnt occur on basis of lush, empty. 

## New File Manual
I have done manual splitting of data into three classes based on month and if I use this for classification, even using simple cnn I am getting 80 percent accuracy for training. If I use powerfull CNN then accuracy more than 90 can be achieved.
