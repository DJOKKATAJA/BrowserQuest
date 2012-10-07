BrowserQuest
============

[BrowserQuest](http://browserquest.mozilla.org/) is a HTML5/JavaScript multiplayer game experiment.

It has two major parts:

* the server side, which runs using Node.js
* the client side, which runs in your browser

How to get it going - local on Windows
--------------------------------------

Getting the server up and running is pretty easy. You need to have the following installed:

* Node.js (most recent stable version)
* Cygwin
* Microsoft Windows SDK (I don't recall if this is actually required or not; you could try it without the SDK initially and install the SDK if the server does not set up).

Use Cygwin for the following commands - the windows command prompt does not take kindly to some of them. 

Clone the git repo:

    $ git clone git://github.com/DJOKKATAJA/BrowserQuest.git
    $ cd BrowserQuest

Then install the Node.js dependencies by running:

    $ npm install -d

Then start the server by running:

    $ node server/js/main.js

The BrowserQuest server should start, showing output like this:

    $ node server/js/main.js
    This server can be customized by creating a configuration file named: ./server/config_local.json
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO Starting BrowserQuest game server...
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world1 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world2 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world3 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world4 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world5 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO Server (everything) is listening on port 8000

That means it's working.  There should not be any warnings or errors.

Using a browser, connect to: 127.0.0.1:8000

The BrowserQuest start page should appear, and the game should work.


Hosting the game publicly on a Linux server:
--------------------------------------------

Node.js backend setup
---------------------

Getting the backend server up and running is pretty easy. You need to have the following installed:

* Node.js (most recent version)

Clone the git repo:

    $ git clone git://github.com/browserquest/BrowserQuest.git
    $ cd BrowserQuest

Then install the Node.js dependencies by running:

    $ npm install -d

Then start the server by running:

    $ node server/js/main.js

The BrowserQuest server should start up, showing output like this:

    $ node server/js/main.js
    This server can be customized by creating a configuration file named: ./server/config_local.json
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO Starting BrowserQuest game server...
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world1 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world2 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world3 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world4 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world5 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO Server is listening on port 8000

That means its working.  There should not be any warnings or errors.


Client side setup
-----------------

Open a new terminal.

First, set the "host" value in client/config/config_build.json-dist, then copy it to/client/config/config_build.json:

    $ vi client/config/config_build.json-dist
    $ cp client/config/config_build.json-dist client/config/config_build.json

The updated host value must be the IP address of the BrowserQuest Node.js server.  For example:

    {
        "host": "100.200.300.400",
        "port": 8000
    }

Then do the same thing for client/config/config_local.json-dist, editing the host value, then copying it to client/config/config_local.json:

    $ vi client/config/config_local.json-dist
    $ cp client/config/config_local.json-dist client/config/config_local.json

Next, copy the "shared" directory from the root of the git repo, into the "client" directory:

    $ cp -r shared client/

Install http-server to run the client:
	
	$ npm install -g http-server
	
Run http-server from the client directory:

	$ cd client
	$ http-server

You should see:
	Starting up http-server, serving ./ on port: 8080
	Hit CTRL-C to stop the server
	
No warning messages should be displayed.

Using a browser, connect to port 8000 of the IP address you entered above.  The BrowserQuest start page should appear.

If you have the BrowserQuest Node.js server running when you do this, you should then be able to launch and play the game.


License
-------

Code is licensed under MPL 2.0. Content is licensed under CC-BY-SA 3.0.
See the LICENSE file for details.


Credits
-------
Originally created by [Little Workshop](http://www.littleworkshop.fr):

* Franck Lecollinet - [@whatthefranck](http://twitter.com/whatthefranck)
* Guillaume Lecollinet - [@glecollinet](http://twitter.com/glecollinet)

All of the music in BrowserQuest comes from Creative Commons [Attribution 3.0 Unported (CC BY 3.0)](http://creativecommons.org/licenses/by/3.0/) sources.

* [Aaron Krogh](http://soundcloud.com/aaron-anderson-11) - [beach](http://soundcloud.com/aaron-anderson-11/310-world-map-loop)
* [Terrel O'Brien](http://soundcloud.com/gyrowolf) - [boss](http://soundcloud.com/gyrowolf/gyro-scene001-ogg), [cave](http://soundcloud.com/gyrowolf/gyro-dungeon004-ogg), [desert](http://soundcloud.com/gyrowolf/gyro-dungeon003-ogg), [lavaland](http://soundcloud.com/gyrowolf/gyro-scene002-ogg)
* [Dan Tilden](http://www.dantilden.com) - [forest](http://soundcloud.com/freakified/what-dangers-await-campus-map)
* [Joel Day](http://blog.dayjo.org) - [village](http://blog.dayjo.org/?p=335)

Many other people are contributing through GitHub:

* Myles Recny [@mkrecny](https://github.com/mkrecny)
* Ben Noordhuis [@bnoordhuis](https://github.com/bnoordhuis)
* Taylor Fausak [@tfausak](https://github.com/tfausak)
* William Bowers [@willurd](https://github.com/willurd)
* Steve Gricci [@sgricci](https://github.com/sgricci)
* Dave Eddy [@bahamas10](https://github.com/bahamas10)
* Mathias Bynens [@mathiasbynens](https://github.com/mathiasbynens)
* Rob McCann [@unforeseen](https://github.com/unforeseen)
* Scott Noel-Hemming [@frogstarr78](https://github.com/frogstarr78)
* Kornel Lesiński [@pornel](https://github.com/pornel)
* Korvin Szanto [@KorvinSzanto](https://github.com/KorvinSzanto)
* Jeff Lang [@jeffplang](https://github.com/jeffplang)
* Tom McKay [@thomasmckay](https://github.com/thomasmckay)
* Justin Clift [@justinclift](https://github.com/justinclift)
* Brynn Bateman [@brynnb](https://github.com/brynnb)
* Dylen Rivera [@dylenbrivera](https://github.com/dylenbrivera)
