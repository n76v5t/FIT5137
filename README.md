java cFIT5137 Assignment 2 -S2 2024  (Weight = 40%) Due - Friday, 20 September 2024, 4:30 PM General Information and Submission o This is an individual assignment. o Submission method: Submission is online through Moodle. o Penalty for late submission: 5% deduction for each day. o Assignment FAQ: There is an Assignment Frequently Asked Questions page set up for the Assignment 2 on EdStem Forum. Problem Description M-Stay is a residential service that offers homestay and rental services to Monash students and staff around Melbourne. The company has an existing operational database that maintains and stores all of the business transactions information (e.g. properties, hosts, listings, booking, etc.) required for the management's daily operation. As the business grows, M-Stay has decided to build a Data Warehouse to improve their analysis and work efficiency. However, since the staff at M-Stay have limited Business Intelligence and Data Warehouse knowledge, they have decided to hire you to design, develop and quickly generate BI reports from a Data Warehouse.The operational database tables can be found at the MStay account. You can, for example, execute the following query:select * from MStay.; The data definition of each table in MStay is as follows:Table Name Attributes,Data Types and Key Constraints Notes 
REVIEW 
Review_ID  
Number 
(PK) 
The table stores review information of the related booking order.  
Review_Date 
Date 
Review_Comment 
Varchar2 
Booking_ID 
Number 
(FK) 
BOOKING 
Booking_ID 
Number 
(PK) 
The table stores booking information. 
Booking_Date 
Date 
Booking_Stay_Start_Date 
Date 
Booking_Duration 
Number 
Booking_Cost 
Number 
Booking_Num_Guests 
Number 
Listing_ID 
Number 
(FK) 
Guest_ID 
Number 
(FK) 
GUEST 
Guest_ID 
Number 
(PK) 
The table stores all guest information. 
Guest_Name 
Varchar2 
LISTING 
Listing_ID 
Number 
(PK) 
The table stores all listing information. Each listing has one property and one host information. 
Listing_Date 
Date 
Listing_Title 
Varchar2 
Listing_Price 
Number 
Listing_Min_Nights 
Number 
Listing_Max_Nights 
Number 
Prop_ID 
Number 
(FK) 
Type_ID 
Number 
(FK) 
Host_ID 
Number 
(FK) 
HOST 
Host_ID 
Number 
(PK) 
The table stores all host information. 
Host_Name 
Varchar2 
Host_Since 
Date 
Host_Location 
Varchar2 
Host_About 
Varchar2 
Host_Listing_Count 
Number 
HOST_VERIFICATION 
Host_ID 
Number 
(PF) 
The table stores the verification information between host and channel. 
Channel_ID 
Number 
(PF) 
CHANNEL 
Channel_ID 
Number 
(PK) 
The table stores the channel of verification for the hosts. 
Channel_Name 
Varchar2 
LISTING_TYPE 
Type_ID 
Number 
(PK) 
The table stores all listing types. 
Type_Description 
Varchar2 A. Transformation Stage The first stage of this assignment is divided into TWO main tasks:
1. Design a data warehouse for the above M-Stay database. 
You are required to create a data warehouse for the M-Stay database.The management is especially interested in the following indicators :● Number of reviews● Number of listings● Average booking costThe following is a list of dimension attributes that you should include in your data warehouse:● Listing type● Listing time [Month, Year]● Listing seasono (Spring:9 to 11, Summer: 12 to 2, Autumn: 3 to 5 and Winter: 6 to 8)● Listing maximum stay duration [short-term: less than 14 nights, medium-term: 14 to 30 nights, long-term: more than 30 nights]● Listing price range [low: less than $100, medium: $100 to $200, high: more than $200]● Channels● Booking duration [short-term: less than 30 nights, medium-term: 30 to 90 nights, long-term: more than 90 nights]● Review time [Month, Year]● Booking cost range [low: less than $5000, medium: $5000 to $10000, high: more than $10000]For the attribute, ensure that it meets the requirements of the range or group specified in your submission, if required in the specification.  
- Preparation stage. Before you start designing the data warehouse, you have to ensure that you have explored the operational database and have done sufficient data cleaning. Once you have done the data cleaning process, you are required to explain what strategies you have taken to explore and clean the data.The outputs of this task for Report are:a) If you have done the data cleaning process, explain the strategies you used in this process (you need to show the SQL to explore the operational database and SQL of the data cleaning, as well as the screenshot of data before and after data cleaning).- Designing the data warehouse by drawing star/snowflake schema. Design task A: The star schema for this data warehouse may contains multi-facts. You need to identify the fact measures, dimensions, and attributes of the star/snowflake schema. The following queries might help you to determine the fact measures and dimensions:
● How many long-term stay duration listings are listed on Facebook?
● How many listings are listed in June 2015?
● How many listings are there in summer for an “Entire代 写FIT5137 Assignment 2 -S2 2024
代做程序编程语言 home/apt” in a medium price range?
● How much is the average booking cost in March 2013?
● How many bookings were there for “Private rooms” with a short-term stay duration in 2015?
● How many high-cost bookings were made in April 2014?
● How many reviews were given in February 2016?Note: the star schema you created in Design Task A as the highest level of aggregationDesign task B:In this assignment, consider the star schema you created in Design Task A as the highest level of aggregation. The M-Stay company manager wants to implement a drill-down function to explore more detailed information. Your task is to suggest several ways to increase the granularity of your fact tables from Design Task A. In other words, the manager wants to decrease the aggregation level of the fact tables you created in Design Task A.The outputs of task A  B for Report are:b) A  star/snowflake schema diagrams for design task A. (You can use Lucidchart to draw the star schema.)c) List suggestion of  increase the granularity of your fact tables for design task B2. Implement design task A star/snowflake schema using SQL.  You are required to implement the star/snowflake schema that you have drawn in design task A. This implies that you need to create the fact and dimension tables in SQL. The output is a series of SQL statements to perform. this task. You will also need to show that this task has been carried out successfully.Note: ● If your account is full, you will need to drop all of the tables that you have previously created during the tutorials.● If you have dropped all tables in your account and you still encounter the ORA-01536: space quota exceeded for tablesace ‘TABLE_NAME’, please check your SQL code whether you have properly joined all tables. This issue was mainly caused when you did not do the table join properly as the number of records multiplied during the process.The outputs of this task for Report are:a) Screenshots of the table structure you created for Design Task A, including the dimension tables and fact tables.
A sample of screenshots of the table structure 

