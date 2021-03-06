---
layout: page
title: "Q289000: Client Agent Settings Do Not Propagate After Applying SP3 RC9"
permalink: /kb/289/Q289000/
---

## Q289000: Client Agent Settings Do Not Propagate After Applying SP3 RC9

{% raw %}

	Article: Q289000
	Product(s): Microsoft Systems Management Server
	Version(s): 2.0 SP2,2.0 SP3
	Operating System(s): 
	Keyword(s): kbsms200preSP3fix
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server versions 2.0 SP2, 2.0 SP3 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	After you apply the RC9 version of Systems Management Server (SMS) 2.0 Service
	Pack 3 (SP3), updates that are made to client agent settings are not propagated
	to the client computers properly.
	
	SMS 2.0 SP3 RC9 (1493.3009) was initially released to the Web for Premier
	customers. Shortly after this release, a problem was discovered and Microsoft
	re-released SP3. This article describes the availability of a hotfix to upgrade
	an RC9 site to the full release version of SMS 2.0 SP3, which does not have this
	problem.
	
	This problem occurs only in the RC9 version of SMS 2.0 SP3.
	
	RESOLUTION
	==========
	
	Apply the following SMS 2.0 SP3 RC9 hotfix that upgrades your version to the
	full release version of SMS 2.0 SP3.
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem that is described in this article. Only apply it to systems
	that are experiencing this specific problem. This fix may receive additional
	testing. Therefore, if you are not severely affected by this problem, Microsoft
	recommends that you wait for the next Systems Management Server service pack
	that contains this fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information about support costs, visit the following Microsoft
	Web site:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are ordinarily incurred for support calls
	may be canceled if a Microsoft Support Professional determines that a specific
	update will resolve your problem. The usual support costs will apply to
	additional support questions and issues that do not qualify for the specific
	update in question.
	
	The English version of this fix should have the following file attributes or
	later:
	
	 Date        Time        Size  File name           Platform  Version
	 -------------------------------------------------------------------------
	 02/08/2001  05:10a   1324080  CcmCore.exe         I386           2.0.92.1
	 02/08/2001  05:10a   1925326  CcmCore.exe         Alpha          2.0.92.1
	 02/08/2001  05:10a   3378093  CliCore.exe         I386      2.0.1493.3010
	 02/08/2001  05:10a   4434139  CliCore.exe         Alpha     2.0.1493.3010
	 02/08/2001  05:10a     87920  clisvcl.exe         I386      2.0.1493.3010
	 02/08/2001  05:10a    124688  clisvcl.exe         Alpha     2.0.1493.3010
	 02/08/2001  05:10a        67  compverbase.ini     Intel
	 02/08/2001  05:10a        67  compverhinv.ini     Intel
	 02/08/2001  05:10a        67  compverlicmtr.ini   Intel
	 02/08/2001  05:10a        67  compverremctrl.ini  Intel
	 02/08/2001  05:10a        67  compversinv.ini     Intel
	 02/08/2001  05:10a        67  compversmsapm32.ini Intel
	 02/08/2001  05:10a        67  compversnmpelea.ini Intel
	 02/08/2001  05:10a        67  compverswdist.ini   Intel
	 02/08/2001  05:10a        67  compverwbem.ini     Intel
	
	NOTE: Due to file dependencies, the most recent hotfix or feature that contains
	the above files may also contain additional files.
	
	
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in the Microsoft products that
	are listed at the beginning of this article.
	
	MORE INFORMATION
	================
	
	To install the hotfix, use the appropriate method on the SMS site server.
	
	Using the Hotfix Installer
	--------------------------
	
	NOTE: You can use this method only on Intel-based computers.
	
	1. Copy the hotfix folder structure to a share on your network (for example, the
	  Q289000.exe file is located in a root folder with Intel and Alpha
	  subfolders). Q289000.exe is a Microsoft Windows Installer file that updates
	  specific files on your site server.
	
	2. Log on to your site server using an account with administrative privileges.
	
	3. Run Q289000.exe and follow the instructions in the wizard. You can run the
	  file in Quiet mode by using the /s switch.
	
	Manual Installation
	-------------------
	
	1. Stop all SMS services on the site server.
	
	2. Replace the Clisvcl.exe file in the
	  <Sms_root_folder>\Bin\<Platform> folder with the version obtained
	  from the hotfix.
	
	3. Replace the Clicore.exe file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\Base\<Platform> folder with
	  the version obtained from the hotfix.
	
	4. Replace the CCMcore.exe file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\Base\<Platform> folder with
	  the version obtained from the hotfix.
	
	5. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\Base folder with the
	  Compverbase.ini file obtained from the hotfix. Note that you must rename the
	  Compverbase.ini file to Compver.ini.
	
	6. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\Hinv folder with the
	  Compverhinv.ini file obtained from the hotfix. Note that you must rename the
	  Compverhinv.ini file to Compver.ini.
	
	7. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\licmtr folder with the
	  Compverlicmtr.ini file obtained from the hotfix. Note that you must rename
	  the Compverlicmtr.ini file to Compver.ini.
	
	8. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\remctrl folder with the
	  Compverremctrl.ini file obtained from the hotfix. Note that you must rename
	  the Compverremctrl.ini file to Compver.ini.
	
	9. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\sinv folder with the
	  Compversinv.ini file obtained from the hotfix. Note that you must rename the
	  Compversinv.ini file to Compver.ini.
	
	10. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\smsapm32 folder with the
	  Compversmsapm32.ini file obtained from the hotfix. Note that you must rename
	  the Compversmsapm32.ini file to Compver.ini.
	
	11. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\snmpelea folder with the
	  Compversnmpelea.ini file obtained from the hotfix. Note that you must rename
	  the Compversnmpelea.ini file to Compver.ini.
	
	12. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\swdist folder with the
	  Compverswdist.ini file obtained from the hotfix. Note that you must rename
	  the Compverswdist.ini file to Compver.ini.
	
	13. Replace the Compver.ini file in the
	  <Sms_root_folder>\Inboxes\Clicomp.src\wbem folder with the
	  Compverwbem.ini file obtained from the hotfix. Note that you must rename the
	  Compverwbem.ini file to Compver.ini.
	
	14. Restart the SMS services on the site server.
	
	
	Additional query words: prodsms
	
	======================================================================
	Keywords          : kbsms200preSP3fix 
	Technology        : kbSMSSearch kbSMS200SP2 kbSMS200SP3
	Version           : :2.0 SP2,2.0 SP3
	Hardware          : x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
