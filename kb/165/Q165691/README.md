---
layout: page
title: "Q165691: INFO: Visual C++ 5.0 Readme, Sample Program Issues"
permalink: /kb/165/Q165691/
---

## Q165691: INFO: Visual C++ 5.0 Readme, Sample Program Issues

{% raw %}

	Article: Q165691
	Product(s): Microsoft C Compiler
	Version(s): 5.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 31-JUL-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual C++, 32-bit Enterprise Edition, version 5.0 
	- Microsoft Visual C++, 32-bit Professional Edition, version 5.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Sample Program Issues
	---------------------
	
	  New Visual C++ 5.0 Samples
	  Updated Samples
	  ATL Samples COMMAP, CONNECT, and DRAWSERV Do Not Register Correctly When
	  Path Contains Spaces
	  CUSTOMWZ Sample Missing Files
	  Get Sendtime and Settime Samples from the Compact Disc
	  ATL CIRC Sample Fails in Some Containers
	  ATLCON Sample Fails Under MinCRT Configurations
	  ATLBUTTON Sample Returns Incorrect Property Values
	  ATL POLYGON Sample Does Not Build in Release Mode
	  Link Error in Debug Build of COM Sample acdual/mfcctrl
	  Typo in tan and tanh Sample
	  BINDENRL Sample Fails to Copy STDREG32.MDB
	  Access Violation in Visual Basic 5 When Running COMEXCEL Sample
	  Running OLE SDK Samples
	  Running InOLE2 SDK Samples
	
	MORE INFORMATION
	================
	
	The samples on the first Visual C++ CD are accessible from any directory browser
	(Windows Explorer or File Manager, for example). Sample code remains available
	for viewing and download from sample abstracts in the documentation.
	
	New Visual C++ 5.0 Samples
	--------------------------
	
	Try out the samples located in the \DEVSTUDIO\VC\SAMPLES directory of the first
	Visual C++ CD. These include examples of using the new compiler support for COM
	and samples for ATL. They also include a new Custom AppWizard sample.
	
	Updated Samples
	---------------
	
	The most recent versions of the following samples are in the DevStudio\Vc\Samples
	directory on the disc that includes "Microsoft Visual C++" on the label. (Disc 1
	if you purchased Visual C++; Disc 3 if you purchased Visual Studio.) Do not use
	the versions that you can find in the InfoViewer's Samples abstracts. Instead,
	copy the files from the Microsoft Visual C++ disc to your hard drive.
	
	MFC Samples
	
	- OLDBARS
	- SUPERPAD
	- OLEVIEW
	- WORDPAD
	- EXTBIND
	- MDIBIND
	- BINDENRL
	- REGSVR
	- SMILEY
	- DAOCTL
	- ODBCINFO
	
	ATL Samples
	
	- CIRC
	- POLYGON
	
	Enterprise Samples
	
	- SENDTIME
	- SETTIME
	
	Com Samples
	
	- ALLINONE
	- INPROC
	- LABRADOR
	
	SDK Samples
	
	- AXSCRIPT
	- URLPAD
	
	ATL Samples COMMAP, CONNECT, and DRAWSERV Do Not Register Correctly When
	Path Contains Spaces
	---------------------------------------------------------------------------------------------
	
	These ATL samples do not register correctly when their path contains spaces.
	
	Workaround
	
	Edit their corresponding .RGS files and add single quotes around all occurrences
	of %MODULE%. For example, you would change a line containing the following:
	
	     InprocServer32 = s %MODULE%
	
	to the following:
	
	     InprocServer32 = s '%MODULE%'
	
	NOTE: DRAWSERV is a sample program within the DCOM ATL sample.
	
	CUSTOMWZ Sample Missing Files
	-----------------------------
	
	The CUSTOMWZ sample in the DevStudio\Vc\Samples\appwiz\ directory is missing some
	essential files.
	
	To obtain the entire sample, with all of its files, install it from the
	"CUSTOMWZ: A Custom AppWizard" topic in the online documentation. To find this
	topic, choose the Search command from the Help menu, enter the comma- delimited
	string, "CUSTOMWZ: A Custom AppWizard", on the Query tab, and then click the
	Query button.
	
	Get Sendtime and Settime Samples From the Compact Disc
	------------------------------------------------------
	
	The files for the Sendtime and Settime samples downloaded from the Enterprise
	sample abstracts in the online documentation will not compile.
	
	Workaround
	
	Manually copy the correct files for these samples from the
	DevStudio\VC\Samples\Ent\time directory. This directory is on the disc that
	includes "Microsoft Visual C++" on the label. (Disc 1 if you purchased Visual
	C++; Disc 3 if you purchased Visual Studio.)
	
	ATL CIRC Sample Fails in Some Containers
	----------------------------------------
	
	For correct functionality in certain containers, objects passing properties must
	support the propputref semantics. The CIRC sample as installed from the online
	abstract supports propput instead of propputref. Therefore, you should use the
	CIRC sample from the DevStudio\Vc\Samples\Atl\circ directory. To see the correct
	propputref syntax, look in the Circ.idl file. This directory is on the disc that
	includes "Microsoft Visual C++" on the label. (Disc 1 if you purchased Visual
	C++; Disc 3 if you purchased Visual Studio.)
	
	ATLCON Sample Fails Under MinCRT Configurations
	-----------------------------------------------
	
	To successfully run the ATL sample, ATLCON, under a MinCRT configuration, you
	must remove the WinMain entry point as follows:
	
	1. On the Projects menu, click Settings.
	
	2. In the Settings For: drop-down list, choose one of the MinCRT configurations.
	
	3. On the Link tab, choose the Output category.
	
	4. Remove the text in the Entry-point symbol edit box.
	
	ATLBUTTON Sample Returns Incorrect Property Values
	--------------------------------------------------
	
	The ATLBUTTON sample returns incorrect values for the properties ImageHover and
	ImagePush. To correct the sample change the file AtlButton.h so that the
	function get_ImageHover uses m_bstrFilename[1].Copy() and change get_ImagePush
	so that it uses m_bstrFilename[2].Copy().
	
	ATL POLYGON Sample Does Not Build in Release Mode
	-------------------------------------------------
	
	If you copy the ATL POLYGON sample from the online documentation, it will not
	build in Release mode as it incorrectly defines the _ATL_MIN_CRT macro. The
	sample on the disc does not have this problem. (Disc 1 if you purchased Visual
	C++; Disc 3 if you purchased Visual Studio.)
	
	Workaround
	
	1. Select the Settings command from the Project menu
	
	2. Choose the C/C++ tab. In the General category, remove _ATL_MIN_CRT from the
	  Preprocessor definitions edit box. 3.Choose the Link tab. In the Output
	  Category, remove DllMain from the Entry-point symbol edit box.
	
	Link Error in Debug Build of COM Sample acdual/mfcctrl
	------------------------------------------------------
	
	This sample will fail under debug builds looking for comsuppd.lib. To fix the
	problem, go into the Project Settings dialog box and remove _COM_DEBUG from the
	Preprocessor definitions box in the C/C++ Preprocessor section.
	
	Typo in tan and tanh Sample
	---------------------------
	
	In the documentation of tan and tanh, there is a typo in the sample. The current
	sample shows:
	
	     printf( "tan( %f ) = %f\n", x, y );
	     printf( "tanh( %f ) = %f\n", y, x );
	
	It should be:
	
	     printf( "tan( %f ) = %f\n", pi/4, x );
	     printf( "tanh( %f ) = %f\n", x, y );
	
	The correct output is:
	
	  tan( 0.785398 ) =  1.000000
	  tanh( 1.000000 ) = 0.761594
	
	See both the \DEVSTUDIO\VC\SAMPLES and the \OLEDB\SAMPLES directories on the
	first Visual C++ CD.
	
	BINDENRL Sample Fails to Copy STDREG32.MDB
	------------------------------------------
	
	To build the BINDENRL sample, you'll need to manually copy the database file
	stdreg32.mdb into the same local directory that you copy the samples source
	files. You will find stdreg32.mdb in the
	DEVSTUDIO\VC\Samples\mcl\mfc\database\daoenrol directory. This directory is on
	the disc that includes "Microsoft Visual C++" on the label. (Disc 1 if you
	purchased Visual C++; Disc 3 if you purchased Visual Studio.)
	
	Access Violation in Visual Basic 5.0 When Running COMEXCEL Sample
	-----------------------------------------------------------------
	
	If you get an access violation while running the COMEXCEL sample in Visual Basic
	5.0 under Windows NT V4.0, please install the Windows NT Service Pack 2.
	
	Running OLE SDK Samples
	-----------------------
	
	Before you run an OLE SDK sample, you should first copy the following
	subdirectories from the first VC++ product CD
	
	  DevStudio\VC\Samples\SDK\ole\include
	  DevStudio\VC\Samples\SDK\ole\lib
	
	to the following subdirectories on the disk (in this case c:) that will hold the
	OLE samples
	
	  c:\samples\ole\include
	  c:\samples\ole\lib
	
	You can now install the sample files in any directory on the disk (in this case
	c:) and compilation will find the include and lib directories. If you have an
	MSTOOLS environment variable defined, you should put the include and lib
	directories in the following location on your hard disk: MSTOOLS path\samples.
	
	Running InOLE2 SDK Samples
	--------------------------
	
	Before you run an InOLE2 SDK sample, you should first copy the following
	subdirectories from the first VC++ product CD
	
	  DevStudio\VC\Samples\SDK\ole\inole2\inc
	  DevStudio\VC\Samples\SDK\ole\inole2\lib
	
	to the following subdirectories on the disk (in this case c:) that will hold the
	OLE samples
	
	  c:\samples\ole\inole2\inc c:\samples\ole\inole2\lib
	
	You can now install the sample files in any directory on the disk (in this case
	c:) and compilation will find the inc and lib directories. If you have an
	MSTOOLS environment variable defined, you should put the inc and lib directories
	in the following location on your hard disk: MSTOOLS path\samples.
	
	======================================================================
	Keywords          :  
	Technology        : kbVCsearch kbAudDeveloper kbVC500 kbVC32bitSearch kbVC500Search
	Version           : 5.0
	
	=============================================================================
	

{% endraw %}
