---
layout: page
title: "Q137073: PC WSPlus: Corrupt Schedule File May Prevent Access"
permalink: /kb/137/Q137073/
---

## Q137073: PC WSPlus: Corrupt Schedule File May Prevent Access

{% raw %}

	Article: Q137073
	Product(s): Microsoft Schedule+ for Windows
	Version(s): WINDOWS:1.0,7.0,95
	Operating System(s): 
	Keyword(s): 
	Last Modified: 12-SEP-1999
	
	1.00 7.00
	WINDOWS
	kbusage
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Schedule+ for Windows, versions 1.0, 95, 7.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you use version 1.0 or 7.0 of Schedule+ for Windows, and you try to Open
	Other's Appointment Book..., the following error may appear:
	
	For version 1.0:
	
	  The schedule file could not be opened. You may not have the necessary access
	  privileges or the file may be unavailable.
	
	For version 7.0:
	
	  The schedule cannot be opened. Access is denied.
	
	CAUSE
	=====
	
	Either the access privileges have not been granted, or the schedule file may be
	corrupt.
	
	RESOLUTION
	==========
	
	Setting Access Privileges.
	--------------------------
	
	If the access privileges have not set, they can be set by doing the following:
	
	For version 1.0:
	
	1. From the Options menu, select Set Access Privileges.
	
	2. From the Set Access Privileges dialog box, click the Add button.
	
	3. From the Add Users dialog box, select the users to grant access privileges
	  to. Click the Add button. Repeat as often as necessary. Click OK when you are
	  finished. This will bring you back to the Set Access Privileges dialog box.
	
	4. The default access privileges will be assigned to the users. To modify the
	  user's access privileges, highlight the user in the Users field, then select
	  the appropriate level of access from the Privileges field for the user.
	
	5. Click OK. Exit and Sign Out of Schedule+ to save the changes.
	
	For version 7.0:
	
	1. From the Options menu, select Set Access Permissions.
	
	2. From the Set Access Permissions dialog box, select the Users tab, then click
	  the Add button.
	
	3. From the Add Users dialog box, select the users to grant access privileges
	  to. Click the Users button. Repeat as often as necessary. Click OK when you
	  are finished. This will bring you back to the Set Access Privileges dialog
	  box.
	
	4. The default access privileges will be assigned to the users. To modify the
	  user's access privileges, highlight the user in the Users field, then select
	  the appropriate level of access from the Permission Details for <User
	  Name> field for the user from the User Role drop down menu. Click OK to
	  save the changes to the schedule file.
	
	Resetting Access Privileges/Permissions in the Schedule File.
	-------------------------------------------------------------
	
	For version 1.0:
	
	1. From the Options menu, select Set Access Privileges.
	
	2. From the Set Access Privileges dialog box, remove all access privileges for
	  users by first highlighting the user in the Users filed, then by clicking the
	  Remove button.
	
	3. Again from the Users field in the Set Access Privileges dialog box, select
	  the Default, and reset that to none in the Privileges field.
	
	4. Click OK. Exit and Sign Out of Schedule+ to save the changes to the schedule
	  file.
	
	5. Follow the steps for Procedure A to set the appropriate access privileges for
	  any users, paying special attention to reset the Default privileges as well.
	
	For version 7.0:
	
	1. From the Options menu, select Set Access Permissions.
	
	2. From the Set Access Permissions dialog box, remove all access permissions for
	  users by first highlighting the user in the Users filed, then by clicking the
	  Remove button. Once done, click OK to save the changes to the schedule file.
	
	3. Follow the steps for Procedure A to set the appropriate access permissions
	  for any users.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in versions 1.0 of Microsoft
	Schedule+ for Windows and version 7.0 of Microsoft Schedule+ for Windows 95. We
	are researching this problem and will post new information here in the Microsoft
	Knowledge Base as it becomes available.
	
	MORE INFORMATION
	================
	
	If the access privileges/permissions have been set, but the user cannot access
	the schedule file, there may be corruption in the schedule file. Following the
	appropriate procedure above may resolve this. If the procedure above does not
	resolve the issue, then the corruption in the schedule file is too severe, and
	it may be necessary to restore the file from backup.
	
	Additional query words: schedule plus 1.00 7.00 .cal .sch .scd
	
	======================================================================
	Keywords          :  
	Technology        : kbScheduleSearch kbSchedule700 kbSchedule100
	Version           : WINDOWS:1.0,7.0,95
	
	=============================================================================
	

{% endraw %}
