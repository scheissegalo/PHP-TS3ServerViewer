TeamSpeak 3 Server Viewer (TS3SSV)
=====
TeamSpeak 3 Server Viewer is a simple status dashboard powered by PHP.
Originally a fork of https://github.com/LeoWinterDE/TS3ServerStatusViewer

![screenshot of TS3ServerStatusViewer](https://i.imgur.com/x6529AN.jpg)

## Download, install

- <a href="https://github.com/scheissegalo/PHP-TS3ServerViewer/releases">Download</a>
- Extract the archive and upload it to your webspace/website
- Give the file ts3ssv.php.cache write permission (chmod 777)
- Navigate to yoursite.tld/setup.php
- You will get a red warning because the generator is disabled by default
- To enable the generator you have to edit setup.php and replace $enableGenerator = false; by $enableGenerator = true
- Now you can test and customize TS3SSV. The generator will output/update the codes needed to display your status page  
- Don't forget to disable the script when you done!


# Configuration options
```
	useServerId: use specific server udp port
		$tsstatus->useServerPort(9987);

	useServerPort: define server id
		$tsstatus->useServerId($sid);

	imagePath: path to the TSStatus icons directory
		$tsstatus->imagePath = "/tsstatus/img/";

	clearServerGroupFlags: clear all server groups flags
		$tsstatus->clearServerGroupFlags();

	setServerGroupFlag: define a server group flag
		$tsstatus->setServerGroupFlag(6, 'servergroup_300.png');

	clearChannelGroupFlags: clear all channel groups flags
		$tsstatus->clearChannelGroupFlags();

	setChannelGroupFlag: define a channel group flag
		$tsstatus->setChannelGroupFlag(5, 'changroup_100.png');
		$tsstatus->setChannelGroupFlag(6, 'changroup_200.png');

	showNicknameBox: show/hide the nickname box
		$tsstatus->showNicknameBox = true/false;

	timeout: The timeout, in seconds, for connect, read, write operations
		$tsstatus->timeout = 2;

	showPasswordBox: show/hide the password box
		$tsstatus->showPasswordBox = false; // never render the password box
		$tsstatus->showPasswordBox = true; // the box will be rendered only if the server have a password

	setLoginPassword: set the ServerQuery login/password
		$tsstatus->setLoginPassword("ServerQueryLogin", "ServerQueryPassword");

	setCache: activate caching system to prevent bans from the server... you are banned extra_msg=you may retry in XXX seconds
		$tsstatus->setCache(5);
		$tsstatus->setCache(5, "/tmp/mycachefile");
		The first parameter is the cache time in seconds
		The second parameter is the file were the datas will be stored (.../tsstatus/tsstatus.php.cache if not specified)
		The cache file MUST be writable

	limitToChannels: define a list of channel to render, others will be ignored
		$tsstatus->limitToChannels(1, 5, 17); // only render channels with ids equal to 1, 5 and 17

 	hideEmptyChannels:
		$tsstatus->hideEmptyChannels = true/false;

	hideParentChannels: Use this options with limitToChannels or hideEmptyChannels
		$tsstatus->hideParentChannels = true/false;

```

# Recognized Status
```
	Clients:
		- client is talking
		- client is away
		- harware input muted
		- harware output muted
		- input muted
		- output muted

	Channels:
		- channel is full
		- passworded channel
```

# Recognized flags
```
	Clients:
		- Server admin
		- Channel admin
		- Channel operator

	Channels
		- default channel
		- passworded channel
		- moderated channel
```