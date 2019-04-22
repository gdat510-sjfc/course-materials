GDAT510 - Final Project
================
Chip Galusha
4/2/2019

-   [The Data Science Workflow: Final Project](#the-data-science-workflow-final-project)
    -   [Step 1: Propejct Propsal](#step-1-propejct-propsal)
    -   [Step 2: Folder Structure](#step-2-folder-structure)
    -   [Step 3: Data Aquisition & Preperation](#step-3-data-aquisition-preperation)
    -   [Step 4: Modeling](#step-4-modeling)
    -   [Step 5: Operationalization](#step-5-operationalization)
    -   [Step 6: Iterate](#step-6-iterate)
    -   [Presentation](#presentation)
    -   [Remember!](#remember)
    -   [Grading](#grading)

The Data Science Workflow: Final Project
----------------------------------------

**Purpose:** The goal of the final project is to develop a operational data science workflow in a domain of your choice. This will help broaden your understanding of data science by building each of the workflow components and designing them to work together.

#### Step 1: Propejct Propsal

Develop a project proposal in the suggested format. This can be saved as the README document you create when you initialize your final project proposal.

#### Step 2: Folder Structure

In the folder where your final R project is saved, create the following folders and sub-folders:
![](/assignments/github_screen_shots/folder_structure.png)

#### Step 3: Data Aquisition & Preperation

Create a markdown with *data\_prep\_historical* in the title. In could be just data\_prep\_historical.RMD or something like , using my example, zillow\_data\_prep\_historical.RMD and save it in the *code/dataPrep* folder.

This document will describe with words and execute code how you go about ingesting the raw data and what steps are required to process the data. This is commonly referred to as ETL or extract-transform-load. As the folder names imply, raw data (yet to be processed) should go in the *data/raw* folder and processed data should go in the *data/processed* folder.

Let's say you were using twitter data from the API (like we did in class). The data in it's raw format, as returned by the *get\_timeline* function, would be saved in the data/raw folder. If your pulling data across multiple days, you should appended the date of the pull to each file (e.g RejectTheNull\_twitter\_data\_20190404.RDS). If possible, save as an RDS file.

Using the same example, if we wanted to remove columns and change the names of those left, we would do so in the data\_prep document and save the now processed data into the data&gt;processed folder.

The historial data will be used for EDA & model building but consider the data pipeline requirement for scoring new data.

#### Step 4: Modeling

Once you've loaded and processed the data, it's time do some exploratory data analysis and develop a modeling strategy. This will require several documents.

-   model\_EDA.Rmd: this should be a journal like document that describes your exploratory data analysis and provides visualizations and summaries of any useful insights. Also, if you have ideas for creating new variables - also know as feature engineering - they should be documented here. Save this file *docs/model*
-   model\_dev.Rmd: this is where you will build and validate the model. It should save the model object as an RDS object in the *data/models* folder. The markdown file should be saved in *code/model*
-   model\_research.Rmd: any research and development related to the model development can be done here and saved in the docs&gt;model folder. This should be saved in *docs/model*

#### Step 5: Operationalization

Once you've developed the ETL process and have build a model, it's time to think about the production version of the process. In the wild, this is developing and implementing a plan to integrate the solution into the business process.

*data\_prep\_production.R* &gt; This file will prep and load new data to be scored. It will save the newly processed data in the *data/modeling* folder.

*scoring\_production.Rmd* &gt; This markdown will execute the data\_prep\_production.R from above using the *source* function, load the saved model from *data/models*, and use the *predict* function to score the new data. This scored data can be saved in the *data/scoring* folder (not shown).

#### Step 6: Iterate

Now that you have working data science solution, you probably have some ideas to improving the process. If necessary, go back to step 3: - Add more data to model
- Improve the speed of the process by remove unnecessary variables - Make code more efficient.

After this, move to step 4:
- Engineer additional features
- Build up a more complex model or ensemble several techniques.

#### Presentation

On the last day of class, you each will have 20 minutes to showcase your product. In the event that we need an extra class to finish up, presentations will be pushed to the day and time reserved for the final exam.

#### Remember!

You're all Github users now! Take advantage of the functionality.

#### Grading

The grade you receive will be a function of the extent to which you follow these guidelines, write neat code, provide thoughtful explanations, and build a working product. You will *NOT* be penalized for an under performing model.
