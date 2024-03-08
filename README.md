# pf-personal-health-optimization
track your behaviour affecting your health and apply different analysis including prediction

[README Deutsch](./README-DE.md)

The data workflow is:

1) keep original data so that once interpretation changes it can be redone

2) allow post processing steps and analysis (according to dr who, why own, USA
   FDA, World food organization, ..)
   so that different ways to seet he data can be configured

```
    INPUT TYPES (configurable)
      images  (what=image, date, image)
      images  (what=qr_codes_from_grocery_shopping, date, image)
      // video  (what=video, date, ?) -> no use case yet cause processing complex but we can allow it
      speech (what=singing_recording, date, voice-recording)
      text (what=regular_log, date, text)
      value  (what=laughed, date, number)
      value  (what=sit_ups, date, number)
      value  (what=custom_table, custom_table(nr situps, nr curl, nr, ..), table)
      value  (what=mediated, date, 2h)
      table  (what=scientific_food_tracking, date, table) # 30 g eggs, ....
      table  (what=food_bought, date, table) # 30 g eggs, 1l milk, ...
      table  (what=mobile_phone_activity, date, date_ranges[]) # 30 g eggs, 1l milk, ...

    Configuring processed-inputs
      speech -> text (what=regular_log)
      sleeping times from text INPUTS= (what=regular_log), (what=mobile_phone_activity)
      food from text
      food from scientific_food_tracking
      food from food_bought
      qr_code_from_grocey_shopping -> list_of_incredients

    Configuring analysis:
      judge intredients -> compare after DR X -> analyse deficits

```
