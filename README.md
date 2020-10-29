![Marvel](https://i.imgur.com/mXpnO7n.jpg)
# Marvel
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/6141417ceaf84545bab6bd671503df51)](https://app.codacy.com/gh/noobanon/Marvel?utm_source=github.com&utm_medium=referral&utm_content=noobanon/Marvel&utm_campaign=Badge_Grade_Settings)  [![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity) [![GPLv3 license](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://perso.crans.org/besson/LICENSE.html) [![Open Source](https://badges.frapsoft.com/os/v2/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://makeapullrequest.com) [![Updates channel!](https://img.shields.io/badge/Join%20Channel-!-red)](https://t.me/ThebotSupport)

<code> THIS CODE FREE TO USE BUT YOUR FORK MUST BE PUBLIC UNDER License-GPLv3 IF USED AS PRIVATE WE WILL GBAN YOU OFF </code>
<br>[![Suoport Group!](https://img.shields.io/badge/Support%20Group-!-red)](https://t.me/ThebotSupports)
# Marvel-English
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/noobanon/missmarvel)

# Deploy This Bot Manual by @noobanon

<b>If deploy button not gonna work or you getting deploy error use this method</b>

Create a app in heroku and fork this repo then  connect to your github account and deploy

after successfully deploy goto setting and fill This Given Value in Your Config Vars

<br><code> KEY = OWNER_ID | VALUE = YOUR USER ID </code> <br>
<br><code> KEY = OWNER_USERNAME | VALUE = YOUR USER NAME </code> 
<br><code> KEY = SUDO_USERS | VALUE = YOUR SUDO USERS ID </code>
<br><code> KEY = SUPPORT_USERS | VALUE = YOUR SUPPORT USERS ID </code>
<br><code> KEY = WHITELIST_USERS | VALUE = YOUR WHITELISTED USERS ID <code><br>
<br><code> KEY = ENV | VALUE = ANYTHING </code></br>
<br><code> KEY = DEL_CMDS | VALUE = True </code></br>
<br><code> KEY = MESSAGE_DUMP | VALUE = EXAMPLE " USE CHAT ID MUST PRIVATE " </code></br>
<br><code> KEY = ALLOW_EXCL | VALUE = True </code><br>
<br><code> KEY = TOKEN | VALUE = YOUR BOT TOKEN FOR BOT FATHER </code><br>
<br><code> KEY = STRICT_GBAN | VALUE = True </code><br>
<br><code> KEY = PORT | VALUE = 8443 </code><br>

# NOTE DON'T FORGET TO ADD DATABASE ADD ON HEROKU POSGRES THEN TURN ON WORKER
# Thanks To 
Pual Larson [ Maria Creator ]
Ayra Hikari [Fed V2 + Best Source Updater ]
MR ANON [ Marvel Mentioner ]
AND MANY MORES

# Report Bug
ANY BUG RELATED QUESTION ASK ME HERE
[Support Group](https://t.me/TheBotSupports)


A modular telegram Python bot running on python3 with an sqlalchemy database.

Originally a simple group management bot with multiple admin features, it has evolved, becoming extremely modular and 
simple to use.

Can be found on telegram as [Marvel](https://t.me/MissMarvel_bot). 

Menhera and I are moderating a [support group](https://t.me/ThebotSupports), where you can ask for help setting up your
bot, discover/request new features, report bugs, and stay in the loop whenever a new update is available. Of course
I'll also help when a database schema changes, and some table column needs to be modified/added. Note to maintainers that all schema changes will be found in the commit messages, and its their responsibility to read any new commits.

Join the [news channel](https://t.me/TheBotSupport) if you just want to stay in the loop about new features or
announcements.

Alternatively, [find me on telegram](https://t.me/noobanon)! (Keep all support questions in the support chat, where more people can help you.)

## Starting the bot.

Once you've setup your database and your configuration (see below) is complete, simply run:

`python3 -m marvel`


## Setting up the bot (Read this before trying to use!):
Please make sure to use python3.6, as I cannot guarantee everything will work as expected on older python versions!
This is because markdown parsing is done by iterating through a dict, which are ordered by default in 3.6.

### Configuration

There are two possible ways of configuring your bot: a config.py file, or ENV variables.

The prefered version is to use a `config.py` file, as it makes it easier to see all your settings grouped together.
This file should be placed in your `marvel` folder, alongside the `__main__.py` file . 
This is where your bot token will be loaded from, as well as your database URI (if you're using a database), and most of 
your other settings.

It is recommended to import sample_config and extend the Config class, as this will ensure your config contains all 
defaults set in the sample_config, hence making it easier to upgrade.

An example `config.py` file could be:
```
from marvel.sample_config import Config


class Development(Config):
    OWNER_ID = 1091139479  # my telegram ID
    OWNER_USERNAME = "noobanon"  # my telegram username
    API_KEY = "your bot api key"  # my api key, as provided by the botfather
    SQLALCHEMY_DATABASE_URI = 'postgresql://username:password@localhost:5432/database'  # sample db credentials
    MESSAGE_DUMP = '-' # some group chat that your bot is a member of
    USE_MESSAGE_DUMP = True
    SUDO_USERS = [/]  # List of id's for users which have sudo access to the bot.
    LOAD = []
    NO_LOAD = ['translation']
```

If you can't have a config.py file (EG on heroku), it is also possible to use environment variables.
The following env variables are supported:
 - `ENV`: Setting this to ANYTHING will enable env variables

 - `TOKEN`: Your bot token, as a string.
 - `OWNER_ID`: An integer of consisting of your owner ID
 - `OWNER_USERNAME`: Your username

 - `DATABASE_URL`: Your database URL
 - `MESSAGE_DUMP`: optional: a chat where your replied saved messages are stored, to stop people deleting their old 
 - `LOAD`: Space separated list of modules you would like to load
 - `NO_LOAD`: Space separated list of modules you would like NOT to load
 - `WEBHOOK`: Setting this to ANYTHING will enable webhooks when in env mode
 messages
 - `URL`: The URL your webhook should connect to (only needed for webhook mode)

 - `SUDO_USERS`: A space separated list of user_ids which should be considered sudo users
 - `SUPPORT_USERS`: A space separated list of user_ids which should be considered support users (can gban/ungban,
 nothing else)
 - `WHITELIST_USERS`: A space separated list of user_ids which should be considered whitelisted - they can't be banned.
 - `DONATION_LINK`: Optional: link where you would like to receive donations.
 - `CERT_PATH`: Path to your webhook certificate
 - `PORT`: Port to use for your webhooks
 - `DEL_CMDS`: Whether to delete commands from users which don't have rights to use that command
 - `STRICT_GBAN`: Enforce gbans across new groups as well as old groups. When a gbanned user talks, he will be banned.
 - `WORKERS`: Number of threads to use. 8 is the recommended (and default) amount, but your experience may vary.
 __Note__ that going crazy with more threads wont necessarily speed up your bot, given the large amount of sql data 
 accesses, and the way python asynchronous calls work.
 - `BAN_STICKER`: Which sticker to use when banning people.
 - `ALLOW_EXCL`: Whether to allow using exclamation marks ! for commands as well as /.

### Python dependencies

Install the necessary python dependencies by moving to the project directory and running:

`pip3 install -r requirements.txt`.

This will install all necessary python packages.

### Database

If you wish to use a database-dependent module (eg: locks, notes, userinfo, users, filters, welcomes),
you'll need to have a database installed on your system. I use postgres, so I recommend using it for optimal compatibility.

In the case of postgres, this is how you would set up a the database on a debian/ubuntu system. Other distributions may vary.

- install postgresql:

`sudo apt-get update && sudo apt-get install postgresql`

- change to the postgres user:

`sudo su - postgres`

- create a new database user (change YOUR_USER appropriately):

`createuser -P -s -e YOUR_USER`

This will be followed by you needing to input your password.

- create a new database table:

`createdb -O YOUR_USER YOUR_DB_NAME`

Change YOUR_USER and YOUR_DB_NAME appropriately.

- finally:

`psql YOUR_DB_NAME -h YOUR_HOST YOUR_USER`

This will allow you to connect to your database via your terminal.
By default, YOUR_HOST should be 0.0.0.0:5432.

You should now be able to build your database URI. This will be:

`sqldbtype://username:pw@hostname:port/db_name`

Replace sqldbtype with whichever db youre using (eg postgres, mysql, sqllite, etc)
repeat for your username, password, hostname (localhost?), port (5432?), and db name.

## Modules
### Setting load order.

The module load order can be changed via the `LOAD` and `NO_LOAD` configuration settings.
These should both represent lists.

If `LOAD` is an empty list, all modules in `modules/` will be selected for loading by default.

If `NO_LOAD` is not present, or is an empty list, all modules selected for loading will be loaded.

If a module is in both `LOAD` and `NO_LOAD`, the module will not be loaded - `NO_LOAD` takes priority.

### Creating your own modules.

Creating a module has been simplified as much as possible - but do not hesitate to suggest further simplification.

All that is needed is that your .py file be in the modules folder.

To add commands, make sure to import the dispatcher via

`from marvel import dispatcher`.

You can then add commands using the usual

`dispatcher.add_handler()`.

Assigning the `__help__` variable to a string describing this modules' available
commands will allow the bot to load it and add the documentation for
your module to the `/help` command. Setting the `__mod_name__` variable will also allow you to use a nicer, user
friendly name for a module.

The `__migrate__()` function is used for migrating chats - when a chat is upgraded to a supergroup, the ID changes, so 
it is necessary to migrate it in the db.

The `__stats__()` function is for retrieving module statistics, eg number of users, number of chats. This is accessed 
through the `/stats` command, which is only available to the bot owner.
