# Create Auto Report

## Follow these instructions to create a new Auto Report

1. In the image directory create a new subdir with the client_id as the name 
2. Add the png logo of the client and rename it 1.png (must be 270 px height)
3. Change the title in the config_options of module 31 ( the logo )

```php
<?php

 INSERT INTO auto_report (name, client_id, email, frequency, run_time, start_day, timezone, status_code)
VALUES ('Hollywood Records Weekly YouTube Moderation Rep', 116, 'kees.hessels@icuc.social', 'WEEKLY', '00:00:00', '20016-07-01', 'GMT', 'ACTIVE');


