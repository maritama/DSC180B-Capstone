### Background

The purpose of phrase mining is to extract high-quality phrases from a large amount of text corpus. It identifies the phrases instead of an unigram word, which provides a much more understanding of the text.  In this study, we apply AutoPhrase method into two different datasets and compare the decreasing quality ranked list of phrase ranked list in multi-words and single word. Our datasets are from the abstract of Scientific papers in English with the English knowledge base from Wikipedia. Through this project, we will be able to understand the advantages of the AutoPhrase method and how to implement Autophrase in two datasets by identifying different outcomes it produces. 


### Requirements
##### If you run in the local:
Linux or MacOS with g++, Java and gensim installed.


##### You can also use our docker images to run the code. No need any install. It stores in submission.json file.


### Purpose of the Code

For Final Replication, our code would do the data ingestion proportion first, to pull data as the input corpus for future use from the cloud. Then to perform some basic EDA on it. We would run the autophrase algorithm along with phrasal segmentation, analyzing the results. At the end, we manually label the high-quality phrases and select 3 phrases and put those into the phrase embedding model to return five most silimiar phrase as the result.

### Code Content
Some Python Scripts, involved in etl.py, eda.py, auto.py,visual.py, and example.py to download, process data, analyze, visualize data and find the most similar phrase by building the model.

	
### How to Run the Code

To get the data:     -      run python run.py etl


This downloads the data from Illinois University in the directory specified in config/etl-params.json and do data cleaning process. You can find the result




To do the eda for the data     -       run python run.py eda


This performs exploratory data analysis and saves the figures in the location specified in config/eda-params.json.


To run autophrase algorithm and get the segementation result.     -        run python run.py auto



This performs autophrase algorithm and phrasal segmentation saves the results in the location specified in config/auto-params.json.


To analyze the output of autophrase           -         run python run.py visual


This performs analysis on the results and saves the figures in the location specified in config/visual-params.json.


To find the most 5 similar phrases           -         run python run.py example


This ask the users to manually label the high-quality phrase. It builds the word2vec model on the phrasal segmentation results to obtain phrase embedding based on random sampleing. It also report the top-5 similar phrases based on the 3 high-quality phrases from your previous annotations.However, if the users want to try their own sampling, they can manually label the high-quality phrases in sample.txt, which stored the output file by changing the configuration. 


To run whole project       -          run python run.py all

It will complete the whole process with results.


To make a test run.          -        run python run.py test

It will implement dataset DBLP.5k.txt, which is a test data to check the whole process is working. DBLP.5k.txt is sampled from the original dataset DBLP.txt. However, in this test run, it will not generate the last steps, because the phrase embedding building is not build for the test dataset, becaused it has less than 100 phrases to train.



### Reference

In the folder data/folder/example, we stored a file called sample_example.txt. It randomly samples 100 multi-phrases after computing the result from AutoPhrase and we manually label the high-quality phrases. In the run.py all or run.py example, we apply that file in it, but if the users want to try their own sampling, they can change the configuration and add the column of label in the file to apply it.


### Work Cited

Professor Jingbo Shang’s Github: https://github.com/shangjingbo1226/AutoPhrase
Jingbo Shang, Jialu Liu, Meng Jiang, Xiang Ren, Clare R Voss, Jiawei Han, "Automated Phrase Mining from Massive Text Corpora", accepted by IEEE Transactions on Knowledge and Data Engineering, Feb. 2018.

### Responsibilities
We discussed the general idea of the replication project and outlined the steps of the process together.
Tiange Wan: some of code portion and report portion, and revised the report portion.
Yicen Ma: some of code portion and report portion, and revised the code portion.





