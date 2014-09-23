economic-py
===========

# About
These few files were created to help automatically pre fill Economic.
Entries are based on Google calendar events and JIRA tasks currently assigned
to user and matching configurable filter. Duplicates are checked by
looking at task description (Economic) so it's safe to run this command
as many times a day as needed.

# Installation
Make sure you have `pip` installed on your system by calling:
`sudo apt-get install -y python-pip`

Once `pip` is installed run command below to install all required python libraries:
`sudo pip install -r requirements.txt`

After that `config.ini.dist` to `config.ini` and update it with all required
credentials for JIRA, Economic and Google account.

# Usage
Calling `python run.py` will create all economic entries for today.
What's left it to update hours spent on each task in economic.

Due to application's limitations (see below) it advised to add new entry
in crontab to make sure all tasks will be registered:
`1 8-17 * * 1-5 root python /path/to/run.py >/dev/null 2>&1`

# Known limitations
* adding JIRA tasks for day other than current is not supported (might be tricky),
* adding Google calendar events for day other than today is not supported (easy to implement)
* time reported in JIRA is not exported to economic yet