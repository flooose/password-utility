# A password manager for bash

## Introduction

This started out as an experiment in password management for terminal
oriented users. It has since evolved into a fairly robust script that
I've been using for a few years.

If used on a linux, it takes advantage of both the primary and
secondary X-clipboards, saving the login in the primary (middle mouse
click) and the password in the secondary (ctrl-v) clipboard. On MacOS,
only the password is copied to the clipboard.

After [setting up](#setup), password retrieval is done in the form of

    $ p somedomainorothergrep-ableentity

which will present you with a list of possible password/usernames to
be copied to your clipboard.

Although some effort at MacOS compatibility has been made, I've only
been able to test it on my linux, so feel free to give me some
feedback.

<h2 id="setup">Setup</h2>

The following steps are necessary for the function to work:

1. Create the file and directory structure

        $ mkdir ~/.password
        $ touch ~/.password/db.txt

2. Create a plain text version of your password database in ```~/.password/db.txt```.
   Entries in the database are assumed to be in the form of

        domain|login|password|comments|password

   but most important is that the login is in the second field and the
   password is in the last field.

3. Encrypt the password file

        $ ccrypt ~/.password/db.txt

4. Add ```source ~/path/to/password.bash``` somewhere in your
   ```~/.bashrc```

## Dependencies

The function has the following dependencies that should readily be
available in your system's package utility:

- ccrypt
- sed (hopefully not much longer)
- xclip/pbcopy

## TODO

Please see the comments in the souce code for this

## Known Bugs

Please see the comments in the souce code for this

## Contributions and Feedback

If you'd like to contribute something to this script, or give
feedback, feel free to send pull requests, emails, twits, etc.
