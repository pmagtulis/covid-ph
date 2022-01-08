# covid-philippines
A Covid-19 database containing cases and test numbers

Source: Department of Health data drop (as of Jan. 7)

# Recent updates

As of Jan. 7: Included code to track cases by day on a provincial and regional level, **groupby** municipalities added samples data, charts are bigger, cleaned 
and made more succinct.

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

1. **CaseCode** - random code assigned for labelling cases; does not equate to the unique case number assigned by DOH
2. **Age** - age
3. **AgeGroup** - five-year age group
4. **Sex** - confirmed case's sex
5. **DateSpecimen** - date when specimen was collected
6. **DateResultRelease** - date of release of result
7. **DateRepConf** - date publicly announced as confirmed case
8. **DateDied** - date patient died. *Not used to tabulate number of deaths as publicly reported*
9. **DateRecover** - date patient recovered. *Not used to tabulate number of recoveries as publicly reported*
10. **RemovalType** - type of removal, whether by recovery or death, that happens to a patient. *Probably important in tallying active cases which are not included
in this report*
11. **Admitted** - binary variable indicating patient has been admitted to hospital 
12. **RegionRes** - region of residence
13. **ProvRes** - province of residence
14. **CityMunRes** - city or municipality of residence
15. **CityMuniPSGC** - Philippine Standard Geographic Code of Municipality or City of residence
16. **BarangayRes** - barangay of residence
17. **HealthStatus** - known current health status of patient (asymptomatic, mild, severe, critical, died, recovered)
18. **DateOnset** - date of onset of symptoms
19. **Pregnanttab** - binary variable (Yes/No) indicating if the patient is pregnant at any point during Covid-19 infection
20. **Quarantined** - ever been home quarantined, not necessarily currently in home quarantine

### Tests

1. **facility_name** - name of the institution certified by the Department of Health to perform COVID-19 Testing
2. **daily_output_positive_individuals** - refer to the actual number of all unique individuals with positive results that are released from 6pm the previous day
to 6pm of the reporting date
3. **daily_output_negative_individuals** - refer to the actual number of all unique individuals with negative results that are released from 6pm the previous day 
to 6pm of the reporting date
4. **daily_output_unique_individuals** - sum of all unique individuals tested (positive+negative) with results that are released from 6pm the previous day to 6pm 
of the reporting date
5. **daily_output_invalid** - number of all specimens with invalid results that are released from 6pm the previous day to 6pm of the reporting date. *Reasons for
invalidity were not indicated.*
6. **daily_output_samples_tested** - total specimens processed with results (positive, negative, equivocal or invalid) released from 6pm the previous day to 6pm of 
the reporting date.
7. **cumulative_unique_individuals** - number of unique individuals who underwent COVID-19 testing, regardless of result, accumulated since the start of operations 
in the laboratory. One individual, with 2 or more specimen results will only be counted once.
9. **cumulative_positive_individuals** - number of unique individuals with a positive result after COVID-19 testing using the appropriate confirmatory test (ex. 
RT-PCR)
10. **cumulative_negative_individuals** - total number of unique individuals with a negative result after COVID-19 testing
11. **cumulative_samples_tested** - sum of all specimens tested with validated results from the start of laboratory operation up to the reporting date
12. **pct_positive_cumulative** - total Number of cumulative positive individuals as percent of cumulative unique individuals per day
13. **pct_negative_cumulative** - total Number of cumulative negative individuals as percent of cumulative unique individuals per day
14. **remaining_available_tests** - remaining COVID-19 tests that can be conducted by the health facility or laboratory based on the PCR testing kits they 
currently have. For GeneXpert labs, this refers to the remaining number of cartridges on hand.

# What is the source of data?

Information in the database were collected from the [DOH Covid-19 Tracker Data Drop](https://doh.gov.ph/covid19tracker). CSV files were downloaded from the
Cloud drive maintained and updated by the agency daily. To properly use this database, simply download the latest CSV files and update the file name in the
**pd.read_csv** portion of the code once in Jupyter Notebook (*Most likely you'll only have to change the numerical date in the filename)*

After the necessary updates, simply run the kernel to get outputs.

# What is needed to be able to use this code?

You would need to install Python and Jupyter notebook in your computer to read this. You can easily search the installation process, depending on the OS you have,
in the net like [this](https://medium.com/co-learning-lounge/how-to-download-install-python-on-windows-2021-44a707994013). 

After installation, go to your terminal and **pip install pandas**. After which, download the CSV files from the DOH Data Drop. Go run **jupyter notebook** and 
enjoy!


**Comments and suggestions are always welcome! All rights reserved.**
