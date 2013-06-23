# SEARCHING FOR $ – a C64 Ajax loader

Golly gosh Ajax spinners ("throbbers" if you must use the correct term) are boring. They just spin. Not my Ajax throbber. It rocks.

In action: http://www.mrspeaker.net/2010/10/20/c64-ajax-loader/

No longer do you have to bore your users to tears waiting for your Ajax requests to complete - you can keep them thoroughly entertained with this historically accurate representation of the loading screen of the Commodore 64. Ah, how your users will smile with memories of waiting for America's Cup Challenge to load from cassette, but always stopping after 30 minutes, and even if it did ever load, being a really crappy game.

If that's the kind of emotional User Experience you want your apps to evoke, read on!

The code is based on my entry (http://js1k.com/2010-first/demo/527) for the inaugural js1k competition. I expanded it to make it slightly more readable, and add a futuristic API.

	To start the "spinner": LOAD("*",8,1)
	To stop: RUNSTOP()
	To change the message displayed: PRINT("YOUR MESSAGE")
	To load in a particular containing element: LOAD("#myDiv",8,1) (the final parameter is the z-index to set the container)

There are a bunch of settings which can be accessed by PEEKing and POKEing in the RAM and ROM banks. For example, to change the containing element (ROM location 0): POKE(0,"#myDiv") and to read it back and print to screen: PRINT(PEEK(0))

The RAM bank is stored from memory location 49152 (decimal):

	V=49152
	PRINT(PEEK(V+4))
	POKE(V+4,1)

The banks are not fully documented of course. Check out the source if you want to modify things. I'm not giving you any more information than that - it would go against the spirit of the C64.
