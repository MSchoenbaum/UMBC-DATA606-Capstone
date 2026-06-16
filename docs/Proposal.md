## TRANSCRIBING THE BOYDS STORE LEDGER, 1904-1906

Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang

Miriam Schoenbaum

https://github.com/MSchoenbaum/UMBC-DATA606-Capstone

https://www.linkedin.com/in/miriam-s-b52ba9326/

## BACKGROUND

The Boyds store ledger is a valuable primary-source document for researchers interested in the social and/or economic history of a multi-racial/multi-ethnic rural community in the U.S. in the early 20th century. The 464-page accounts ledger was kept by storekeeper Benjamin F. Hicks in Boyds, Maryland, for the years 1904-1906. The store served separate but connected rural communities: a Black community of people who had formerly been enslaved locally or in other states where slavery had been legal, and a white community consisting of local ex-enslaving families and newcomers from elsewhere. Economic activities in Boyds included dairy farms, summer hotels, domestic labor, and railroad labor. The B&O Railroad transported goods and people between Boyds and Washington, D.C.  The Boyds store supplied everything from shoes to arsenic, and accepted payment in cash, barter, and labor. 

Members of the Boyds Historical Society have digitially imaged the document by making high-quality, digitally-enhanced photos of each page of the ledger. However, to be used in research, the document must also be transcribed, and manual transcription is slow and tedious. Efforts to crowd-source the manual transcription through the platform From The Page were not successful.

Therefore, in the fall of 2025, the Boyds Historical Society succesfully applied for a mini grant for $2,500 from Heritage Montgomery for automated transcription. The work plan in the grant was to use the transcription platform Transkribus to train an individual model for the ledger, based on the table layout and at least two individual handwriting styles in the ledger. The Transkribus platform is built on the PyLaia Python library. Users pay to subscribe to the platform, and the transcription runs on their servers. The grant funding was for the Transkribus subscription and for an undergraduate student to proofread the automated transcription.

For this capstone project, research questions include:

- How can the Transkribus platform be most cost-efficiently used to provide a usable automated transcription? Each page transcription costs 1 credit per time. A subscription that costs 99€ (currently roughly $115) comes with 900 credits. Additional credits must be bought additionally.
- What other automated transcription options are available?
- How do open-source automated transcription options compare to Transkribus? Comparison measures include 
- ease of use
- cost in time and effort 
- dollar cost
- skills required
- accuracy (including train/test accuracy where available)
- privacy/control over proprietary data

## DATA

- Data source: the Boyds store ledger, 1904-1906.
- Data size: 464 jpg files, 1.91 GB total, individual files 2.5-8.5 MB
- Time period: 1904-1906
- Each file represents: one page in the store ledger. Generally, there is one customer per page. A few ledger pages have two customers per page. Some customers have more than one page in the ledger. 
- File description: The pages are in column format. The header information is customer name, year, and ledger page number. The columns represent, from left to right: the month of the sold-to transaction, the date of the sold-to transaction, the word to, the items and quantities sold, the dollar amount, the month of the bought-from transaction, the date of the bought-from transaction, the dollar amount. In addition, there are occasional rows representing the customer’s balance.
- Data type: Mixed words and numbers. Includes abbreviations and underlined superscript. At least two different handwritings, one bad, one less bad.




