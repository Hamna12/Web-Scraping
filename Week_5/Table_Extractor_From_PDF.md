# We learn how to Extract Table from PDF

* Basics of PDF file format
* Installing required python modules
* Extracting tables from pdfs
* Introduction to Pandas DataFrame
* Writing Tables into csv file

# What is PDF???

PDF stands for Portable Document Format. It is a file format developed by adobe in 1990s to present documents that include text, graphic and images, independent of 
software, hardware and operating systems. 
Let's say, whether its Apple Mac or Microsoft windows - a documents should look like the same hence pdf was developed.

* The first version 1.0. was introduced in 1993.
* PDF is based on PostScript language, each file encapsulated a complete description of fixed-layout document.

# General Structure of PDF:

It is composed of following code component:
* Header (contain just one line that identifies the version of PDF.)
* Body  (contains all the object information -font, image, words, Bookmark from field and so on)
* Cross-reference (Xref Table)   (contains pointer to all objects included in PDF files. It identifies how many objects are in table)
* Trailer  (contains pointer to xref table and to key objects contained in trailor directory).

# Extract Tables From PDF:

Following are the packages:
### Camelot:
It is python package that is used to extract tables from pdf. It is open source package available in Pypi

# Why Camelot...???
* We are in control. Unlike other libraries and tools which either give a nice output or fail miserably(with no-in-between). Camelot give us the power to tweak table extraction.
* Each table is a pandas dataframe, which seamlessly integrated into ETL and Data Analysis workflow.
* Export to multiple formats, including JSON, Excel and HTML.


## Other Python Modules
* Tabula (it is one of the most widely used pdf extraction library. It is based on java library with same name Tabula. It is python binding for java library.
* Pdftable 
* Pdfplumber
* Pdf-table-extraction
