---
layout: page
title: "Q109847: ScanDisk Err Msg: Directory Tree on This Drive Too Deep..."
permalink: /kb/109/Q109847/
---

## Q109847: ScanDisk Err Msg: Directory Tree on This Drive Too Deep...

{% raw %}

	Article: Q109847
	Product(s): Microsoft Disk Operating System
	Version(s): MS-DOS:6.2,6.21,6.22
	Operating System(s): 
	Keyword(s): 
	Last Modified: 15-NOV-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft MS-DOS operating system versions 6.2, 6.21, 6.22 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When ScanDisk is processing the directory structure, the following error message
	may appear:
	
	  The directory tree on this drive is too deep to examine
	
	CAUSE
	=====
	
	The above error message is generated when a large number of files exist in a
	single directory. The maximum number of files you can include before receiving
	this error depends on the cluster size of the drive and the number of expected
	recursions for ScanDisk.
	
	  Cluster Size of        Maximum Number of Files
	     the Drive                in a Directory
	  -----------------------------------------------
	
	  512 bytes (floppy)   ~ 1280  give or take    16
	    2K                 ~ 5120  give or take    64
	    4K                 ~10240  give or take   256
	    8K                 ~20480  give or take  1024
	   16K                 ~40960  give or take  4096
	   32K                 ~81920  give or take 16384
	
	
	RESOLUTION
	==========
	
	All files must be moved from the original directory to two or more new
	directories so that the maximum number of files (shown above) is not exceeded.
	
	Create the new directories and copy or move a number of files (less than the
	limit shown above) to each directory until all files are copied or moved from
	the original directory. Then, delete the original directory. The original
	directory must be deleted; otherwise, the clusters that were storing the files
	remain attached to the original directory structure. At this point, you may
	rerun ScanDisk.
	
	Additional query words: 6.22 6.20
	
	======================================================================
	Keywords          :  
	Technology        : kbMSDOSSearch kbMSDOS621 kbMSDOS622 kbMSDOS620
	Version           : MS-DOS:6.2,6.21,6.22
	
	=============================================================================
	

{% endraw %}