B. Data Analytic Stage 
Conduct a data analysis using the star schema you created in Design Task A by writing SQL queries to explore the data further. Present your findings in a clear and concise manner, demonstrating your understanding of the dataset and highlighting any noteworthy observations or patterns.The outputs of this task for Report are:1. Findings report: A detailed explanation of your findings, including any significant observations or patterns identified during the analysis.Submission Checklist Step 1: Report (25% of the total score) A combined pdf file save as: YourstudentID_A2_report.pdf, containing all of the above tasks: A. Cover pageB. If you have done the data cleaning process, explain the strategies you used in this process (you need to show the SQL to explore the operational database and SQL of the data cleaning, as well as the screenshot of data before and after data cleaning). Note that you are only required to find around 5 (five) data errors for this stage.C. A  star/snowflake schema diagrams for design task AD. List suggestion of  increase the granularity of your fact tables for design task BE. Screenshots of the table structure you created for Design Task A only, including the dimension table and fact tables.a. SQL file for creating the star/snowflake schema is NOT required in submissionF. Findings report: A detailed explanation of your findings, including any significant observations or patterns identified during the analysis.Step 2: Poster (35% of the total score) One page standard A4 poster in PDF format to save as: YourstudentID_A2_poster.pdf Extract key information from the report you created and present it in a one-page poster. The poster must be in standard A4 size and in PDF format, which can be either landscape or portrait. The content should be clear and easy to understand. Avoid using technical jargon or complex language. Review the poster before submission to ensure it effectively communicates the key messages of your report.Note:Ensure the poster content is consistent with the key structure and findings of your report, and choose an appropriate layout that effectively organizes the information in a clear and logical manner. Maintain a good balance of text and visuals to enhance readability, and ensure all visuals are relevant and support the content of the poster. Label all visuals clearly and provide captions where necessary. Avoid overcrowding the poster with too much text or too many visuals, and ensure the poster is free of any grammatical or typographical errors.Key guidance of design a poster: ● What is the main theme/objective of the poster that you want to express?● Who is your target audience for this poster?● Do you really need all the details from your report on this poster?Step 3: Video presentation (40% of the total score) A five minute video presentation in mp4 format save as: YourstudentID_A2_video.mp4 Based on the report and poster you have created, present your design and findings in a five-minute video presentation. Ensure you thoroughly understand both the report and the poster to effectively extract and communicate the key points.



         
加QQ：99515681  WX：codinghelp
