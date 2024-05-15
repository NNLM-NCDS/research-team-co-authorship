# research-team-co-authorship
Searches in PubMed and retrieves co-authored articles via the Entrez Programming Utilities

# Project Description
This Python script fetches articles with citation information from PubMed via the Entrez Programming Utilities provided by National Libraries of Medicine. It takes a list of authors (csv file) and creates potential queries of co-authorship between authors including variations of author name (e.g., J Smith,  Jacob Smith) and unique author combinations (Jacob Smith and Andrey Smith, Andrey Smith and Henry Williams). Using these search queries, the script calls the PubMed API to perform the search for each query and retrieves the results. The results are downloaded in a csv file. 

An NCBI key is not required to execute the code. If you have a large number of search queries, utilizing the NCBI key will enable you to issue a larger number of queries per minute to the PubMed APIs. Here is more information on obtaining an NCBI key: https://support.nlm.nih.gov/knowledgebase/article/KA-05317/en-us

# How to Install and Run the Project
Google Colaboratory has an import feature that includes GitHub as an option:
[https://colab.research.google.com/](https://colab.research.google.com/)

When you visit that URL, you should see a prompt to open or connect or upload a notebook. Use the GitHub tab, and paste the URL of this GitHub repository to import the code notebook: https://github.com/NNLM-NCDS/research-team-co-authorship/

![Screenshot 2024-05-13 at 2 30 35 PM](https://github.com/NNLM-NCDS/research-team-co-authorship/assets/23493464/12acd701-f2f8-42e4-9acb-bb7472d31251)

Then choose the *pubmed_coauthorship_search.ipynb* to get started.

### Running the Project:
1. **Open the notebook**:
   - If you followed the steps above, you should now have the code notebook open in Google Colaboratory. Otherwise, search for or navigate to the notebook file (`pubmed_coauthorshop_search.ipynb`) in your Google Colaboratory files: https://colab.research.google.com/. Then double click on the notebook file to open it in Google Colab.
2. **Upload the CSV file**:
   - This code requires an input CSV file to work. See below for an example on how to structure your file. Make sure you have your CSV file available on your local machine. (Or you can use our [sample CSV file](https://github.com/NNLM-NCDS/research-team-co-authorship/blob/main/sample-author-list.csv) to test the script.) 
   - In Google Colab, click on the `Files` icon in the left sidebar.
   - Click on `Upload` and select the CSV file (`filename.csv`) from your local machine. (See screenshot below.)
  
![Screenshot 2024-05-15 at 4 03 01 PM](https://github.com/NNLM-NCDS/research-team-co-authorship/assets/23493464/32874d44-ecbe-467c-b828-31cd4b987173)

3. **Connect to a runtime**:
   - Click on `Runtime` > `Change runtime type`.
   - Select `GPU` as the hardware accelerator (optional, if your project requires GPU).
4. **Run the cells**:
   - Click on `Runtime` > `Run all`.
   - Follow the prompts in the notebook, if any.

# How to Use the Project
The script uses the [metapub](https://github.com/metapub/metapub) Python library and the Entrez module from the [Bio](https://biopython.org/docs/1.75/api/Bio.Entrez.html) python library. These are not typically available on Google Colaboratory, so the script includes an installation of them on your runtime instance.

To run this code, you will need to do the following in Google Colab, with the notebook open:
1. Ensure that your input data CSV file is correctly formatted (see "Example with sample data" below).
2. Save your input CSV data file in your Google Drive.
3. Mount your Google Drive to connect your input CSV file. (This step is included in the code and will prompt a pop-up box that will walk you through the process.)
4. Change the file path inside the quotes in this line of code to the location of your CSV in your Google Drive: df = pd.read_csv('**/content/drive/MyDrive/path-to-your-file.csv**', skipinitialspace=True)
5. Run all cells in the code: Click on `Runtime` > `Run all`.
6. The output file will be saved as 'article_info.cvs' in your Google Colab space.
7. Download this file to your computer. 

# Example with sample data
This script takes as input a CSV file with the following column names:
* **FirstName** -  The first name of the author.
* **MI** - The middle initial of the author, if used/available.
* **LastName** - The last name of the author.
* **Publishes As** - Other known names the author has published under, in full, including maiden names, aliases, and suffixes (Jr, Sr, III, etc.). You can include multiple "Publishes As" names, separated by semicolons (;).
* **OrcID** - The author's OrcID, if available (note the capitalization used here).

This is [our sample CSV file](https://github.com/NNLM-NCDS/research-team-co-authorship/blob/main/sample-author-list.csv) following the correct format:

![Screenshot 2024-05-13 at 2 40 06 PM](https://github.com/NNLM-NCDS/research-team-co-authorship/assets/23493464/62294f5a-55bb-4560-bcea-df241385766b)

The output of the code with this sample file is available on this repo at: https://github.com/NNLM-NCDS/research-team-co-authorship/blob/main/article_info.csv

# License
This project utilizes the **MIT License**, a permissive software license with few restrictions of reuse. You can do whatever you want as long as you *include 1) the original copyright and 2) copy of the license notice* in any copies or derivations of this software project. You can *use, copy, modify, merge, publish, distribute, sublicense, and sell copies* of this software. Read the **MIT license** for additional information: https://github.com/NNLM-NCDS/research-team-co-authorship?tab=MIT-1-ov-file.

# Credit 

The NNLM National Center for Data Services (NCDS) held a class, the Fundamentals of Health Data Science(Fall 2023), that brought together the following professionals interested in working on Python projects to solve information challenges in our workplace: 

**Project management:** Justin de la Cruz, Beth Blackwood
 
**Code development:** Brett Porter, Justin de la Cruz
 
**GitHub documentation:** Cheryl Thompson, Brett Porter, Justin de la Cruz, Beth Blackwood
 
**Administrative support:** Katy Smith, Sunny Chung
 
**Additional thanks to:** Angeleen Neely-Sardon, David Farris, Linda Hartman, Lisa Connor, Mego Franks, Ahlam Saleh, Breck Turner, Kathryn Mlsna, and Doug Dechow

# How to Contribute to the Project

# Extra pointers/notes/comments
