# <div align="center">oneHourmaid</div>

oneHourmaid is a small project created to post a request containing the users details and home cleaning information. This can then be viewed and replied to over on the Cleaner Account page.

<img align="center" src="static\README_files\readme_heading_img.png">

## User Experience (UX)

The project was designed to lead the user straight to what they're looking for, weather that be to post a request to a cleanerfor Basic or Deep clean, or to view a pending job.

* ### Design
    * ###### Imagery
        - The main background of all pages uses a sunset image taken from [Unsplash.](https://unsplash.com/)
    * ###### Typography
        - The main font throughout is Lato, with Oswald as the as the projects title font and Sans-Serif as a fallback for both.
    * ###### Colour Scheme
        - The colors used are all based off of the main background image. A bright Orange is used for some of the form fields, along with a Dark Slate Grey for the buttons.

* ### Wireframes
    - Main page wireframe - [Here](#)
    - Services wireframe - [Here](#)
    - Basic Clean Wireframe - [Here](#)
    - Deep Clean Wireframe - [Here](#)
    - Cleaner Account Wireframe - [Here](#)

### Features
* #### [Main Page Features](http://127.0.0.1:5000/index)
   - On the main page of the project you can choose between making a request or viewing any pending jobs. Making a request will take you to the services page whereas clicking "Cleaner Account" will show any pending jobs/posts.
<img align="center" src="static\README_files\main_readme.png">

#### Future Features
I would like to add a Register and Sign in page so i can target Cleaners and users with more specific requests and services.
___

* #### [Services Page Features](https://onehourmaid-project.herokuapp.com/services)
  - On the Services page you can choose between requesting a Basic or a Deep clean. Each takes you to a separate form to be filled out to post your request. The mobile view features a carousel instead of the cards seen in the desktop view. The cards give a simple explanation of each option.
<img align="center" src="static\README_files\services_page_rm.png">

#### Future Features
I would like to add another service called "Moving In/Out", there, you would have the choice of having a full deep clean for the home your moving in to or the property you're moving out of.
___

* #### [Basic Clean Page Features](https://onehourmaid-project.herokuapp.com/basic_clean_info)
  - The Basic Clean page contains a simple form to be filled out with the Users information including, address of cleaning location and details of their cleaning needs i.e *"Please can you vacuum throughout."* You must also enter a valid email address in order to receive your confirmation email. This form is then posted in the [Cleaner Account](https://onehourmaid-project.herokuapp.com/cleaner_account) section to be viewed and responded to by the cleaner.
<img align="center" src="static\README_files\basic_clean.png">

#### Future Features
On the Basic Clean page I would like to be able to target specific cleaners based on how they registered, eg. if you registered as a Basic Cleaner, you will only receive the Basic Clean requests.
___

* #### [Deep Clean Page Features](https://onehourmaid-project.herokuapp.com/deep_clean_info)
  - The Deep Clean page is to post a more in depth request. Here, as in the Basic Clean form, you must fill out the form with your details and a short message containing your cleaning needs, you also have the choice of requesting a deep Carpet Clean, Floor Steam, White Goods (cleaning behind ovens, fridges etc.) or simply get your Windows cleaned! You must also give a valid email address to receive the confirmation message, This request will also be posted in the [Cleaner Account](https://onehourmaid-project.herokuapp.com/cleaner_account) section.
<img align="center" src="static\README_files\deep_clean.png">

#### Future Features
As the same with the Basic Clean page, I would like to be able to target specific cleaners based on the cleaning request. Also, i would like to be able to send more detailed and personalised confirmation messages.
___

* #### [Cleaner Account Page Features](https://onehourmaid-project.herokuapp.com/cleaner_account)
  - The Cleaner Account page is where you can view any requests made for either a Basic or Deep clean. Each job card will contain a tag reading either "Basic Clean" or "Deep Clean" to identify the type of post. Clicking on a job card will expand to display the rest of the request details including the users address and message. The Deep Clean job card will show the more in depth clean request, including what they would like deep cleaned i.e Carpets, Windows etc. You also have the options to edit or delete your request. Clicking the "Send Confirmation" button will send a confirmation email to the users address.
<img align="center" src="static\README_files\cleaner_account.png">

#### Future Features
On the Cleaner Account page, I would like the ability for cleaners to only see jobs sent to them based on how they registered. I would also like to implement a better response function instead of a plain confirmation message. At the moment the jobs stay in the list once set to "Job complete," if given more time I would've liked to have a "yes/no" modal appear to give the cleaner a choice of deleting a request or not.
___

### <div align="center">Libraries & Frameworks</div>


##### MaterializeCSS
I used [MaterializeCSS](https://materializecss.com/) for all of the forms, this helped alot for speed purpose, but does make styling buttons and popups etc. a little tricky. That being said, Materialize is easy to use and great for forms, buttons and grids.

##### Flask & Python3
[Flask](https://flask.palletsprojects.com/en/1.1.x/) and [Python3](https://www.python.org/download/releases/3.0/) were used to send and receive data from [MongoDB.](https://www.mongodb.com/) ```@app.route``` was used throughout to navigate to pages and to trigger the actions on forms and buttons. The [Jinja2](https://jinja.palletsprojects.com/en/2.11.x/) template language was used alongside Flask to add and manipulate data in the HTML files, known to Jinja as "Templates."
- ###### Libraries used in Python3:
  - **flask_pymongo**
    *used to send and receive data from MongoDB*
  - **bson.objectid**
    *used to make changes to the database entries ```_id```*
  - **smtplib**
    *used to send the confirmation email fom the cleaner account*
  - **email.message**
    *used to send the confirmation email fom the cleaner account*
___

### <div align="center">Testing & Bugs</div>

##### Bug: Fixed Locally, not working on Heroku [FIXED]

Heroku having issues finding URL to edit MongoDB post. Works fine locally. Checked "Config Vars" in Heroku to make sure all keys are correct and in place. The logs show that the error is with accessing the URL *https://onehourmaid-project.herokuapp.com/basic_clean_info?request_id=*
```
HEROKU LOGS [error]

4pWNosP85CsCvMJj1bILOnhlp68mclIoxZ7wfQg\n5.7.14 1jUR4IzTlyTZI0wx_ka5nD64ZjproXT401-euojiTE3OcAhvYC8el6BAnmfH6GkB>\n5.7.14 Please log in via your web browser and then try again.\n5.7.14  Learn more at\n5.7.14  https://support.google.com/mail/answer/78754 l19sm2432751qtu.16 - gsmtp')
2020-09-09T09:18:28.055462+00:00 app[web.1]: 10.93.223.38 - - [09/Sep/2020:09:18:28 +0000] "POST /basic_clean_info?request_id= HTTP/1.1" 500 290 "https://onehourmaid-project.herokuapp.com/basic_clean_info" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.83 Safari/537.36"
2020-09-09T09:18:28.058053+00:00 heroku[router]: at=info method=POST path="/basic_clean_info?request_id=" host=onehourmaid-project.herokuapp.com request_id=4f03faeb-1596-4792-a4ee-95dbe31b3d55 fwd="176.26.119.21" dyno=web.1 connect=0ms service=1596ms status=500 bytes=470 protocol=https
2020-09-09T09:18:28.337326+00:00 app[web.1]: 10.93.223.38 - - [09/Sep/2020:09:18:28 +0000] "GET /favicon.ico HTTP/1.1" 404 232 "https://onehourmaid-project.herokuapp.com/basic_clean_info?request_id=" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.83 Safari/537.36"
2020-09-09T09:18:28.339433+00:00 heroku[router]: at=info method=GET path="/favicon.ico" host=onehourmaid-project.herokuapp.com request_id=29b37684-aea0-4fbd-9e90-1527f2a40744 fwd="176.26.119.21" dyno=web.1 connect=0ms service=2ms status=404 bytes=400 protocol=https
```
[FIXED] - Issue was not with MongoDB or Heroku, bug came from not having set up an "App Secure Password" with gmail for the auto email that sends out when the request is made.
```
2020-09-09T12:57:07.389853+00:00 app[web.1]: smtplib.SMTPAuthenticationError: (534, b'5.7.14 <https://accounts.google.com/signin/continue?sarp=1&scc=1&plt=AKgnsbs\n5.7.14 srUuNDQdOeyso_sU31unv0si9awF-KWMJ3V5GRNN9FAfIM9LqUjVraLV-G_Yv_UcAKwh2\n5.7.14 6JZTr47JO3w6ydDb7qqxoBbdzfIV0nQEpLCT-fZkYcmX9OH-xog-XrOKLTbVsr9_>\n5.7.14 Please log in via your web browser and then try again.\n5.7.14  Learn more at\n5.7.14  https://support.google.com/mail/answer/78754 m6sm2477223qkh.106 - gsmtp')
```
Tested by sending auto emails to different addresses to confirm they sent as expected.
___

### <div align="center">Future Project Implementations</div>

There were many functions I would have loved implemented in this project but unfortunately didn't have the time. I would like to make the "Cleaner Account" page a lot more intuitive with features such as responding directly to a User regarding their post/request. Originally, the project included both a sign in and register page, this was my first attempt and making the requests more personalised based on how the User registered, unfortunately this had to be taken away for time purposes.

### <div align="center">Credits</div>

##### Media:
- The main background image was taken by Adel Gordon and downloaded from [Unsplash.](https://unsplash.com/photos/2MIbJa4lVtI)