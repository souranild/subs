# subs [![Build Status](https://api.travis-ci.org/mitchweaver/subs.svg?branch=master)](https://travis-ci.com/mitchweaver/subs)

Have a feed of your YouTube subscriptions. No Google account needed.

Select a choice and with dmenu and view with mpv.

Written in POSIX sh.

deps: curl, mpv, dmenu

## About

I'm a fan of command line and "doing things yourself".  
I also don't like having a Google account, but still want to keep track of subscriptions.  
Thus [subs](http://github.com/mitchweaver/subs) was born.

![subs_dmenu](https://wvr.sh/u/tXCc.png)

## Environment

Create your `$SUBS_FILE`, as described below, and export this var its path.

Next set your `$SUBS_MENU_PROG` if desired, by default the menu will be `dmenu -p Subs:`.

## Usage

First generate the links to the XML feeds of your subscriptions via `subs -g`.

Once this has completed, this needn't be done again unless you update your `$SUBS_FILE`.

Next, update your subs cache via `subs -u`. This will fetch any
changes from the feeds and store it back into the cache locally.
This way the cache only is updated when you choose to, rather than
redownloading them all every run.

## Subs File

The `$SUBS_FILE` file is a normal text file containing usernames of your subscriptions.  
These can be the username or the channel IDs.

Comments and blank lines are ignored.  
Here is a short example:

```
# Travel
UCXulruMI7BHj3kGyosNa0jA # Indigo Traveller
cmbroad44                # Abroad in Japan
# Misc
UCimiUgDLbi6P17BdaCZpVbg # exurb1a
Vsauce                   # Vsauce
UCF9cNYdVSYS_oha1eGzDTGQ # Goniloc
```

As you can see, some of these are usernames and some are channel IDs -- either work just fine.

## Safety

Every commit is [shellchecked](https://github.com/mitchweaver/subs/blob/master/.travis.yml) with travis.
