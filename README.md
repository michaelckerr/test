# Create Auto Report

## Follow these instructions to create a new Auto Report

1. Insert a new record in the auto_report table for the new report and remember the new report_id.
2. Copy auto_report_module records belonging to the source report 
3. and insert them in the same table with an updated report_id
4. In the image directory create a new subdir with the client_id as the name 
5. Add the png logo of the client and rename it 1.png (must be 270 px height)
6. Change the title in the config_options of module 31 ( the logo )

```php
<?php

 INSERT INTO auto_report (name, client_id, email, frequency, run_time, start_day, timezone, status_code)
VALUES ('Hollywood Records Weekly YouTube Moderation Rep', 116, 'kees.hessels@icuc.social', 'WEEKLY', '00:00:00', '20016-07-01', 'GMT', 'ACTIVE');


CREATE TEMPORARY TABLE temp_AR_table
AS
SELECT * FROM auto_report_module WHERE id=4;
UPDATE temp_AR_table SET id=NULL' WHERE id=4;
INSERT INTO auto_report_module SELECT * FROM temp_AR_table;
DROP TEMPORARY TABLE temp_AR_table;


