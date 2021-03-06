---
layout: page
title: "Q178640: Could Not Find Domain Controller When Establishing a Trust"
permalink: /kb/178/Q178640/
---

## Q178640: Could Not Find Domain Controller When Establishing a Trust

{% raw %}

	Article: Q178640
	Product(s): Microsoft Windows NT
	Version(s): WinNT:3.51,4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 09-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation versions 3.51, 4.0 
	- Microsoft Windows NT Server versions 3.51, 4.0 
	-------------------------------------------------------------------------------
	
	IMPORTANT: This article contains information about editing the registry.
	Before you edit the registry, make sure you understand how to restore it
	if a problem occurs. For information on how to do this, view the "Restoring
	the Registry" online Help topic in Regedit.exe or the "Restoring a Registry
	Key" online Help topic in Regedt32.exe.
	
	SYMPTOMS
	========
	
	Regardless of the protocols being used, You may receive the following error
	message:
	
	  Could not find domain controller for this domain.
	
	The same error can occur even though LMHOSTS files and the WINS database are
	correct. No connectivity problems of any kind exist on the network.
	
	CAUSE
	=====
	
	A mechanism was provided with Windows NT 4.0 Service Pack 3 and in a hotfix for
	Windows NT 3.51 that allows for administrators to restrict the ability for
	anonymous logon users (also known as NULL session connections) to list account
	names and enumerate share names.
	
	This registry setting also restricts a trusting domain from establishing a
	connection to the trusted primary domain controller to establish a trust
	relationship.
	
	RESOLUTION
	==========
	
	Set the RestrictAnonymous value to 0 in the registry, or remove the value and
	the trust can be established.
	
	WARNING: Using Registry Editor incorrectly can cause serious problems that may
	require you to reinstall Windows. Microsoft cannot guarantee that problems
	resulting from the incorrect use of Registry Editor can be solved. Use Registry
	Editor at your own risk.
	
	For information about how to edit the registry, view the "Changing Keys And
	Values" online Help topic in Registry Editor (Regedit.exe) or the "Add and
	Delete Information in the Registry" and "Edit Registry Data" online Help topics
	in Regedt32.exe. Note that you should back up the registry before you edit it.
	
	1. Run Registry Editor (Regedt32.exe).
	
	2. Go to the following key in the registry:
	
	  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\LSA
	
	3. Select the following value:
	
	  RestrictAnonymous
	
	4. On the Edit menu, click DWORD and change the data (value) to 0, as reflected
	  in the following information:
	
	  Value Name: RestrictAnonymous
	  Data Type:  REG_DWORD
	  Value:      0
	
	5. Exit Registry Editor and restart the computer for the change to take effect.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT versions 3.51 and
	4.0. We are researching this problem and will post new information here in the
	Microsoft Knowledge Base as it becomes available.
	
	MORE INFORMATION
	================
	
	The purpose of the registry value is to configure local system policy for
	whether authentication is required to perform common enumeration functions.
	Requiring authentication to obtain the account name list is an optional feature.
	When the RestrictAnonymous value is set to 1, anonymous connections from the
	Graphical User Interface tools for security management will receive an access
	denied error when attempting to get the list of account names. When the
	RestrictAnonymous value is set to 0, or the value is not defined, anonymous
	connections will be able to list account names and enumerate share names. It
	should be noted that even with the value of RestrictAnonymous set to 1, although
	the user interface tools with the system will not list account names, there are
	Win32 programming interfaces to support individual name lookup that do not
	restrict anonymous connections.
	
	Windows NT networks using a multiple domain model can restrict anonymous
	connections without loss of functionality. The initial steps in planning to
	disable anonymous connections is for administrators in resource domains to add
	members of trusted account domains to specific local groups as needed before
	changing the value for the LSA RestrictAnonymous registry entry. Users logged on
	using accounts from trusted account domains will continue to use authenticated
	connections to obtain list of account names to manage security access control.
	
	
	Additional query words: restrict anonymous security
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT351search kbWinNT400search kbWinNTW351search kbWinNTW351 kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWinNTS351 kbWinNTS351search
	Version           : WinNT:3.51,4.0
	Hardware          : x86
	Issue type        : kbbug
	
	=============================================================================
	

{% endraw %}
