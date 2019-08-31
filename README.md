# web-scraper
This is python web scraper implemented using multithreading/multiprocessing/pool for amazon.com

## How to use:
#### For threading:
python3 scrape_amazon.py t
#### For processing:
python3 scrape_amazon.py p
#### For pool:
python3 scrape_amazon.py l


## Enhancements to be considered:
1. Instead of hardcoding "laptops" as labels, and number of pages, you can pass it as a list input from user and then iterate through all the labels in case you want data for multiple products.
2. Try for various other tags in the website and scrape various other product information.
3. In case of different labels like laptops, Televisions, mobile phones, since we are using multithreading, the data will be random while taking out from queue because any thread/process might have inserted to the queue at any time. Here comes the dataframe to the rescue; as it's very fast and easy to convert this dataframe to separate dataframes (and hence CSVs) based on label name.

## Important points to remember:
Don't use multiprocessing queue object as that will throw you an error in case of pool objects Always use Manager.Queue object as used above. Frankly, everywhere I have researched, I have got this as the only solution but why multiprocessing.Queue doesn't work, i still haven't been able to find an answer. I have raised the question in StackOverflow, but in vain.
https://stackoverflow.com/questions/57663041/why-multiprocessing-queue-doesnt-work-but-manger-queue-works-in-case-of-pas?noredirect=1#comment101778285_57663041
