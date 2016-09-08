# Create Auto Report

## Follow these instructions to create a new Auto Report

1. Insert a new record in the auto_report table for the new report and remember the new report_id.
2. Copy auto_report_module records belonging to the source report 
3. and insert them in the same table with an updated report_id
4. In the image directory create a new subdir with the client_id as the name 
5. Add the png logo of the client and rename it 1.png (must be 270 px height)
6. Change the title in the config_options of module 31 ( the logo )

```php


 

queries for auto_report_modules below

INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33', 160, '{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[729],"style-elements":[{"margin-top":"25px"}],"force_new_page":"YES"}', 'ACTIVE');



0 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('31', '0', '{"title":"Hollywood Records<br>Weekly Instagram Moderation Report", "sub_title":"Reporting dates: {$dates_reporting}",
"streams":[619,620],
"height_image_client":"35px", "text_margin_left":"100px","style-elements":[{"margin-left":"75px"}]}', 'ACTIVE');


1 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33','1', '{"title":"Rejection Overview", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"8px"}]}', 'ACTIVE');

2 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('27', '2', '{"title":"Rejections by Page", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

3 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('28', '3', '{"title":"Rejections by Date", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

4 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('26', '4', '{"title":"", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

5 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33', '5', '{"title":"Rejections Breakdown", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

6 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('22', '6', '{"title":"Rejections by Reason", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

7 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('21', '7', '{"title":"Rejections by Reason", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

8 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('18', '8', '{"title":"", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

9 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33', '10', '{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"22px"}],"force_new_page":"YES"}', 'ACTIVE');

10 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('28', '12', '{"title":"Rejections by Day", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

11 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('21', '14', '{"title":"Rejections by Reason", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

12 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('18', '16', '{"title":"", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

13 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33', '20', '{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}],"force_new_page":"YES"}', 'ACTIVE');

14 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('28', '22', '{"title":"Rejections by Day", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

15 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('21', '24', '{"title":"Rejections by Reason", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

16 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('18', '26', '{"title":"", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

17 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('23', '350', '{"title":"", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}], "max-rows":"5", "max-chars-per-entry":"1000"}', 'ACTIVE');

18 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('23', '351', '{"title":"", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}], "max-rows":"5", "max-chars-per-entry":"1000"}', 'ACTIVE');




















SELECT  `id`,  `name`,  `client_id`,  `client_visible`,  `email`,  `frequency`,  `run_time`,  `start_day`,  `timezone`,  `status_code`,  `error_count`,  LEFT(`last_error`, 256),  LEFT(`config_options`, 256) FROM `social_patrol_primary`.`auto_report` LIMIT 1000;
















































































Document & Knowledge Transfer - Auto Report Generation
-------

#### _This document contains steps on how to_: 
- Add a new Auto Report based on an existing report
- Add modules for the Auto Report we added
- Update an Auto Report recipients list


----------


## Adding a new Auto Report based on an existing report
***Script:*** 
`UPDATE auto_report SET email = EMAIL_ADDRESSES WHERE id = REPORT_ID`
`INSERT INTO auto_report (name, client_id, client_visible, email, frequency, run_time, start_day, timezone, status_code, error_count, last_error, config_options)
SELECT  REPORT_NAME, CLIENT_ID, client_visible, EMAIL_ADDRESSES, frequency, run_time, start_day, timezone, status_code, error_count, last_error, config_options FROM auto_report WHERE id=REPORT_ID`


The variables in UPPERCASE should be changed with values we want to insert.

> REPORT_NAME : *Report Name*
CLIENT_ID : *Client Id for this report*
EMAIL_ADDRESSES : *email addresses that will receive the report, should be comma seperated; **example**: email1@icuc.social, email2@icuc.social*


----------


**Example:**
Here, I'm going to clone a report with the id = 4, and create a new report out of it with the name "Hello World Report", and a client id "5", and as for the email addresses, it will be "ahmed.mohamed@icuc.social, kees.hessels@icuc.social, michael.kerr@icuc.social".

`INSERT INTO auto_report (name, client_id, client_visible, email, frequency, run_time, start_day, timezone, status_code, error_count, last_error, config_options)
SELECT  "Hello World Report", 5,client_visible,"ahmed.mohamed@icuc.social, kees.hessels@icuc.social, michael.kerr@icuc.social", frequency, run_time, start_day, timezone, status_code, error_count, last_error, config_options FROM auto_report WHERE id=4`

----------

## Add modules for the Auto Report we added
***Script:*** 
`INSERT INTO auto_report_module (report_id, module_id, sort_order, config_options, status_code) SELECT NEW_REPORT_ID, module_id, sort_order, config_options, status_code WHERE report_id = REPORT_ID;`

The variables in UPPERCASE should be changed with values we want to insert.

> NEW_REPORT_ID : *This is the ID of the new auto report we just added.*
REPORT_ID : *The ID of the report we copied*


**Example:**
After adding the Auto Report, now we need to add the modules of this new report. In the previous example, REPORT_ID was = 4, so this is what we're going to use for REPORT_ID. As for the NEW_REPORT_ID, we should get the ID for the last auto report we just created.

In order to get the ID of the last entry in the auto_report table, we use the following script:
`SELECT id FROM auto_report ORDER BY id DESC LIMIT 1`

And then we use the value we get for NEW_REPORT_ID. (Just for this example, I will use 9 as the ID returned)

`INSERT INTO auto_report_module (report_id, module_id, sort_order, config_options, status_code) SELECT 9, module_id, sort_order, config_options, status_code WHERE report_id = 4;`

Now, we need to check that we really have modules for this report.
Script:
`SELECT * FROM auto_report_module WHERE report_id = NEW_REPORT_ID`

For this example:
`SELECT * FROM auto_report_module WHERE report_id = 9`

----------


## Updating Auto Report recipients list
**Script:**
`UPDATE auto_report SET email = EMAIL_ADDRESSES WHERE id = REPORT_ID`


The variables in UPPERCASE should be changed with values we want to update.

> EMAIL_ADDRESSES : *email addresses that will receive the report, should be comma seperated; **example**: email1@icuc.social, email2@icuc.social*


----------

**Example:**
In order to update an Auto Report recipients list, we need first to know the REPORT_ID. In this example, I'm going to update the email list of an auto report with id = 9;

`UPDATE auto_report SET email = "ahmed.mohamed@icuc.social" WHERE id = 9`

Pretty simple, right?
Now let's do the same for multiple email addresses:
`UPDATE auto_report SET email = "ahmed.mohamed@icuc.social, michael.kerr@icuc.social" WHERE id = 9`

Nothing much changed, I added a comma and then the other email address.

----------


# Create Auto Report

## Follow these instructions to create a new Auto Report

1. Insert a new record in the auto_report table for the new report and remember the new report_id.
2. Copy auto_report_module records belonging to the source report 
3. and insert them in the same table with an updated report_id
4. In the image directory create a new subdir with the client_id as the name 
5. Add the png logo of the client and rename it 1.png (must be 270 px height)
6. Change the title in the config_options of module 31 ( the logo )

```php


 

