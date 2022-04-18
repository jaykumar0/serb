# serb
Indian Science and Engineering Research Board Projects - Yr 2015-2020

about -  
https://www.serbonline.in/SERB/HomePage

Extramural Research (EMR) funding scheme of SERB to academic institution, research laboratories and other R&D organizations to carry out basic research in all frontier areas of Science and Engineering is in limelight for more than four decades since from the inception of SERC. This scheme encourages emerging and eminent scientist in field of science and engineering for individual centric competitive mode of funding. Since the scheme provides core research support to the active researchers, the existing name Extramural Research (EMR) has been renamed as Core Research Grant (CRG).

Extramural Research (EMR) funding scheme of Indian Science and Engineering Research Board to academic institution, research laboratories and other R&D organizations to carry out basic research in areas of Science and Engineering.

data - 
http://www.serb.gov.in/emr-projects.php

The data is of approved projects from years 2015 till 2020.[http://www.serb.gov.in/emr-projects.php]

More Analysis - 
https://www.kaggle.com/datasets/jaykumar/serb-projects/code

Viz
https://public.tableau.com/app/profile/jaykumar0/viz/ScAndErResearchBoard/ByYr


Processing -
STEP 1 - Read from PDF  to csv -

Use Python tabula library to read the pdf files.

STEP 2 - Process the csv -

Many observations are spread across multiple rows.
For such obeservatoins,the Cost feature is is the grouping criteria.
Created a logic around this to properly get all the rows.


STEP 3 - Clean -  Process 2016-17,2017-18,2018-19,2019-20 together as the data structure is similar.
1. Add year to the individual file.
2. merge all the years data into one dataframe.
From all the string fields - Discipline, Sub Area,Title,PI Details - 
a) Remove leading, trailing,multiple spaces and carriage returns
b) Clean Discipline and Sub Area
c) Get Professor Names from PI Details
d) Get Institute from PI Details
e) Get Pin Code - get the six numeric characters from PI Details - 10% Pin Codes Missing
f) Get State from PI Details - Few States Missing - not fitting into  the logic [ {Update Manually} - 1]

STEP 4 - Clean 2015-16 - Process separately because - 
a) the features are different 
b) upon reading many Professors Names get embedded into the Title
c) Many Institute Names gets into the Professors name

For b and c - cannot do any logic , needs to be manually cleaned.[ {Update Manually} - 2]

d) Rename columns  as per other files
e) Get Pin Code and State
f) Add Year
g) Merge it with all the other years file

STEP 5 - ( all merged file ) 
a)  Clean Institute -Trim  it, remove multiple spaces, remove spaces after ',' and make it proper case
a) Add Tier based on Institute

=========================================
Still Institute can be cleaned more, for example check the variations in Indian Instaitute of Science - 
(This has been extrated based on if the text has 560012(Pin cd) in it or not- possibly there may be variations where the pin code may be missing)


array(['Indian Institute Of Science,Bangalore,Bangalore,Karnataka,560012',
       'Indian Institute Of Science,Bangalore,Bangalore,Karnataka,560012 Tamal Banerjee,Indian Institute Of Technology Guwahati,Guwahati,Assam,781039',
       'Indian Institute Of Science,Bangalore,Bangalore,Karnataka,560012 Ankur A Kulkarni,Indian Institute Of Technology Bombay,Mumbai,Maharashtra,400076',
       'Indian Institute Of Science Education And Research Thiruvananthapuram,Thiruvananthapuram,Kerala,695016 Divya Bellur Uma,Azim Premji University Banglore,Bangalore,Karnataka,Tejas Gorur Murthy,Indian Institute Of Science,Bangalore,Karnataka,560012',
       'Indian Institute Of Science,Banglore,Bangalore,Karnataka,560012',
       'Department Of Inorganic And Physical Chemistry,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Solid State And Structural Chemistry Unit,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Dept. Of Inorganic & Physical Chemistry,Indian Institute Of Sciences,Bangalore,Karnataka,560012.',
       'Department Of Inorganic & Physical Chemistry,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Nmr Research Centre,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Chemical Engineering,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Chemical Engineering,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Electrical Engineering,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Electrical Communication Engineering,Institute Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Electrical Communication Engineering,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Computational And Data Sciences,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Dept. Of Materials Engineering,Indian Institute Of Sciences,Indian Institute Of Sciences ,Banglore,Karnataka,560012.',
       'Department Of Instrumentation And Applied Physics,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Dept. Of Materials Engineering,Indian Institute Of Science,Indian Institute Of Sciences- Bangalore,Karnataka,560012.',
       'Department Of Materials Engineering,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Microbiology & Cell Biology,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Biochemistry,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Moleucular Reproduction,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Computaional And Data Sciences,Indian Institute Of Sciences,Indian Institute Of Sciences- Bangalore,Karnataka,560012.',
       'Molecular Biophysics Unit,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Biochemistry,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Microbiology & Cell Biology,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Department Of Computational And Data Sciences,Indian Institute Of Science,Bangalore,Karnataka,560012',
       'Department Of Physics,Indian Institute Of Science,Bangalore,Karnataka,560012.',
       'Indian Institute Of Science Bangalore 560012 Karnataka',
       'National Institute Of Advanced Studies Bangalore 560012Karnataka',
       'Indian Institute Of Science Bangalore 560012Karnataka'],
      dtype=object)








