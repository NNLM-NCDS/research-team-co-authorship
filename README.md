# research-team-co-authorship
Searches in PubMed and retrieves co-authored articles via the Entrez Programming Utilities

# Project Description
This Python script searches PubMed for co-authored articles and fetches those citations via the Entrez Programming Utilities (E-Utilities) API provided by National Library of Medicine. The script takes a list of author names (in a CSV file) and creates queries of co-authorship between authors of that list, including variations of author name (e.g., J Smith,  Jacob Smith) and unique author combinations (e.g., Jacob Smith AND Andrey Smith, Andrey Smith AND Henry Williams). Using the list of author names as an input, the script develops one Boolean search string (representing all of the possible author combinations) that it then feeds to E-Utilities to perform the search and to retrieve the results. The results are provided in a CSV file containing article citations that include any articles in PubMed that were co-authored by at least two authors on the input list. 

# How to Install and Run the Project
The script is shared here as a Python Notebook file (.ipynb) that is optimized for use in Google Colaboratory (but can also be used in Jupyter Notebook). Google Colab has an import feature that includes GitHub as an option:
[https://colab.research.google.com/](https://colab.research.google.com/)

When you visit that URL, you should see a prompt to open or connect or upload a notebook. Use the GitHub tab, and paste the URL of this GitHub repository to import the code notebook: https://github.com/NNLM-NCDS/research-team-co-authorship/

![Screenshot 2024-05-13 at 2 30 35 PM](https://github.com/NNLM-NCDS/research-team-co-authorship/assets/23493464/12acd701-f2f8-42e4-9acb-bb7472d31251)

Then choose the *pubmed_coauthorship_search.ipynb* file to get started.

# How to Use the Project
The script uses the [metapub](https://github.com/metapub/metapub) Python library and the Entrez module from the [Bio](https://biopython.org/docs/1.75/api/Bio.Entrez.html) python library. These are not typically available on Google Colaboratory, so the script includes an installation of them on your runtime instance.

**First, open the notebook:** If you followed the steps above, you should now have the code notebook open in Google Colaboratory. Otherwise, search for or navigate to the notebook file (`pubmed_coauthorshop_search.ipynb`) in your Google Colaboratory files: https://colab.research.google.com/. Then double click on the notebook file to open it in Google Colab.

**Second, upload your CSV input data file:** See the "Example with sample data" section below to note how to format your CSV input data file. We recommend uploading your CSV file to your Google Drive, since our code mounts your Google Drive folders to interact with them. If you take this approach, you will need to first upload your file, then change one line of code in the script to point to your file. 

Change the file path inside the quotes in this line of code to the location of your CSV in your Google Drive: `df = pd.read_csv('/content/drive/MyDrive/path-to-your-file.csv', skipinitialspace=True)`

The default storage path to reach Google Drive from Google Colab is `'/content/drive/MyDrive/'` which points to your home directory in Google Drive. So, for example, if you happen to have your data-input.csv file in a folder named Data in your home directory, then your new path for the code would be `'/content/drive/MyDrive/Data/data-input.csv'`

Alternatively, you can upload your CSV file to your temporary runtime storage space. This is not recommended since all files in your temporary space will be deleted when you close Google Colab. But to do this, you can click on the `Files` icon in the left sidebar, and then click on `Upload` and select the CSV file (`filename.csv`) from your local machine. (See screenshot below.)
  
![Screenshot 2024-05-15 at 4 03 01 PM](https://github.com/NNLM-NCDS/research-team-co-authorship/assets/23493464/32874d44-ecbe-467c-b828-31cd4b987173)

After it is uploaded, hover on your file in the sidebar and use the three dots menu next to it to "Copy path" on your file, then insert that path into the code line referenced above.

**Third, run all cells in the notebook:** Run all cells in the code by clicking on the `Runtime` menu and then `Run all`. The script will run and prompt you to connect to your Google Drive.

The output file will be saved as 'article_info.csv' in your Google Colab space, and the last line of code will download the file to your machine. 

The code will also print out the Boolean search string used for your query; if needed, you can copy that information from the output of the `print(result)` line of code. (It may be good to see how the query came out, or to save it for future reference. That query can be used directly in the PubMed web searching interface to get the same results that the code provides.)

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

# Credits

This script was inspired by, and borrowed heavily from, https://github.com/erilu/pubmed-abstract-compiler

This work was made possible through the Network of the National Library of Medicine's National Center for Data Services, has been funded with Federal funds from the National Library of Medicine, National Institutes of Health, and Department of Health and Human Services, under Cooperative Agreement Number UG4LM012347 with NYU Langone Health. The content is solely the responsibility of the authors and does not necessarily represent the official views of NIH.

The NNLM National Center for Data Services held a class, the Fundamentals of Health Data Science (Fall 2023), that brought together the following project contributers who were interested in working on Python projects to solve information challenges in our workplace: 

**Project management:** Justin de la Cruz, Beth Blackwood
 
**Code development:** Brett Porter, Justin de la Cruz
 
**GitHub documentation:** Cheryl Thompson, Brett Porter, Justin de la Cruz, Beth Blackwood
 
**Administrative support:** Katy Smith, Sunny Chung
 
**Additional thanks to:** Joshua Kearney (for the Boolean structure), Angeleen Neely-Sardon, David Farris, Linda Hartman, Lisa Connor, Mego Franks, Ahlam Saleh, Breck Turner, Kathryn Mlsna, and Doug Dechow

# How to Contribute to the Project
You could create and share a version of this script that doesn't require Google Colab (so folks can run it locally on their computers), and accompanying documentation.

This script is narrow in scope: it works on finding co-authored publications in PubMed for a list of author names and retrieving those citations in a CSV format. Due to limitations on the number of characters that can be used in URLs and in PubMed searching, this script may break with more than 19 authors, or even with authors who have multiple aliases. (It broke in testing when we had too many search facets, which is partially why we omitted author institutional affiliation from the search.) You could contribute to this project by finding a way to restructure the code to work around that limitation.

This script works with the E-Utilities [eSummary](https://www.ncbi.nlm.nih.gov/books/NBK25499/#_chapter4_ESummary_) data, which is sometimes incomplete or missing. You could restructure this code to work with the E-Utilities [eFetch](https://www.ncbi.nlm.nih.gov/books/NBK25499/#_chapter4_EFetch_) data, which is more robust (it includes abstracts, for example).

This script retrieves all results in one batch. You could restructure to assist with anyone needing to retrieve very large batches of citations by implementing time-delayed requests.

# Extra pointers/notes/comments
* This code requires an input CSV file of author names to work. If you don't have one, or don't know how to format it, you can use our [sample CSV file](https://github.com/NNLM-NCDS/research-team-co-authorship/blob/main/sample-author-list.csv) for reference and to test the script.
* You should only list one value in each cell of your data input file (FirstName, MI, etc.) *except* the Publishes As column, which can take multiple values, separated by semicolons.
* An NCBI key is not required to execute the code. If you have a large number of search queries, utilizing the NCBI key will enable you to issue a larger number of queries per minute to the PubMed APIs. Here is more information on obtaining an NCBI key: https://support.nlm.nih.gov/knowledgebase/article/KA-05317/en-us
* This script draws from the eSummary information provided by MEDLINE PlUS / PubMed. It may be incomplete or missing for some of your results. If it is, you should still be able to find the PubMed ID in your output file, and search for that PMID via [PubMed](https://pubmed.ncbi.nlm.nih.gov/) directly to retrieve the info you need.
* You can manually inspect the eSummary XML file information on a given PMID by using the following URL construction: https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=pubmed&id=11850928 (and you can view multiple PMIDs at a time by adding a comma after the URL and adding your PMIDs to the URL, example: [...?db=pubmed&id=11850928,11482001](https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=pubmed&id=11850928)
* Simiarly, you can inspect the eFetch XML file information on a PMID by switching "esummary" to "efetch" in that same URL construction: https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=pubmed&id=11850928
