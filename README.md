# Sharks Ice Schedule Sync Tool

A quick and dirty sync tool that will pull in all the games scheduled for your hockey teams at Sharks Ice San Jose,
Sharks Ice Fremont, and the NCWHL and add them to a Google calendar.

## Dependencies / Setup

Requires python 2.x and [pip](https://pypi.python.org/pypi/pip)

Run the following command (may need to use sudo depending on your system).
> pip install --upgrade BeautifulSoup google-api-python-client pytz argparse

Open the _config.cfg_ file and edit the teams property for your particular rink (comma separated, as they appear on the stat page)

## Running

You'll need to obtain client credentials for the app -- [follow the instructions provided by Google](https://developers.google.com/api-client-library/python/auth/installed-app#creatingcred)
and put the credentials (renamed to client_secret.json) in the root of the project.  Specifically:

1.  Go to https://console.developers.google.com/
2.  Create a New Project
3.  Name your new project whatever you want.
4.  On the left sidebar, click on "APIs & Auth."
5.  You need to add "Calendar API" to your list by searching for it and toggling its state to "On" (click the button at right).
6.  Click on "Credentials" on the left sidebar.
7.  Click "Create new Client ID."
8.  Select "Installed Application" and then "Other" for Application Type.
9.  Enter your email address and a name for the credentials, then click "OK."
10.  Click on "Download JSON File."
11.  Change the name of the file to "client_secret" and download it.
12.  Move the file into the same folder as all of the Parser files, and you're done!

Then just run
> python ScheduleRipper.py

The first run will prompt you for authorization to your google account and ask which calendar you'd like to sync the
events to.  Every run afterwards will use the stored credentials and settings to run without intervention (making it
usable for cron jobs)

## To do:

- Add a connector for Ice Oasis' Google Calendar
- Add functionality for Toyota Sports Center leagues