# TiddlyWiki5 on Sandstorm

Rapid and basic implementation of [TiddlyWiki5](http://tiddlywiki.com/) as a [Sandstorm](http://sandstorm.io) app. 

[TiddlyWiki5](http://tiddlywiki.com/) is a non-linear personal web notebook that anyone can use and keep forever, independently of any corporation.

[TiddlyWiki5](http://tiddlywiki.com/) is a complete interactive wiki in JavaScript. Natively, it can be used as a single HTML file in the browser or as a powerful Node.js application. It is highly customisable: the entire user interface is itself implemented in hackable WikiText. 

[Sandstorm](http://sandstorm.io) is an open source platform for personal servers. [Sandstorm](http://sandstorm.io) lets you run your own server and easely install apps like [Roundcube](https://roundcube.net/), [Wekan](https://wekan.io/), [EtherCalc](https://ethercalc.org/), [Etherpad](http://etherpad.org/), [GitLab](https://about.gitlab.com/), and more. It handles login & access control, and can run any web app that runs on Linux, though some apps may need changes to work within the Sandstorm sandbox.

The goal of this work i to used it as an instance on the [Sandstorm](https://sandstorm.io) app platform. 

Documentation :

- [Sandstorm packaging tutorial (Generic)](https://docs.sandstorm.io/en/latest/vagrant-spk/packaging-tutorial/)
- [Installing and using TiddlyWiki5 on NodeJS](https://github.com/Jermolene/TiddlyWiki5/blob/master/readme.md)

## Developing

To launch a local [Sandstorm](http://sandstorm.io) instance with [TiddlyWiki5](http://tiddlywiki.com/) pre-installed, do the following.

- Install [Vagrant](https://www.vagrantup.com/downloads.html).
- Install [VirtualBox ](https://www.virtualbox.org/wiki/Downloads).
- Install [Vagrant-SPK](https://github.com/sandstorm-io/vagrant-spk).
- Clone this repo and from the top-level directory, run:
 - `vagrant-spk vm up` to start a virtual Linux machine containing Sandstorm
 - `vagrant-spk dev` to make the app available in the Sandstorm, in development mode
- Your system is running a Sandstorm instance. You should visit it in your web browser now by opening this link.
 - http://local.sandstorm.io:6080
- Log in with a dev account, choose *Alice (admin)* as the user to sign in with
- Click the *TiddlyWiki App* icon, then *Create new instance* to spin up a new TiddlyWiki instance.

Packaging:

To create a Sandstorm package (SPK) file, containing the app and all its dependencies. 

- Stop the `vagrant-spk dev` server : type `Ctrl-C`.
- To create the SPK file, run: `vagrant-spk pack ~/export-path/package.spk`

You can upload this spk file inside your own Sandtorm server to test it.

Issues:

- The TW markups are not inserted in the editing area when I click on edit buttons whith Firefox (48.01, OSX), but it's working fine with Chrome (OSX).
- Because of the Sandstorm security policy, it is not possible to load plugins and themes from the interface TW5 of administration (it works still in Dev mode). You have to download them manually with *import* tool.