queries for auto_report_modules below

INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33', 160, '{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[729],"style-elements":[{"margin-top":"25px"}],"force_new_page":"YES"}', 'ACTIVE');



0 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('31', '0', '{"title":"Hollywood Records<br>Weekly Instagram Moderation Report", "sub_title":"Reporting dates: {$dates_reporting}",
"streams":[619,620],
"height_image_client":"35px", "text_margin_left":"100px","style-elements":[{"margin-left":"75px"}]}', 'ACTIVE');


0 done
UPDATE auto_report_module SET config_options='{"title":"Hollywood Records<br>Weekly Instagram Moderation Report", "sub_title":"Reporting dates: {$dates_reporting}",
"streams":[619,620],
"height_image_client":"35px", "text_margin_left":"100px","style-elements":[{"margin-left":"75px"}]}' WHERE report_id=2 And sort_order=0;




1 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33','1', '{"title":"Rejection Overview", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"8px"}]}', 'ACTIVE');

1 done
UPDATE auto_report_module SET config_options='{"title":"Rejection Overview", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"8px"}]}' WHERE report_id=2 And sort_order=1;


2 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('27', '2', '{"title":"Rejections by Page", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');
2 done
UPDATE auto_report_module SET config_options='{"title":"Rejections by Page", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' WHERE report_id=2 And sort_order=2;


