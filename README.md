minecraft_bigreactor_control
============================

Minecraft BigReactor Computercraft Control Program

	Program name: Lolmer's EZ-NUKE reactor control system
	Version: v0.2.1
	Programmer: Lolmer
	Last update: 2014-02-18
	Pastebin: http://pastebin.com/fguScPBQ

	Description: 
	This program controls a Big Reactors nuclear reactor
	in Minecraft with a Computercraft computer, using Computercraft's
	own wired modem connected to the reactors computer control port.

	Features:
		Configurable min/max energy buffer and min/max temperature via ReactorOptions file.
		ReactorOptions is read on start and then current values are saved every program cycle.
		Rod Control value in ReactorOptions is only useful for initial start, after that the program saves the current Rod Control average over all Fuel Rods for next boot.
		Auto-adjusts individual control rods (based on hottest/coldest) to maintain temperature.

	Default values:
		Rod Control: 90% (Let's start off safe and then power up as we can)
		Minimum Energy Buffer: 15% (will power on below this value)
		Maximum Energy Buffer: 85% (will power off above this value)
		Minimum Temperature: 850^C (Will raise control rods below this value)
		Maximum Temperature: 950^C (Will lower control rods above this value)

	TODO:
		Add Fuel consumption metric to display - No such API. :(
		Support multiple reactors and multiple monitors.
		- If one reactor, display same output to all monitors
		- If multiple reactors, require a monitor for each reactor and display only that reactor on a monitor
		Add support for direct attached monitors and computers
		Add support for wireless modems, see http://computercraft.info/wiki/Modem_%28API%29, will not be secure (anyone can send/listen to your channels)!

	Requirements:
		Advanced Monitor size is X: 29, Y: 12 with a 3x2 size
		Computer or Advanced Computer
		Modems (not wireless) connecting each of the Computer to both the Advanced Monitor and Reactor Computer Port.

	Resources:
		This script is available from:
			http://pastebin.com/fguScPBQ
			https://github.com/sandalle/minecraft_bigreactor_control
		Startup script is available from:
			http://pastebin.com/ZTMzRLez
			https://github.com/sandalle/minecraft_bigreactor_control
		Other reactor control which I based my program on:
			http://pastebin.com/aMAu4X5J (ScatmanJohn)
			http://pastebin.com/HjUVNDau (version ScatmanJohn based his on)
		FC API, required:
			http://pastebin.com/A9hcbZWe
		A simpler Big Reactor control is available from:
			http://pastebin.com/tFkhQLYn (IronClaymore)

		Reactor Computer Port API: http://wiki.technicpack.net/index.php?title=Reactor_Computer_Port
		Computercraft API: http://computercraft.info/wiki/Category:APIs

ChangeLog
============================
0.2.2 - Do not auto-start the reactor if it was manually powered off (autoStart=false)
0.2.1 - Lower/raise only the hottest/coldest Control Rod while trying to control the reactor temperature.
	"<" Rod Control buttons was off by one (to the left)

0.2.0 - Lolmer Edition :)
	Add min/max stored energy percentage (default is 15%/85%), configurable via ReactorOptions file.
	No reason to keep burning fuel if our power output is going nowhere. :)
	Use variables variable for the title and version.
	Try to keep the temperature between configured values (default is 850^C-950^C)
	Add Waste and number of Control/Fuel Rods to displayBards()

TODO
============================
	Add Fuel consumption metric to display - No such API. :(
