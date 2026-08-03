## METHODS FOR TRANSCRIBING HANDWRITING IN IMAGES FOR HISTORICAL RESEARCH
Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang

Miriam Schoenbaum

Summer 2026

[GitHub repo]( https://github.com/MSchoenbaum/UMBC-DATA606-Capstone)

[Final PowerPoint presentation]( https://github.com/MSchoenbaum/UMBC-DATA606-Capstone/blob/4dd3182c6f68601ed8d13fac67778709fe64a8c7/docs/Capstone%20presentation.pptx
)

[Video of presentation]( https://github.com/MSchoenbaum/UMBC-DATA606-Capstone/blob/c8b16a2af174477d9149a7c75a95c9bc12636fe2/docs/Video%20presentation.ppsx)

## BACKGROUND

The Boyds store ledger is a valuable primary-source document for researchers interested in the social and/or economic history of a multi-racial/multi-ethnic rural community in the U.S. in the early 20th century. The 464-page accounts ledger was kept by storekeeper Benjamin F. Hicks in Boyds, Maryland, for the years 1904-1906. The store served separate but connected rural communities: a Black community of people who had formerly been enslaved locally or in other states where slavery had been legal, and a white community consisting of local ex-enslaving families and newcomers from elsewhere. Economic activities in Boyds included dairy farms, summer hotels, domestic labor, and railroad labor. The B&O Railroad transported goods and people between Boyds and Washington, D.C.  The Boyds store supplied everything from shoes to arsenic, and accepted payment in cash, barter, and labor. 

Members of the Boyds Historical Society have digitally imaged the document by making high-quality, digitally-enhanced photos of each page of the ledger. However, to be used in research, the document must also be transcribed, and manual transcription can slow and tedious. Initial efforts to crowd-source the manual transcription through the platform From The Page were not successful.

Therefore, in the fall of 2025, the Boyds Historical Society successfully applied for a mini grant for $2,500 from Heritage Montgomery for automated transcription. The work plan in the grant was to use the transcription platform Transkribus to train an individual model for the ledger, based on the table layout and at least two individual handwriting styles in the ledger. The Transkribus platform is built on the PyLaia Python library. Users pay to subscribe to the platform, and the transcription runs on their servers. The grant funding was for the Transkribus subscription and for an undergraduate student to proofread the automated transcription.

For this capstone project, research questions include:

- What are the feasible options for transcribing the Boyds store ledger?
- Which is the most feasible option? Factors affecting feasibility include:
  - accuracy
  - ease of use
  - cost in time and effort 
  - dollar cost
  - skills required
  - privacy/control over proprietary data

## DATA

**Data source**: the Boyds store ledger, 1904-1906.

**Data size** : 464 jpg files, 1.91 GB total, individual image files 2.5-8.5 MB.

**Time period**: primarily 1904-1906.

**Data elements**: each image file represents one page in the store ledger. Generally, there is one customer per page. A few ledger pages have two or three customers per page. Many customers have more than one page in the ledger. Some pages are not customer pages, such as the page for the livery stable, the page for life insurance payments, and the page for a mortgage loan. Some pages are blank.

**File description**: The ledger paper is in column format. For the customer pages that are one customer per page, the format is irregularly tabular. The header information is customer name, year, and ledger page number. The columns represent, from left to right: the month of the sold-to transaction, the date of the sold-to transaction, the word to, the items and quantities sold, the dollar amount, the month of the bought-from/paid transaction, the date of the bought-from/paid transaction, the dollar amount. In addition, there are occasional rows representing the customer’s balance. There are a lot more rows representing sold-to than bought-from/paid.

**Data type**: Mixed words and numbers. Includes abbreviations, annotations, and underlined superscript. At least two different handwritings, one bad (the jagged handwriting), one less bad (the loopy handwriting).

## OPTIONS

### MANUAL TRANSCRIPTION

The images from the Boyds store ledger are posted on the transcription platform From the Page, hosted on the account belonging to the Sandy Spring Museum, at [From the Page]( https://fromthepage.com/ssm-archives/boyds-store-boyds-md).

A table format was created for the manual transcription. Anyone can create an account, sign in, and start transcribing. From the Page also has an AI transcription option, using Gemini, but this option is not available on the Sandy Spring Museum’s account.

At the beginning of this project, 8 pages had been manually transcribed. An additional 9 pages were manually transcribed to prepare for training the Transkribus model (described below). 

### PYLAIA PYTHON LIBRARY

PyLaia is a toolkit for Automatic Text Recognition and Keyword Spotting. Documentation is posted at [PyLaia documentation]( https://doc.teklia.com/pylaia/). PyLaia has the capability of generating trainable models for transcribing individual text line images.

PyLaia is based on an earlier version, called Laia, which is in turn is based on a 2017 paper by Joan Puigcerver. The paper examined the potential for convolutional and one-dimensional recurrent layers for handwritten text recognition, versus the computationally more expensive multidimensional recurrent layers (J. Puigcerver, "Are Multidimensional Recurrent Layers Really Necessary for Handwritten Text Recognition?," 2017 14th IAPR International Conference on Document Analysis and Recognition (ICDAR), Kyoto, Japan, 2017, pp. 67-72, doi: 10.1109/ICDAR.2017.20.)

The most recent version of Python that is compatible with PyLaia is Python 3.10, and PyLaia was most recently updated in August 2024.

### TRANSKRIBUS

Transkribus is a platform for text recognition, layout detection, and AI training on handwritten documents. It is based on PyLaia. Transkribus is owned and operated by READ-COOP SCE, a European Cooperative Society founded in 2019 in Innsbruck, Austria. The platform requires a paid subscription.

### GEMINI

Gemini offers users the option of uploading an image and receiving a transcription of the handwriting in the image. Gemini is a family of multimodal large language models developed by Google. The versions used in this project are Gemini 3.6 Flash and Gemini 3.1 Pro. According to a Substack post by Mark Humphries, professor of history at Wilfrid Laurier University in Waterloo, Canada, “Gemini 3 consistently produces text with error rates comparable to the very best humans” (see [Gemini 3 Solves Handwriting Recognition]( https://generativehistory.substack.com/p/gemini-3-solves-handwriting-recognition), November 25, 2025; accessed August 2, 2026).

## RESULTS: EVALUATION OF FEASIBILITY 

### MANUAL TRANSCRIPTION

**Accuracy**: In this project, the manual transcription is considered the ground truth. The manual transcriptions were done by members of the Boyds Historical Society, who are familiar with the residents and history of Boyds at the time of the ledger, as well as many of the products bought and sold at that time. In addition, where a particular word or abbreviation is unclear, the transcriber can often do additional research to help clarify the transcription.

**Ease of use**: The From the Page platform is intuitive to use and only requires a transcriber to create an account and sign in.

**Cost in time and effort**: Uploading the images into From the Page and creating the table format both required considerable time and effort, but both of these tasks had already been completed before this project began. Manual transcription is slow and requires familiarity with both the handwriting and the historical context. An experienced transcriber of the ledger may be able to complete transcription of one complete page of the ledger in an hour or two. Even assuming one hour per page, as well as some blank pages, a full transcription of the ledger would take over 10 weeks of full-time work at 40 hours per week. 

**Dollar cost**: From the Page has zero cost to the Boyds Historical Society, thanks to the Sandy Spring Museum, which is paying for their account. The cost to a small organization is $3,600 per year. The cost to a researcher with one project is $1,200 per year.

**Skills required**: The manual transcriber needs to have familiarity with handwriting and historical context.

**Privacy/control over proprietary data**:  The From the Page platform claims a nonexclusive license to publish users’ data on From The Page Services, including anything reasonably related to publishing it (like storing, displaying, reformatting, and distributing it), as well as using the data to promote FromThePage, including its products and content.  Users can delete their data.

### PYLAIA

The coding for this part of the project was done in Google Colab, using Python 3.10, the PyLaia documentation, and assistance from Gemini. Three line images were used for the model, corresponding to the following text:

*Train*: The moving finger writes; and, having writ, moves on.

*Validate*: Nor all they piety nor wit shall lure it back to cancel half

*Test*: a line, nor all thy tears wash out a word of it.

**Accuracy**: The model trained on the train image did not return a result for the test image. A trained model imported from Hugging Face, following the PyLaia documentation, returned the following transcription for the test image: oerr m ar m nor mraa a vosen It is likely that a model trained on a much larger number of images would produce better results.

**Ease of use**: PyLaia transcribes individual line images. The images in the Boyds store ledger are page images containing many lines. 

**Dollar cost**: No additional cost.

**Skills required**: The user would at least have to be familiar with basic coding and coding structure in Python. Gemini was able to provide and correct code for individual tasks, such as providing file paths, but would not have been able to provide workable code for the whole project as a single task. Explicit input of PyLaia documentation, from the user, was also necessary.

**Privacy/control over proprietary data**: There’s no way to know what Google actually does with anybody’s data. It would probably be possible to run the code in Jupyter Notebook, though.

### TRANSKRIBUS

**Accuracy**: The model trained on 17 ground truth images produced a best Character Error Rate (CER) of 57.05%, and a best Word Error Rate (WER) of 76.89%. Effectively, the results were unusable. (See [Transkribus/manual comparison table]( https://github.com/MSchoenbaum/UMBC-DATA606-Capstone/blob/4dd3182c6f68601ed8d13fac67778709fe64a8c7/data/Transkribus/comparison%20table%20Transkribus%20manual.docx) as an example.)

**Ease of use**: At minimum, there was an additional step of manually identifying all of the individual lines in each image for ground truth. The general version of Transkribus was not able to reliably identify individual lines on its own.

**Dollar cost**: This project used the grant from Heritage Montgomery to buy a one-year subscription from Transkribus for €99. Preparing ground truth images and running training models does not use up credits. Using the training model to transcribe images uses up one credit per page, each time. 

**Skills required**: It is likely that someone with more experience using Transkribus would be able to produce better results with training the model. Transkribus has posted a lot of webinars to YouTube to help users use the platform more effectively.

**Privacy/control over proprietary data**: Transkribus is GDPR-compliant, and all of the data are processed and stored on Transkribus-owned servers in Austria. The owner of the data retains control over the data and can delete the data.

### GEMINI

**Accuracy**: This project used two versions of Gemini (Gemini 3.6 Flash and Gemini 3.0 Pro) and two prompts. 

The first prompt, with Gemini 3.6 Flash, was “Transcribe this handwritten page from a store ledger. The writing has numbers and words. Some of the words are abbreviations. The image is in tabular format. The customer name and the year are at the top. The columns from left to right are month, day, items sold to the customer, total cost of items, month, day, items bought from the customer or customer payment, total amount.

The second prompt, with Gemini 3.1 Pro, was “Your task is to accurately transcribe this handwritten historical document, minimizing the CER and WER. Work character by character, word by word, line by line, transcribing the text exactly as it appears on the page. To maintain the authenticity of the historical text, retain spelling errors, grammar, syntax, capitalization, and punctuation as well as line breaks. Transcribe all of the text on the page including headers, footers, marginalia, insertions, page numbers, etc. If insertions or marginalia are present, insert them where indicated by the author (as applicable). In your final response write Transcription: followed only by your transcription.” The source of this prompt, specifically with Gemini 3.1 Pro, is the Substack post by Mark Humphries cited above, modified to be appropriate for this specific project.

In both cases, Gemini produced results that were plausible but often incorrect. Compare [Gemini 3.6]( https://github.com/MSchoenbaum/UMBC-DATA606-Capstone/blob/4dd3182c6f68601ed8d13fac67778709fe64a8c7/data/Gemini/Gemini%203.1%20page%201.docx), [Gemini 3.1]( https://github.com/MSchoenbaum/UMBC-DATA606-Capstone/blob/4dd3182c6f68601ed8d13fac67778709fe64a8c7/data/Gemini/Gemini%203.6%20page%201.docx), and the [manual transcription]( https://github.com/MSchoenbaum/UMBC-DATA606-Capstone/blob/4dd3182c6f68601ed8d13fac67778709fe64a8c7/data/Gemini/Manual%20page%201.docx). That is, the Gemini transcriptions included items that could have been in the store ledger page, but in reality, they were not the correct items that actually were on the store ledger page.

**Ease of use**: Gemini is easy to use for individual images: just upload the image and add the prompt. The API would likely be somewhat less easy to use.

**Cost in time and effort**: The initial cost in time and effort is minimal for individual images. However, given the plausible but incorrect results, there would need to be a lot of close attention for proofing, after the Gemini transcription.

**Dollar cost**: Gemini is currently free to use for individual images and for the limited API. The unlimited API is not free.

**Skills required**: The same skills would be required for proofing as for manual transcription, i.e., familiarity with handwriting and historical context.

**Privacy/control of proprietary data**:  There’s no way to know what Google actually does with anybody’s data.

## CONCLUSIONS

- Manual transcription on the From the Page platform, using the Sandy Spring Museum’s subscription, is the most feasible option for the Boyds Historical Society to transcribe the Boyds store ledger. 

- Transkribus may also be a feasible option, if the accuracy improves with more training data. The Boyds Historical Society has already paid for the subscription, and more pages will need to be manually transcribed either way.

- Gemini is not really a feasible option. An API would be needed. However, the free limited API uses the data to train the LLM, while the unlimited API, which does not use the data to train the LLM, is not free. In addition, the transcription results are plausible but incorrect often enough that close manual editing and correction would be required. With that level of effort, it might be just as easy to skip Gemini and go straight to manual transcription.

- PyLaia is not a feasible option. The Boyds Historical Society does not have the capability to convert the 436 page images in the ledger into 100 or more line images per page. 

## LIMITATIONS

There are at least two limitations to this project.

1. The Boyds store ledger may not be a typical handwritten historical document. The mix of words, abbreviations, numbers, and annotations may complicate the transcription task. The semi-regular format – not really a table but somewhat tabular, generally linear but in columns – may also complicate the transcription task. All four of the transcription methods, including manual transcription, might be more succesful with a more regular handwritten historical document.

2. It’s likely that many researchers examining handwritten historical documents do not have a data science background. Even Gemini, which is the easiest automated transcription method for the general user, would require access to an API. The alternative would be manually uploading 436 pages (minus the blank pages) into Gemini, one at a time.

## FUTURE RESEARCH DIRECTIONS

For this transcription project specifically, the future research direction consists of more manual transcription, producing more ground train images for training the Transkribus model, and better preparation of ground truth images in Transkribus. 

However, generally, there is a need for a handwriting transcription option that is accurate, transparent, and easy to use, while also maintaining ownership of the data.