3 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('28', '3', '{"title":"Rejections by Date", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

3 done
UPDATE auto_report_module SET config_options='{"title":"Rejections by Date", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' WHERE report_id=2 And sort_order=3;

4 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('26', '4', '{"title":"", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

4 done
UPDATE auto_report_module SET config_options='{"title":"", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' WHERE report_id=2 And sort_order=4;


5 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33', '5', '{"title":"Rejections Breakdown", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

5 done
UPDATE auto_report_module SET config_options='{"title":"Rejections Breakdown", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' WHERE report_id=2 And sort_order=5;

6 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('22', '6', '{"title":"Rejections by Reason", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

6 done
UPDATE auto_report_module SET config_options='{"title":"Rejections by Reason", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' WHERE report_id=2 And sort_order=6;

7 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('21', '7', '{"title":"Rejections by Reason", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

7 done
UPDATE auto_report_module SET config_options='{"title":"Rejections by Reason", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' WHERE report_id=2 And sort_order=7;



8 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('18', '8', '{"title":"", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}', 'ACTIVE');

8
UPDATE auto_report_module SET config_options='{"title":"", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' WHERE report_id=2 And sort_order=8;



9 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33', '10', '{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"22px"}],"force_new_page":"YES"}', 'ACTIVE');

9 done
UPDATE auto_report_module SET config_options='{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"22px"}],"force_new_page":"YES"}' WHERE report_id=2 And sort_order=10;


10 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('28', '12', '{"title":"Rejections by Day", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

10 done
UPDATE auto_report_module SET config_options='{"title":"Rejections by Day", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}' WHERE report_id=2 And sort_order=12;


11 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('21', '14', '{"title":"Rejections by Reason", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

11 done
UPDATE auto_report_module SET config_options='{"title":"Rejections by Reason", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}' WHERE report_id=2 And sort_order=14;


12 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('18', '16', '{"title":"", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

12 done
UPDATE auto_report_module SET config_options='{"title":"", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}' WHERE report_id=2 And sort_order=16;

13 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('33', '20', '{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}],"force_new_page":"YES"}', 'ACTIVE');

13 done
UPDATE auto_report_module SET config_options='{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}],"force_new_page":"YES"}' WHERE report_id=2 And sort_order=20;



14 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('28', '22', '{"title":"Rejections by Day", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

14 done
UPDATE auto_report_module SET config_options='{"title":"Rejections by Day", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}' WHERE report_id=2 And sort_order=22;

15 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('21', '24', '{"title":"Rejections by Reason", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

15 done
UPDATE auto_report_module SET config_options='{"title":"Rejections by Reason", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}' WHERE report_id=2 And sort_order=24;

16 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('18', '26', '{"title":"", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}', 'ACTIVE');

16 done
UPDATE auto_report_module SET config_options='{"title":"", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}' WHERE report_id=2 And sort_order=26;

17 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('23', '350', '{"title":"", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}], "max-rows":"5", "max-chars-per-entry":"1000"}', 'ACTIVE');

17 done
UPDATE auto_report_module SET config_options='{"title":"", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}], "max-rows":"5", "max-chars-per-entry":"1000"}' WHERE report_id=2 And sort_order=350;

18 done
INSERT INTO auto_report_module (module_id, sort_order, config_options, status_code)
VALUES ('23', '351', '{"title":"", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}], "max-rows":"5", "max-chars-per-entry":"1000"}', 'ACTIVE');

18 done
UPDATE auto_report_module SET config_options='{"title":"", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}], "max-rows":"5", "max-chars-per-entry":"1000"}' WHERE report_id=2 And sort_order=351;


# Create Auto Report

## Follow these instructions to create a new Auto Report

1. Insert a new record in the auto_report table for the new report and remember the new report_id.
2. Copy auto_report_module records belonging to the source report 
3. and insert them in the same table with an updated report_id
4. In the image directory create a new subdir with the client_id as the name 
5. Add the png logo of the client and rename it 1.png (must be 270 px height)
6. Change the title in the config_options of module 31 ( the logo )




queries for auto_report_modules below
```php

UPDATE auto_report_module 
SET config_options='{"title":"Hollywood Records<br>Weekly Instagram Moderation Report", "sub_title":"Reporting dates: {$dates_reporting}",
"streams":[619,620],
"height_image_client":"35px", "text_margin_left":"100px","style-elements":[{"margin-left":"75px"}]}' 
WHERE report_id=2 
AND sort_order=0;


UPDATE auto_report_module 
SET config_options='{"title":"Rejection Overview", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"8px"}]}' 
WHERE report_id=2 
AND sort_order=1;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections by Page", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' 
WHERE report_id=2 
AND sort_order=2;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections by Date", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' 
WHERE report_id=2 
AND sort_order=3;


UPDATE auto_report_module 
SET config_options='{"title":"", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' 
WHERE report_id=2 
AND sort_order=4;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections Breakdown", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' 
WHERE report_id=2 
AND sort_order=5;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections by Reason", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' 
WHERE report_id=2 
AND sort_order=6;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections by Reason", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' 
WHERE report_id=2 
AND sort_order=7;


UPDATE auto_report_module 
SET config_options='{"title":"", "sub_title":"","streams":[619,620],"style-elements":[{"margin-top":"22px"}]}' 
WHERE report_id=2 
AND sort_order=8;


UPDATE auto_report_module 
SET config_options='{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"22px"}],"force_new_page":"YES"}' 
WHERE report_id=2 
AND sort_order=10;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections by Day", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}' WHERE report_id=2 
AND sort_order=12;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections by Reason", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}' 
WHERE report_id=2 
AND sort_order=14;


UPDATE auto_report_module 
SET config_options='{"title":"", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}]}' 
WHERE report_id=2 
AND sort_order=16;


UPDATE auto_report_module 
SET config_options='{"title":"{$stream_name} {$source_code} Overview", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}],"force_new_page":"YES"}' 
WHERE report_id=2 
AND sort_order=20;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections by Day", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}' WHERE report_id=2 
AND sort_order=22;


UPDATE auto_report_module 
SET config_options='{"title":"Rejections by Reason", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}' 
WHERE report_id=2 
AND sort_order=24;


UPDATE auto_report_module 
SET config_options='{"title":"", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}]}' 
WHERE report_id=2 
AND sort_order=26;


UPDATE auto_report_module 
SET config_options='{"title":"", "sub_title":"","streams":[619],"style-elements":[{"margin-top":"25px"}], "max-rows":"5", "max-chars-per-entry":"1000"}' 
WHERE report_id=2 
AND sort_order=350;


UPDATE auto_report_module 
SET config_options='{"title":"", "sub_title":"","streams":[620],"style-elements":[{"margin-top":"25px"}], "max-rows":"5", "max-chars-per-entry":"1000"}' 
WHERE report_id=2 
AND sort_order=351;




