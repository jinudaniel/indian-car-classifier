# Indian Car Classifier  
Car Classifier for popular indian cars using fastai and pytorch

### Getting the data
Inorder to get the data, I have used a tool named `google_images_download`. You can pip install this tool by running the command `$ pip install google_images_download`  
Once it is installed, run the below commands. I have a weak internet connection so I have divided the command into 4 different parts
but you can install all the images in one go.  
```
googleimagesdownload --limit 100 --keywords "Maruti Swift, Maruti Suzuki Baleno, Maruti Wagon R, Maruti Vitara Breeza" --format jpg -o "C:\Images"

googleimagesdownload --limit 100 --keywords "Hyundai Creta, Mahindra Scorpio, Hyundai Elite i20, Maruti Dzire" --format jpg -o "C:\Images"

googleimagesdownload --limit 100 --keywords "Renault Kwid, Toyota Fortuner, Toyota Innova, Maruti Ertiga" --format jpg -o "C:\Images"

googleimagesdownload --limit 100 --keywords "Mahindra Bolero, Hyundai Grand i10, Honda Amaze, Hyundai Verna, Honda City" --format jpg -o "C:\Images"

googleimagesdownload --limit 100 --keywords "Maruti Celerio, Ford Ecosport, Maruti Ciaz" --format jpg -o "C:\Images"
```
This will download 100 images for each category. Once all the images are downloaded, you can manually look at the images for each category
and delete the images that you think does not belong to that category. After deleting some images which I did not think belonged to that
category, I was able to narrow down the number of images to approximately 85-90 images per category which I think is sufficient to train
a CNN with reasonable accuracy.

### Training
I have trained this classifier using a technique named Transfer Learning with resnet34 and resnet50 architecture. Since training a deep
neural network is computationally expensive, I would recommend training it on a GPU machine preferably from one of the cloud providers.  
I have trained the model in a GCP instance with Nividia P4 GPU.
