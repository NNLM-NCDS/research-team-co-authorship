# research-team-co-authorship
Searches in PubMed and retrieves co-authored articles via the Entrez Programming Utilities

# Project Description
This Python script fetches articles with citation information from PubMed via the Entrez Programming Utilities provided by National Libraries of Medicine. It takes a list of authors (csv file) and creates potential queries of co-authorship between authors including variations of author name (e.g., J Smith,  Jacob Smith) and unique author combinations (Jacob Smith and Andrey Smith, Andrey Smith and Henry Williams). Using these search queries, the script calls the PubMed API to perform the search for each query and retrieves the results. The results are downloaded in a csv file. 

An NCBI key is not required to execute the code. If you have a large number of search queries, utilizing the NCBI key will enable you to issue a larger number of queries per minute to the PubMed APIs. 

# How to Install and Run the Project
Google Colaboratory has an import feature that includes GitHub as an option:
[https://colab.research.google.com/](https://colab.research.google.com/)

Right after we make this public, add a new screenshot showing it as an option in the dropdown menu (Google only allows imports of public repos):
![Screenshot 2024-04-15 at 9 52 49 AM](https://github.com/NNLM-NCDS/research-team-co-authorship/assets/23493464/eceda56c-1d8a-44ed-9dba-fe6d49f47a7d)

Alternatively, I think I'd like to make a standalone version of the script that works locally (so people don't have to use Google Colab), and include those instructions here. -Justin
### Running the Project:
1. **Open the notebook**:
   - Navigate to the notebook file (`pubmed_coauthorshop_search.ipynb`) in the file explorer.
   - Double click on the notebook file to open it in Google Colab.
2. **Upload the CSV file**:
   - Make sure you have the CSV file (`sample-author-list.csv`) available on your local machine.
   - In Google Colab, click on the `Files` icon in the left sidebar.
   - Click on `Upload` and select the CSV file (`filename.csv`) from your local machine.
3. **Connect to a runtime**:
   - Click on `Runtime` > `Change runtime type`.
   - Select `GPU` as the hardware accelerator (optional, if your project requires GPU).
4. **Run the cells**:
   - Click on `Runtime` > `Run all`.
   - Follow the prompts in the notebook, if any.
# How to Use the Project


# Examples with sample data


# License
This project utilizes the **MIT License**, a permissive software license with few restrictions of reuse. You can do whatever you want as long as you *include 1) the original copyright and 2) copy of the license notice* in any copies or derivations of this software project. You can *use, copy, modify, merge, publish, distribute, sublicense, and sell copies* of this software. Read the **MIT license** for additional information: https://github.com/NNLM-NCDS/research-team-co-authorship?tab=MIT-1-ov-file.

# Credit 

The NNLM National Center for Data Services (NCDS) held a class, the Fundamentals of Health Data Science(Fall 2023), that brought together the following professionals interested in working on Python projects to solve information challenges in our workplace: 

Project management: Justin de la Cruz, Beth Blackwood
 
Code development: Brett Porter, Justin de la Cruz
 
GitHub documentation: Cheryl Thompson, Brett Porter, Justin de la Cruz, Beth Blackwood
 
Administrative support: Katy Smith, Sunny Chung
 
Additional thanks to: Angeleen Neely-Sardon, David Farris, Linda Hartman, Lisa Connor, Mego Franks, Ahlam Saleh, Breck Turner, Kathryn Mlsna, and Doug Dechow

# How to Contribute to the Project

# Extra pointers/notes/comments
