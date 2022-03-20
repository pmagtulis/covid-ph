# covid-ph
A Covid-19 database of cases and test numbers

Source: Department of Health data drop

# Recent updates

|**Date**|**Updates**|
|---|---|
|*Mar. 19*|Updated data as of Mar. 12. DOH has so far been delaying release of case drop files|
|*Feb. 26*|Updated data as of Feb. 19. DOH has so far been delaying release of case drop files|
|*Feb. 18*|Updated data as of Feb. 12. DOH has so far been delaying release of case drop files|
|*Feb. 14*|Updated data as of Feb. 5. DOH has so far been delaying release of case drop files|
|*Feb. 7*|Updated data as of Jan. 30|
|*Jan. 30*|Updated data as of Jan. 22. Updated with plotnine charts|
|*Jan. 23*|Updated data as of Jan. 15. Included a **NaN section** for testing aggregates where over 9,900 were seen as null values|
|*Jan. 17*|Included a **NaN section** and fixed tally of cases to use **Sex** column instead of **CaseCode** due to null values on the latter|

# What is this about?

Using pandas, I processed regularly released data by the health department. There are two types of data here: first are case numbers. Second are test numbers.
I aim to regularly update this as well.

# Why this?

The code is meant to be an easier way to interpret large Covid-19 data released daily by the health department. This is shared to everyone but the primary goal is
to assist researchers and journalists in their reporting of the ongoing pandemic.

# What you can do with the data?

The code is meant to easily navigate through case files and draw analysis from them. Information such as **which province has the most number of cases** or
**how much testing is being conducted, which age group is most infected** and others can be easily determined through the database. Similarly, programmers
and other researchers can likewise play around with the code for their own analysis using pandas.

Since data can be retrieved and analyzed by just changing the code, it is also easier to make visualization out of them. Below is an example of visualization I made 
using data collected and processed in Jupyter Notebook. These visualizations require the use of other softwares like **QGIS** and **Adobe Illustrator**.

![cases by provinces-01](https://user-images.githubusercontent.com/87161563/148441101-3daa6894-d32e-4ef0-9950-d35f6cb09105.png)

# Definition of terms

The following are MOSTLY from [definitions](https://docs.google.com/spreadsheets/d/1rD77PMdxN6JMVeYmk7mvgDNtEHJt8Du6ozaLm_Qok0Q/edit#gid=1714687638) from the 
Department of Health. In all cases **NaN** means no data input for that particular column.

### Cases

|**column name**|**definition**|
|---|---|
|**CaseCode**|random code assigned for labelling cases; does not equate to the unique case number assigned by DOH|
|**Age**|age|
|**AgeGroup**|five-year age group|
|**Sex**|confirmed case's sex|
|**DateSpecimen**|date when specimen was collected|
|**DateResultRelease**|date of release of result|
|**DateRepConf**|date publicly announced as confirmed case|
|**DateDied**|date patient died. *Not used to tabulate number of deaths as publicly reported*|
|**DateRecover**|date patient recovered. *Not used to tabulate number of recoveries as publicly reported*|
|**RemovalType**|type of removal, whether by recovery or death, that happens to a patient. *Probably important in tallying active cases which are not included in this report*|
|**Admitted**|binary variable indicating patient has been admitted to hospital|
|**RegionRes**|region of residence|
|**ProvRes**|province of residence|
|**CityMunRes**|city or municipality of residence|
|**CityMuniPSGC**|Philippine Standard Geographic Code of Municipality or City of residence|
|**BarangayRes**|barangay of residence|
|**HealthStatus**|known current health status of patient (asymptomatic, mild, severe, critical, died, recovered)|
|**DateOnset**|date of onset of symptoms|
|**Pregnanttab**|binary variable (Yes/No) indicating if the patient is pregnant at any point during Covid-19 infection|
|**Quarantined**|ever been home quarantined, not necessarily currently in home quarantine|

### Tests

|**column name**|**definition**|
|---|---|
|**facility_name**|name of the institution certified by the Department of Health to perform COVID-19 testing|
|**daily_output_positive_individuals**|refer to the actual number of all unique individuals with positive results that are released from 6pm the previous day to 6pm of the reporting date|
|**daily_output_negative_individuals**|refer to the actual number of all unique individuals with negative results that are released from 6pm the previous day to 6pm of the reporting date|
|**daily_output_unique_individuals**|sum of all unique individuals tested (positive+negative) with results that are released from 6pm the previous day to 6pm of the reporting date|
|**daily_output_invalid**|number of all specimens with invalid results that are released from 6pm the previous day to 6pm of the reporting date. *Reasons for invalidity were not indicated*|
|**daily_output_samples_tested**|total specimens processed with results (positive, negative, equivocal or invalid) released from 6pm the previous day to 6pm of the reporting date|
|**cumulative_unique_individuals**|number of unique individuals who underwent COVID-19 testing, regardless of result, accumulated since the start of operations in the laboratory. One individual, with 2 or more specimen results will only be counted once|
|**cumulative_positive_individuals**|number of unique individuals with a positive result after COVID-19 testing using the appropriate confirmatory test (ex. RT-PCR)|
|**cumulative_negative_individuals**|total number of unique individuals with a negative result after COVID-19 testing|
|**cumulative_samples_tested**|sum of all specimens tested with validated results from the start of laboratory operation up to the reporting date|
|**pct_positive_cumulative**|total number of cumulative positive individuals as percent of cumulative unique individuals per day|
|**pct_negative_cumulative**|total Number of cumulative negative individuals as percent of cumulative unique individuals per day|
|**remaining_available_tests**|remaining COVID-19 tests that can be conducted by the health facility or laboratory based on the PCR testing kits they currently have. For GeneXpert labs, this refers to the remaining number of cartridges on hand|

# What is the data source?

Information in the database were collected from the [DOH Covid-19 Tracker Data Drop](https://doh.gov.ph/covid19tracker). CSV files were downloaded from the
Cloud drive maintained and updated by the agency daily. To properly use this database, simply download the latest CSV files and update the file name in the
**pd.read_csv** portion of the code once in Jupyter Notebook (*Most likely you'll only have to change the numerical date in the filename)*

After the necessary updates, simply run the kernel to get outputs.

# What is needed to be able to use this code?

You would need to install Python and Jupyter notebook in your computer to read this. You can easily search the installation process, depending on the OS you have,
in the net like [this](https://medium.com/co-learning-lounge/how-to-download-install-python-on-windows-2021-44a707994013). 

After installation, go to your terminal and **pip install pandas**. After which, download the CSV files from the DOH Data Drop. Go run **jupyter notebook** and 
enjoy!

# Contact

Prinz Magtulis, [ppm2130@columbia.edu](mailto:ppm2130@columbia.edu)

**Comments and suggestions are always welcome! All rights reserved.**
