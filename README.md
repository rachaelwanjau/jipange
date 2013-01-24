# Jipange


This project uses the [Django](https://www.djangoproject.com) framework and is written in [Python](http://www.python.org). It is currently hosted on [Heroku](http://heroku.com) at [http://jipange.herokuapp.com](http://jipange.herokuapp.com), and due to requirements from Heroku, uses [PIP](http://pypi.python.org/pypi/pip) and [VirtualEnv](http://www.virtualenv.org/en/latest/).

### Project Layout

 - `manage.py` This is a script to help run the site and perform tasks related to running it. It is a part of Django.
 - `Procfile` This defines how Heroku (and some other hosting systems) should run the site, most of the time this shouldn't need to be modified.
 - `requirements.txt` This file lists what other code the site depends on, and Heroku uses this to download that code automatically. See below for how to install these dependencies.
 - `jipange.sqlite3` The database file used for development only, you can generally ignore this. Git will ignore this and not deploy it or copy it to the GitHub repository.
 - `messages/` This directory contains the messaging portion of the site.
 - `clinics/` This contains the clinics feedback code.
 - `jipange/` This contains the main site code, including templates.


### Local Setup

For developing the site locally, the following need to be installed:

 - Python 2.7.x
 - PIP
 - VirtualEnv

These can be awkward to set up on Windows, I would recommend Linux or Mac OS. These installation instructions may not work on Windows. These instructions are designed to work in Bash, so if you are on Windows it will work differently, or you will need to install something like [Cygwin](http://www.cygwin.com).

1. Clone the repository from GitHub to your computer.
2. Use the Terminal/Console to move *into* the project directory.
3. Run `virtualenv .` if you have installed VirtualEnv globally, or `python /path/to/virtualenv.py .` if you have installed it locally.
4. Run `source bin/activate` to activate VirtualEnv. **This needs to be run each time you start working on the project again.**
5. Run `pip install -r requirements.txt` to install the dependencies for the project. If you add more dependencies to requirements.txt, make sure to run this command again.

To start the site locally for debugging, run `python manage.py runserver` and access the site at [http://localhost:8000/](http://localhost:8000/).


### SMS

Currently the project uses [Twilio](http://twilio.com), this is a modern, easy to use, and relatively cheap way of sending SMS messages from web applications. At the moment, Twilio only support sending messages. It would be possible to receive messages, but they would have to be sent to an international number which would cost the sender a lot of money.

Pricing for Twilio can be found [here](http://www.twilio.com/sms/pricing/ke):

 - yu Mobile: $0.01 USD
 - Orange: $0.031 USD
 - Airtel: $0.01 USD
 - Safaricom: $0.01 USD

These are the only supported carriers at the moment.


### Notes on CMS and Clinics from Andy

I spent a fair bit of time looking at possible Django plugins to handle the clinic feedback stuff, unfortunately for various reasons it wasn't really feasible in the time.

It's worth noting down for future reference.  It would be nice to be able to add general surveys etc., one of which would be the clinic feedback survey.  For now I've implemented it
as a hard-coded model with specific questions instead.

I tried out django-survey and django-crowdsourcing, but unfortunately after a lot of fiddliness required to make them work at all, it turned out they don't play nicely with Django 1.4.

-- amn
