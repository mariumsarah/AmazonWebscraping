# Environmental Impact of Online Products

The focus of this project is to estimate the level of plastic content in Amazon products and analyze the carbon footprint of the products and at-scale-businesses selling on Amazon.
<br/>

Knowing that majority of the plastic thrown away in recycle bins ends up in landfill, over 78% customers (surveyed by GreenPrint) hope to find eco-friendly products however they have a difficult time identifying them. This project will help customers compare similar products based on their plastic content and the manufacturing brand’s environmental impact.
### **The paper titled "Environmental Impact of Online Products" is available here [click here](https://github.com/mariumsarah/PlasticDetectionOnlineProducts/blob/main/docs/EnvironmentalImactofOnlineProducts.docx)** ###

<br/>

## Installation
Make sure you have [Python 3](https://www.python.org/downloads/) installed, then install [Tensorflow](https://www.tensorflow.org/install/) on your system, and clone this repo.

Make sure to install ``beautifulSoup`` to run 1_WebScrapingAmazon.py to scrape Product information from python. Copy the following command to install ``beautifulsoup``
```Python
pip install bs4
```

```Python
pip install lxml
```

<br/>

## Execution Workflow
The inner workings of the program from input to output is highlighted here
<br/>
<img src="https://github.com/mariumsarah/PlasticDetectionOnlineProducts/blob/main/docs/workflow.png" width="600" height="auto" alt="image-detection icon"/>


## Usage

Our team, Anti Plasti used to detect images of plastics, garbage, metal, paper, glass and cardboard in the ocean to allow for the collection and reduction of these materials, particularly plastic, in the ocean waters.

### Web Scraping of Amazon Products

### Prepare the image data sets
In order to start the transfer learning process, a folder named ``training_dataset`` needs to be created in the root of the project folder. This folder will contain the image data sets for all the subjects, for whom the classification is to be performed.

[Download the Datasets here](https://bit.ly/3mcb3aS)

Create the ``training_dataset`` folder and add the images for all the data sets in the following manner -

```javascript
/
|
|
---- /training_dataset
|    |
|    |
|    ---- /plastics
|    |    plastic1.jpg
|    |    plastic2.jpg
|    |    ...
|    |
|    |
|    ---- /paper
|         paper1.jpg
|         paper2.jpg
|         ...
|
|
```
This enables classification of images between the ``plastics`` and ``paper`` data sets.

> Make sure to include multiple variants of the subject (side profiles, zoomed in images etc.), the more the images, the better is the result.

### Initiate transfer learning
Go to the project directory and run -

```javascript
$ bash train.sh
```
This script installs the ``Inception`` model and initiates the re-training process for the specified image data sets.

Once the process is complete, it will return a training accuracy somewhere between ``85% - 100%``.

The ``training summaries``, ``retrained graphs`` and ``retrained labels`` will be saved in a folder named ``tf_files``.

### Classify objects

```javascript
python classify.py
```

This opens up the file dialog using which you can select your input file.

<img src="https://i.imgur.com/LPXrKe8.png">

Once the input file is selected, the classifier will output the predictions for each data set. A prediction score between ``0.8`` to ``1`` is considered to be optimal.

<img src="https://i.imgur.com/zuFXTRb.jpg">

<br/>

<br/>

## Contributors

| [<img src="https://avatars3.githubusercontent.com/u/4924614" width="100px;"/><br /><sub><b>Arun Michael Dsouza</b></sub>](https://github.com/ArunMichaelDsouza)<br />| [<img src="https://avatars3.githubusercontent.com/u/11679543" width="100px;"/><br /><sub><b>Royal Bhati</b></sub>](https://github.com/royalbhati)<br />|
| :---: | :---: |


[Many thanks for the Dataset which was obtained from this Git project](https://github.com/garythung/trashnet)

<br/>

## License
MIT License

Copyright (c) 2017 Arun Michael Dsouza

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

### **The inner workings of the program from input to output is highlighted here** ###
<img src="https://github.com/mariumsarah/PlasticProductDetection/docs/worflow.png" width="250" height="auto" alt="image-detection icon"/>
- Dataset of trash objects for waste classification and detection.

## **The TrashBox dataset is presented and published in 31st IEEE FRUCT Conference hosted by University of Helsinki (Finland) [click here](https://fruct.org/program31)** ##
### **Furthur details of the dataset is available at Proceedings of the FRUCT'31 website [link](https://fruct.org/publications/fruct31/).** ###

A generic image detection program that uses Google's Machine Learning library, [Tensorflow](https://www.tensorflow.org/) and a pre-trained Deep Learning Convolutional Neural Network model called [Inception](https://research.googleblog.com/2016/03/train-your-own-image-classifier-with.html).

This model has been pre-trained for the [ImageNet](http://image-net.org/) Large Visual Recognition Challenge using the data from 2012, and it can differentiate between 1,000 different classes, like Dalmatian, dishwasher etc.
The program applies Transfer Learning to this existing model and re-trains it to classify a new set of images.

This is a generic setup and can be used to classify almost any kind of image. I created a small demo that classifies two image data sets - my photos and my girlfriend's photos, and returns a prediction score denoting the possibility of it being my image or my girlfriend's image.

- Contains 17785 waste object images divided into seven classes (glass, plastic, metal, e-waste, cardboard, paper, medical waste).

- Each class is furthur divided into its subclasses as follows:

1. Medical waste : Syringes, Surgical Gloves, Surgical Masks, Medicines( Drugs and Pills)   [Number of images: 2010]
2. E-Waste : Electronic chips, Laptops and Smartphones, Applicances, Electric wires, cords and cables   [Number of images: 2883]
3. Plastic : Bags, Bottles, Containers, Cups, Cigarette Butts (which have a plastic filter)  [Number of images: 2669]
4. Paper : Tetra Pak, News Papers, Paper Cups, Paper Tissues  [Number of images: 2695]
5. Metal : Beverage Cans, Cnostruction Scrap, Spray Cans, Food Grade Cans, Other metal objects. [Number of images: 2586]
6. Glass [Number of images: 2528]
7. Cardboard [Number of images: 2414]

## **NOTE: The testing and validation data is available [here](https://github.com/nikhilvenkatkumsetty/TrashBox-testandvalid)** ##
