#### Letter Reports
---

Return letter submission data on any campaign associated with a group.  These can be filtered using a variety of arguments. There are three different report endpoints.


 ##### URL

   * /reports/users

   * /reports/campaigns

   * /reports/letters


 ##### Method:

  `GET`

 ##### URL Params



 |parameter            |required   |value   |example|
 |---|---|---|
 |format|no|CSV : The API will email the supplied “send_to” email with the CSV attachment JSON : Supplied in the return body|format=csv|
 |states|no|Returns data for the provided states (comma separated)|states=MT,WY,ND|
 |send_to|no|If CSV, email to the “send_to” address|send_to=user@domain.com|
 |return|no|Whether to return data or just a count.  Omit to return data.|return=count|
 |count|no|How many items to return|count=100|


* `/reports/users`


|parameter            |required   |value   |example|
|---|---|---|
|us_house|no|US house district|us_house=MT01|
|state_senate|no|State Senate district||
|state_house|no|State House district||
|county_name|no|||
|municipal_name|no|||

Example:
```
/reports/users?us_house=MT01&format=csv&send_to=user@domain.com

```


* `/reports/campaigns`


|parameter            |required   |value   |example|
|---|---|---|
|bipac_id|yes|The string associated with a campaign|bipac_id=internet_freedom

Example:
```
/reports/users?bipac_id=internet_freedom&format=csv&send_to=user@domain.com

```


*  `/reports/letters`


<p class="warning">
  Note: You cannot use the parameters above for this endpoint. Returns JSON
</p>


|parameter            |required   |value   |example|
|---|---|---|
|bipac_id|yes|The string associated with a campaign|bipac_id=internet_freedom|

Example:
```
/reports/letters?bipac_id=internet_freedom

```


 ##### Success Response:

   * ###### Code: 200 <br />
   * ###### Content:


```
   [
      {
        "bipac_id": "urge-state-senators-and-representatives-to-support-sb17-267-state-legislators",
        "email": "jd@example.com",
        "message": "<p>I would like to ask you to Support SB-267.</p>\n<p>SB17-267 will start to fund important transportation and state building infrastructure, while maintaining important funding for rural hospitals.  These are all key issues in building and maintaining a great economy for all Coloradans.</p>\n<p>Please support SB 267!</p>\n<p>Thank you for all your hard work in the legislature this year.</p>\n\n\n\nSincerely\njohn Doe\nSr Project Manager\nExample Company",
        "subject": "Support SB17-267",
        "salutation": "Sincerely",
        "chambers": "a:2:{i:0;s:12:\"state_senate\";i:1;s:11:\"state_house\";}",
        "save": "Y",
        "allow_manual": "Y",
        "test": "N",
        "added": "2017-05-08 10:54:44",
        "issue": "32",
        "status": "1",
        "submission_id": "3",
        "submitted": "2017-05-08 10:55:02",
        "key": null,
        "full_name": "Sen. Irene Aguilar",
        "official_id": "329576",
        "data_1": "CO032",
        "data_2": "Colorado Senate District 32",
        "data_3": "State Legislator",
        "party": "D",
        "gender": "F",
        "chamber": null,
        "first_name": "John",
        "last_name": "Doe",
        "title": "Sr Project Manager",
        "company": "Example Company",
        "telephone": "2025551212",
        "address_1": "123 S Main st",
        "address_2": null,
        "city": "Denver",
        "state": "CO",
        "zip": "80223",
        "prefix": "01",
        "us_senate": null,
        "us_house": null,
        "state_senate": null,
        "state_house": null,
        "county_name": null,
        "municipal_name": null
      }
    ]
```

