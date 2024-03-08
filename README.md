# pf-personal-health-optimization
track your behaviour affecting your health and apply different analysis including prediction

[README Deutsch](./README-DE.md)

The data workflow is:

1) keep original data so that once interpretation changes it can be redone

2) allow post processing steps and analysis (according to dr who, why own, USA
   FDA, World food organization, ..)
   so that different ways to seet he data can be configured

```
    INPUT TYPES (configurable), each eventually have a used by (user, module-x, module-y)
      images  (what=image, date, image)
      images  (what=qr_codes_from_grocery_shopping, date, image)
      // video  (what=video, date, ?) -> no use case yet cause processing complex but we can allow it
      speech (what=singing_recording, date, voice-recording)
      text (what=regular_text_log, date, text)
      value  (what=laughed, date, number)
      value  (what=sit_ups, date, number)
      value  (what=custom_table, custom_table(nr situps, nr curl, nr, ..), table)
      value  (what=mediated, date, 2h)
      table  (what=scientific_food_tracking, date, table) # 30 g eggs, ....
      table  (what=food_bought, date, table) # 30 g eggs, 1l milk, ...
      table  (what=mobile_phone_used, date, date_ranges[]) # 30 g eggs, 1l milk, ...
      gps_tracking  (what=movement_tracker, ..., gps_tracking)

    Configuring processed-inputs
      speech -> text (what=regular_text_log)
      sleeping times from text INPUTS= (what=regular_text_log), (what=mobile_phone_activity)
      food from text
      food from scientific_food_tracking
      food from food_bought
      qr_code_from_grocey_shopping -> list_of_incredients

    Configuring analysis:
      judge intredients -> compare after DR X -> analyse deficits

```

Ready made modules:
Because congfiguring all of that is complex a module is

    * input (eg regular_text_log) -> which direct user feedback hooks (you missed out telling how you feel)
    * processing
    * display
    * analysis

Example modules

    Fasting_Schedule_Tracking
        regular fasting (Dr Seyfried etc)
        might have health benefit if you do it moderately

    Sleeping_Time
        inputs: 
            regular_text_log
            mobile phone active -> interruption_time_range
        processing: (GPT: If you find sleeping or nap time output it in format UP: 8:00, DOWN: 16:00)
        show_in_calendar

    Wellbeing_From_Text
        inputs: regular_text_log
        GPT: find "feeling well, not well whatever")

    Food_From_Images:

    Food_From_Bills:

    Food_From_Tables:

    Sport_From_Movement:
        ..

    Allergie_Analysis
        inputs:
            Pollenflug
            food
            location GPS ?

    Teeth_Check:
        When biting your teeth which one move ?

    Gum check:
        recession ?

    Blood suggar level prediction based on food
        (maybe with measurement)

    sauna walks reminder


TestBrainHealthGrayPattern
    show gray patterns which can hardly be seen.
    The better your blood flow the faster your reception

TestBrainHealthRecall
    Show 30 image pairs (very fast)
    Then ask whether pairs were shown together?
    Number of failures and/or recall time 
    -> health

SOURCES:
https://www.naehrwertrechner.de/
https://www.nutricia-metabolics.de/service/informationen-fuer-den-alltag/bestellformular-aminosaeurentabelle/
