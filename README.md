# Email-Marketing-Analysis-using-Power-BI

The Following are the important DAX measures that were applied throughout the entire project:

1. Click Rate (CTR) = (Emails clicked) / (Emails sent) - (Bounces)
``CTR = SUM(TBL_Communication[Email_Click_Count])/(SUM(TBL_Communication[Is_Email_Sent])-SUM(TBL_Communication[Bounced_email]))```

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

### A Glimpse of the Dashboard

![Screenshot (174)](https://user-images.githubusercontent.com/75041273/133941108-c6ee113b-7a78-4a98-8d63-fa8b32c65d5f.png)
