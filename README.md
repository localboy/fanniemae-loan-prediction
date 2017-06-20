Fannie Mae Loan Prediction
-----------------------

Predict whether or not loans acquired by Fannie Mae will go into foreclosure.  Fannie Mae acquires loans from other lenders as a way of inducing them to lend more.  Fannie Mae releases data on the loans it has acquired and their performance afterwards [here](http://www.fanniemae.com/portal/funding-the-market/data/loan-performance-data.html).

Installation
----------------------

### Download the data

* Clone this repo to your computer.
* Goto project directory and run `mkdir data`.
* Switch into the `data` directory using `cd data`.
* Download the data files from Fannie Mae into the `data` directory.  
    * You can find the data [here](http://www.fanniemae.com/portal/funding-the-market/data/loan-performance-data.html).
    * You'll need to register with Fannie Mae to download the data.
    * It's recommended to download all the data from 2012 Q1 to present.
* Extract all of the `.zip` files you downloaded.
* Remove all the zip files by running `rm *.zip`.
* Go back into the project directory using `cd ..`.

### Install the requirements
 
* Install the requirements using `pip install -r requirements.txt`.

Runnig the project
-----------------------

* Run `mkdir processed` to create a directory for our processed datasets.
* Run `python assemble.py` to combine the `Acquisition` and `Performance` datasets.
    * This will create `Acquisition.txt` and `Performance.txt` in the `processed` folder.
* Run `python annotate.py`.
    * This will create training data from `Acquisition.txt` and `Performance.txt`.
    * It will add a file called `train.csv` to the `processed` folder.
* Run `python predict.py`.
    * This will run cross validation across the training set, and print the accuracy score.

To Do List
------------------------