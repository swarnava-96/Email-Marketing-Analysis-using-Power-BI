# Email-Marketing-Analysis-using-Power-BI

### Aim: To create an interactive dashboard showing the various KPI's of Email Campaigns for an ecommerce comapany. 

### About the Data set: 
The dataset,Email Campaign Analysis.xlsx consists of five excel sheets namely, "TBL_Communication", "TBLCustomerProfieData", "TBL_SalesData", "TBL_CampaignS" and "TBL_CouponData". Out of these five sheets I have taken the "TBL_Communication" sheet and imported into Power BI Desktop. The enitire analysis is carried on with this table or sheet only. The table contains various columns or features like "CampaignCodJ", "Medium_Type", "Is_Email_Sent", "Email_Sent_Status", "Email_SentDate", "Email_Open_Count", "Email_Click_Count", "Is_SMS_Sent" and "SMS_SentDate". The datatypes of each feature is ether categorical or strings.

### Project Description: 
An extensive exploratory data analysis was performed, new columns were created using DAX measures and few new measeures were also calculated with he help of DAX.
Slicers for Campaign Code, Year, Month and Day of Email Sent was created by extracting the Month and Day from the "Email_SentDate" feature using filters.

The Following are the important DAX measures that were applied throughout the entire project:

1. Click Rate (CTR) = (Emails clicked) / (Emails sent) - (Bounces)

```CTR = SUM(TBL_Communication[Email_Click_Count])/(SUM(TBL_Communication[Is_Email_Sent])-SUM(TBL_Communication[Bounced_email]))```

2. Bounce Rate (BR) = ((Bounced Emails) / (Sent Emails)) *  100

```BR = SUM(TBL_Communication[Bounced_email])/SUM(TBL_Communication[Is_Email_Sent])```

3. Email Open Rate (OR) = (Number of Emails Read / Number of Delivered Emails) * 100

```OR = SUM(TBL_Communication[Email_Open_Count])/SUM(TBL_Communication[Delivered_email]) ```

4. Deliverability Rate = (Delivered Emails / Total Sent) * 100

5. Delivery Rate = (((Number of Emails Sent) - (Number of Bounces)) / (Number of Emails Sent)) * 100%

6. Unique click count was calculated using DAX formula: 

```Unique_click = IF(TBL_Communication[Email_Click_Count]>0,1,0)```

7. Unique open count was calculated using DAX formula:

```Unique_open = IF(TBL_Communication[Email_Open_Count]>0,1,0)```

8. Total Bounced Email was calculated using DAX formula: 

```Bounced_email = IF(TBL_Communication[Email_Sent_Status]="Bounced",1,0)```
 
9. Total Delivered Email was calculated using DAX formula: 

```Delivered_email = IF(TBL_Communication[Email_Sent_Status]="Sent",1,0)```

10. ```Member_open = IF(TBL_Communication[Email_Open_Count]>0,TBL_Communication[PartyUId])```
   
   ```Member_click = IF(TBL_Communication[Email_Click_Count]>0,TBL_Communication[PartyUId])```

11. Pie chart showing Email Send Status was created putting Email_Sent_Status as legend and Count of Campaigncod as values

12. New column was created for extracting the month and year applying the DAX measure: 

```Month_Year = CONCATENATE(CONCATENATE(FORMAT(TBL_Communication[Email_SentDate],"mmm"), "-"),YEAR(TBL_Communication[Email_SentDate]))```

Clustered column chart was made putting "Month_Year" as axis and "is_email_sent" as value.  Finally, a table at the bottom was added to show all the feature values in details.

## Installation:

The following steps will guide you to install Power BI Desktop and run the project at your local machine:

1. Download and install Power Bi Desktop from [here](https://www.microsoft.com/en-in/p/power-bi-desktop/9ntxr16hnw1t#activetab=pivot:overviewtab).
2. Clone this github repository or download as zip.
3. Once Everything is done, open the .pbix file. 

If you already have Power BI Desktop, then you can skip the first step.

### A Glimpse of the Dashboard:

![Screenshot (174)](https://user-images.githubusercontent.com/75041273/133941108-c6ee113b-7a78-4a98-8d63-fa8b32c65d5f.png)

### Tech Stack:

<img src="https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=Power%20BI&logoColor=black"/> 

