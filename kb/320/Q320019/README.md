---
layout: page
title: "Q320019: Dungeon Siege: Known Video Issues"
permalink: /kb/320/Q320019/
---

## Q320019: Dungeon Siege: Known Video Issues

{% raw %}

	Article: Q320019
	Product(s): Microsoft Home Games
	Version(s): 1.0
	Operating System(s): 
	Keyword(s): kbimu
	Last Modified: 10-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Dungeon Siege, version 1.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article describes known video-related issues that you can experience when
	you play Microsoft Dungeon Siege. The information in this article is first
	broken out by general issues and then by issues that have only been known to
	happen on specific types of video hardware.
	
	MORE INFORMATION
	================
	
	General Video Issues
	--------------------
	
	The following are general video related issues that you may experience when
	starting or playing Dungeon Siege:
	
	Startup Errors:
	
	When you attempt to start Dungeon Siege, the game does not start and you may
	receive one of the following errors:
	
	- The games hangs on a black screen with little white dots in the lower
	  left-hand corner.
	
	For additional information, click the article number below to view the article in
	the Microsoft Knowledge Base:
	
	  Q321084 Dungeon Siege: Game Stops During Startup at Black Screen
	
	- Unable to enumerate any DirectDraw devices installed on this system.
	
	To resolve this issue, check or enable Direct3D acceleration:
	
	  1. Click Start, and then click Run.
	
	  2. Type "dxdiag" (without the quotation marks), and then click OK.
	
	  3. On the Display tab, verify that all DirectX features are enabled. If any
	     are disabled, click Enable next to the feature.
	
	     NOTE: if some DirectX features are unavailable, please verify that your
	     video adapter meets the minimum requirements.
	
	- Video Initialization Failed.
	
	To resolve this issue, check the DDI (DirectDraw Interface) version:
	
	  1. Click Start, and then click Run.
	
	  2. Type "dxdiag" (without the quotation marks), and then click OK.
	
	  3. Click "Save All Information" to save a Dxdiag.txt report.
	
	  4. Click Desktop, and then click Save.
	
	  5. Open the DxDiag.txt file on your desktop, and then locate the Display
	     Devices section.
	
	  6. Under this section find the line marked DDI Version.
	
	     This must read 7 (or higher) for Dungeon Siege to function correctly. If it
	     does not, download new drivers for your video card, if possible, or
	     upgrade to new video card hardware.
	
	- Your video hardware does not have enough memory.
	
	To resolve this issue, check the amount of video memory:
	
	  1. Click Start, and then click Run.
	
	  2. Type "dxdiag" (without the quotation marks), and then click OK.
	
	  3. On the Display tab, verify that the Approx. Total Memory is equal to 8.0
	     megabytes (MB).
	
	     The video card must have 8.0 MB, or higher, for Dungeon Siege to function
	     correctly. If it does not, upgrade your video card hardware.
	
	     NOTE: Because of video memory that may be in use at the time you run the
	     DirectX Diagnostic Tool (DXDiag), this line may read slightly less than
	     the actual total. For example, 7.5 MB for a 8.0 MB card.
	
	- Your video chipset has been detected as not supporting the features required
	  by Dungeon Siege.
	
	To resolve this issue:
	
	  1. If you are being informed that your video chipset does not support the
	     features required by the game you will need to upgrade your video hardware
	     for the game to work correctly.
	
	  2. Obtain a new video hardware.
	
	- For all video cards running in 32-bit mode, some effects like smoke and
	  waterfall mist may appear too dark when they are viewed from a distance.
	  Drivers available at the time of the Dungeon Siege release did not solve this
	  problem.
	
	  To resolve this issue, download and install the latest drivers from the
	  appropriate manufacturer.
	
	Specific Video Issues
	---------------------
	
	The following specific video adapters and chip sets have known video-related
	issues in Dungeon Siege:
	
	3DFx Velocity 100:
	
	- The character shadows are corrupted when complex shadows are turned on.
	
	  To resolve this issue, turn off complex shadows on the Options/Video menu or
	  download and install the latest drivers from the following Voodoo Files Web
	  site:
	
	  http://www.voodoofiles.com
	
	3DFx Voodoo 2:
	
	- The gamma adjustment slider is not working and there are slight texture
	  corruptions.
	
	  To resolve this issue, download and install the latest drivers from the
	  following Voodoo Files Web site:
	
	  www.voodoofiles.com
	
	3DFx Voodoo 3:
	
	- The shadow graphics are corrupted.
	
	  To resolve this issue, turn off complex shadows on the Options/Video menu or
	  download and install the latest retail drivers.
	
	- When you run the game in full screen, there are two black flashes that occur
	  during the "preparing world" screen. The drivers that were available at the
	  time of the Dungeon Siege release did not solve this problem.
	
	- The mouse pointer does not appear in the game.
	
	- The lava appears as a grid instead of smooth. The drivers that were available
	  at the time of the Dungeon Siege release did not solve this problem.
	
	- The effects for the Charmed spell do not render correctly. The drivers that
	  were available at the time of the Dungeon Siege release did not solve this
	  problem.
	
	To resolve these issues, download and install the latest drivers from the
	following Voodoo Files Web site:
	
	  www.voodoofiles.com
	
	3DFx Voodoo 3 3000:
	
	- The lava polygon texturing is corrupted or appears blocky. The drivers that
	  were available at the time of the Dungeon Siege release did not solve this
	  problem.
	
	  To resolve this issue, download and install the latest drivers from the
	  following Voodoo Files Web site:
	
	  www.voodoofiles.com
	
	3DFx Voodoo 5 5500 In Windows XP:
	
	- Waterfalls, lava rocks, and fog have graphics corruption. The drivers that
	  were available at the time of the Dungeon Siege release did not solve this
	  problem. The 1.04.00 driver from 3Dfx works the best.
	
	  To resolve this issue, download and install the latest drivers from the
	  following Voodoo Files Web site:
	
	  www.voodoofiles.com
	
	Aopen PA3000:
	
	- When you try to start Dungeon Siege, the game stops responding.
	
	  To resolve this issue, download and install the latest drivers from Aopen.
	
	ASUS V-2470 (Intel i740):
	
	- The screen is black if you use retail drivers for this video card. Dungeon
	  Siege may stop responding if you toggle (ALT+TAB) out of the game and then
	  toggle back. The drivers available at the time of the Dungeon Siege release
	  did not solve this problem.
	
	  To resolve this issue, download and install the latest drivers from Intel.
	
	ASUS V-3800 Ultra:
	
	- The game will not start in Microsoft Windows 2000. A fatal exception error is
	  generated.
	
	  To resolve this issue, download and install the latest retail drivers from
	  ASUS and nVidia.
	
	ASUS V-7700 Geforce2:
	
	- There is slight in-game corruption relating to shadowing effects occurs.
	
	  To resolve this issue, download and install the latest retail drivers from
	  ASUS or turn off complex shadows on the Options/Video menu.
	
	ATI Rage Pro:
	
	1. Some graphics are corrupted and the megamap is black. The chipset on this
	  card is below the minimum specification for Dungeon Siege.
	
	  To resolve this issue, update your video card.
	
	ATI Rage Mobility:
	
	1. Some graphics are corrupted and the megamap is black. The chipset on this
	  card is below the minimum specification for Dungeon Siege.
	
	  To resolve this issue, update your video card.
	
	ATI RADEON 8500:
	
	- Corrupt cinematic and in-game textures may occur due to improper blending
	  effects.
	
	  To resolve this issue, download and install the latest retail drivers from ATI
	  and turn off the SmoothVision feature. To turn off SmoothVision, follow these
	  steps:
	
	  1. Click Start, point to Settings, and then click Control Panel.
	
	  2. In Control Panel, double-click Display.
	
	  3. On the Settings tab, click Advanced.
	
	  4. On the Direct3D tab, click SmoothVision, and then change the Anti-aliasing
	     option to "Application preference" or "Always off".
	
	- Corrupt textures may appear when you view the MegaMap.
	
	  To resolve this issue, download and install the latest retail drivers from
	  ATI.
	
	ATI RADEON VE:
	
	- Waterfall effects do not work. The drivers that were available at the time of
	  the Dungeon Siege release did not solve this problem.
	
	  To resolve this issue, download and install the latest drivers from ATI.
	
	Creative 3D Blaster Riva TnT 2 Ultra:
	
	- A fatal error occurs and the game will not start.
	
	  To resolve this issue, download and install the latest drivers from Creative
	  Labs.
	
	Creative Blaster Riva TNT:
	
	- The main menu Option backgrounds become invisible.
	
	  To resolve this issue, download and install the latest retail drivers from
	  Creative Labs.
	
	Diamond Monster Fusion:
	
	- Trees do not fade away when you run up to them.
	
	- The game loads slowly and a black screen is rendered (you can hear the game
	  music in the back ground). By pressing ALT+TAB to leave Dungeon Siege and
	  then ALT+TAB to return, the game appears correctly and you can enter the game
	  world.
	
	- The gamma correction slider does not work. The MegaMap is black. There is a
	  corrupted font in the Options menu. You cannot select complex shadows. The
	  water effects are not correct. The drivers that were available at the time of
	  the Dungeon Siege release resolved all but the water problems.
	
	  This video card is based of the Voodoo Banshee chipset. To resolve these
	  issues, download and install the latest reference drivers from:
	
	  http://www.voodoofiles.com
	
	Diamond Speedstar A90:
	
	- Graphics on the Hero are corrupted if 32-bit display settings are chosen.
	
	  To resolve this issue, set the filtering to bilinear in the Display settings.
	
	Diamond Stealth II G460:
	
	- The game stops responding if you press ALT+TAB to switch to a different
	  program, and then press ALT+TAB again to return to the game.
	
	  To resolve this issue, download and install the latest reference drivers from
	  S3.
	
	Diamond Viper II Z-200:
	
	- When you run Dungeon Siege, your computer may restart.
	
	  If you have a VIA motherboard, download and install the latest '4in1' AGP
	  drivers for that motherboard. You should also download and install the latest
	  retail drivers from S3 (Sonicblue).
	
	Diamond Viper V550:
	
	- When you start the game, the screen turns black, which forces you to restart
	  the computer.
	
	  To resolve this issue, download and install the latest retail or reference
	  drivers from S3.
	
	Diamond Viper V770 TNT2:
	
	- The game stops responding or exits when it is running in full screen.
	
	  To resolve this issue, download and install the latest retail or reference
	  drivers from S3.
	
	ELSA Erazor III:
	
	- A fatal error occurs and the game will not start.
	
	  To resolve this issue, download and install the latest retail drivers from
	  ELSA.
	
	ELSA Erazor X:
	
	- The graphics of your hero character lose textures.
	
	  To resolve this issue, download and install the latest retail drivers from
	  ELSA.
	
	ELSA Gladiac, GLoria II-64, Erazor X2:
	
	- The viewable area of the MegaMap appears black.
	
	  To resolve this issue, download and install the latest reference drivers from
	  ELSA.
	
	ELSA Gladiac:
	
	- The top HUD is projected as a shadow around the main character when complex
	  shadows are turned on.
	
	- The game stops responding if you switch to complex shadows and then try to
	  quit the game.
	
	  To resolve these issues, download and install the latest retail drivers from
	  ELSA.
	
	GeForce 256:
	
	- The MegaMap textures do not display.
	
	  To resolve this issue, download and install the latest reference drivers from
	  nVidia.
	
	GeForce 3:
	
	- If you have Quincunx anti-aliasing enabled, there is a blurry square around
	  the pointer. The drivers that were available at the time of the Dungeon Siege
	  release did not solve this problem.
	
	  To resolve this issue, download and install the latest drivers from nVidia.
	
	Hercules 3D Prophet:
	
	- The game world does not load properly (screen may be black).
	
	- The game generates a fatal exception error when you start it.
	
	- Fog dissipates completely in the MegaMap view. Some areas of the fog flash in
	  and out even after you have crossed over the area. In other places
	  (especially around the water and lava) the fog never disappears.
	
	  To resolve these issues, download and install the latest retail drivers from
	  Hercules or the latest reference drivers from nVidia.
	
	Intel 82815 Graphics Controller:
	
	- An Ice Warrior's shadows are partially blocked when your Hero overlaps him.
	  The drivers available at the time of the Dungeon Siege release did not solve
	  this problem.
	
	  To resolve this issue, download and install the latest drivers from Intel.
	
	Kyro II chipset (3D Prophet 4500):
	
	- The game area is displayed as gray.
	
	  To resolve this issue download the latest drivers for your video card or set
	  the game to use simple shadows. To set simple shadows:
	
	  1. Click Start, point to Programs, point to Dungeon Siege, point to
	     Troubleshooting, and then click "Dungeon Siege Video Configuration Tool".
	
	  2. Under Shadows, select Simple Shadows, and then click OK.
	
	Matrox Marvel G-400:
	
	- A portion of the rock wall looks like the lava.
	
	  To resolve this issue, download and install the latest retail drivers from
	  Matrox.
	
	Matrox Millennium G200:
	
	- The mist from the waterfalls looks like smoke.
	
	- The graphics are corrupted around the character in the Choose Hero screen and
	  around the Character Portrait during game play.
	
	  To resolve these issues, download and install the latest retail drivers from
	  Matrox.
	
	Matrox Millennium G450:
	
	- The game stops responding or quits. When DualHead is enabled and Dungeon
	  Siege is running in windowed mode, the desktop resolution must be set to at
	  least 800 x 600.
	
	  To resolve this issue, run in full screen mode or set the Windows desktop
	  resolution to 800 x 600 or higher. If you are attempting to run in a window,
	  make sure your desktop is set to a bit depth supported by this video card.
	
	Number Nine SR9 Pro:
	
	- The mouse pointer does not appear in the game.
	
	  To resolve this issue, download and install the latest reference drivers from
	  Number Nine Visual Technology.
	
	- You can not enter a name in the Hero Name field.
	
	  To resolve this issue, download and install the latest drivers from Number
	  Nine Visual Technology.
	
	Number Nine Revolution 3D:
	
	- Shadows and the green locater ring are rendered multiple times.
	
	- Flowing river and lava textures do not appear.
	
	- Flashing triangles appear as your character moves through the world.
	
	  The drivers that were available at the time of the Dungeon Siege release did
	  not solve these problems. To resolve these issues, download and install the
	  latest drivers from Number Nine Visual Technology.
	
	nVidia (various):
	
	- When you attempt to log in to a password protected screensaver that is
	  running at the same time as Dungeon Siege, or attempt to return to the game
	  from the Windows Security dialog box in Microsoft Windows 2000 or Microsoft
	  Windows XP, the game may stop responding or quit. At the time of the Dungeon
	  Siege release there was no known resolution for this issue.
	
	  To work around this issue, turn off your screensaver and do not use the
	  Windows Security dialog box while you play Dungeon Siege.
	
	- Text or dialog boxes flicker.
	
	  To resolve this issue download the latest drivers for your video card, disable
	  Hardware TnL or set the game to use blit mode.
	
	  To disable Hardware TnL:
	
	  1. Click Start, click Programs, click Dungeon Siege, click Troubleshooting,
	     and then click "Dungeon Siege Video Configuration Tool".
	
	  2. In the Video Driver drop down list, select "Primary Display Driver -
	     Hardware"
	
	  3. Click OK.
	
	To use blit mode:
	
	  1. Create a shortcut to the DungeonSiege.exe file.
	
	  2. Right-click the shortcut, and then click Properties.
	
	  3. In the Target field on the Shortcut tab, add the following at the end of
	     the line: "bltonly=true" (without the quotation marks). The entire Target
	     line would then read:
	
	  "C:\Program Files\Microsoft Games\Dungeon Siege\DungeonSiege.exe"
	  bltonly=true
	
	nVidia RIVA TNT2 (all):
	
	- When you are running the game in full screen there are two black flashes that
	  occur during the "preparing world" screen. The drivers that were available at
	  the time of the Dungeon Siege release did not solve this problem.
	
	  To resolve this issue, download and install the latest drivers from nVidia.
	
	nVidia RIVA TNT2 Model 64/Model 64 Pro:
	
	- A fatal exception occurs during the credits. The drivers that were available
	  at the time of the Dungeon Siege release did not solve this problem.
	
	  To resolve this issue, reduce the display settings to 16-bit in the Display
	  options or download and install the latest drivers from nVidia.
	
	STB Velocity 4400:
	
	- When you force 32-bit settings on this card, the graphics are corrupted. This
	  card only supports 16-bit settings.
	
	  To resolve this issue, use only 16-bit settings in the Display options.
	
	STB nVidia ZX 8MB:
	
	- Some graphics are corrupted. The memory on this card is below the minimum
	  configuration for Dungeon Siege.
	
	  To resolve this issue, update your video card.
	
	ST Kyro:
	
	- A Critical Error or Fatal Error occurs when you change the game resolution.
	
	  To resolve this issue, download and install the latest retail drivers from ST.
	
	Trident Blade XP:
	
	- No waterfall effects are visible.
	
	  To resolve this issue, download and install the latest drivers from Trident
	  Microsystems.
	
	VIA motherboard chipset:
	
	- Instability problems may occur when playing any 3-D game at full screen.
	
	  To resolve this issue, download and install the latest motherboard drivers, or
	  visit www.viatech.com for the latest 4-1 drivers specific for your
	  motherboard chipset. You can also visit the Windows Update page for drivers
	  and compatibility.
	
	Contact Your Video Adapter Manufacturer:
	
	For information about how to contact your video adapter manufacturer to inquire
	about how to obtain and install the latest video driver for your video adapter,
	click the appropriate article number below to view the article in the Microsoft
	Knowledge Base:
	
	  Q65416 Hardware and Software Third-Party Vendor Contact List, A-K
	
	  Q60781 Hardware and Software Third-Party Vendor Contact List, L-P
	
	  Q60782 Hardware and Software Third-Party Vendor Contact List, Q-Z
	
	To identify the manufacturer and model of your video adapter:
	
	1. Click Start, point to Settings, and then click Control Panel.
	
	2. Double-click System.
	
	3. If you are using a Microsoft Windows 98-based or Microsoft Windows
	  Millennium-based computer, click the Device Manager tab.
	
	  If you are using a Microsoft Windows 2000-based or a Microsoft Windows
	  XP-based computer, click the Hardware tab, and then click Device Manager.
	
	4. Click the plus sign (+) next to "Display adapters" to expand the branch.
	
	5. Under the "Display adapters" branch, note the manufacturer and model of your
	  video adapter, and then click OK.
	
	6. Close all open windows on the desktop.
	
	NOTES: Reference drivers are drivers that are released by the manufacturers of
	specific video chip sets.
	
	Retail drivers are drivers that are released by the manufacturer of a video
	adapter or sound card that use a specific chip set.
	
	If you experience issues when you use the most recent retail drivers supplied by
	the manufacturer of your video adapter, use the latest reference driver from the
	manufacturer of your video adapter chip set.
	
	The third-party contact information included in this article is provided to help
	you find the technical support you need. This contact information is subject to
	change without notice. Microsoft in no way guarantees the accuracy of this
	third-party contact information.
	
	The third-party products discussed in this article are manufactured by vendors
	independent of Microsoft; we make no warranty, implied or otherwise, regarding
	these products' performance or reliability.
	
	Additional query words: msgame
	
	======================================================================
	Keywords          : kbimu 
	Technology        : kbHomeProdSearch kbGamesSearch _IK kbDungeonSiege
	Version           : :1.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
