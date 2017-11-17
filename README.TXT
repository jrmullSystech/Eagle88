Eagle88 	Readme.txt 			
*****************************************************************
Copyright 1997 Systech Software Products, Inc.
*****************************************************************

These set of files contain the User manual document files for Eagle88 version 1.02.  Eagle88 is an IBM mainframe programming utility and operates on the MVS operating system.  It's purpose is to provide advanced file compares, copying, and data modifications.  For a pre-view of Eagle88 tasks see the sample.doc file.



Make sure the following files were extracted from your download.
=================================================================
Readme.txt	This file

contents.doc	Manual documents in MsWord 2.0 format
intro.doc	Overview
command.doc	Command format and usage
samples.doc	Examples of Eagle88
errormsg.doc	Error codes and messages
lesson.doc	Tutorial
install.doc	Installation steps for load module
 
install.jcl	Pre-coded installation jcl (see install.doc)

eagv102.jcl	Tutorial jcl examples
eagv102.dat	Tutorial example data file

eagle80.obj	Object code module
eagle81.obj	
eagle82.obj
eagle83.obj
eagle84.obj
eagle85.obj
eagle86.obj
eagle87.obj
eagle88.obj



Installation steps.
====================

1)  The manual documents should be saved on your LAN or local drive for reference.  Section G, Install.doc should be printed for your review.

2)  The OBJ files need to be transmitted to the mainframe using irma, Rumba, or other send/recieve tools.  Below is an example of irma's send command. Treat the OBJ as a binary file.  They will be link-edited once they are on the mainframe.

3)  The JCL and DAT files need to be transmitted with the CRLF and ASCII translate options  These are text files.

Note: 

It is required that you pre-allocate the mainframe receiving files to be LREC=80,BLKSIZE=800,RECFM=FB.  OBJ needs 10 tracks.  DAT and JCL use 5 tracks.  If you do not pre-allocate as requested, the IEHUPDTE install steps will fail.

Example:
========
SEND  A:EAGLE80.OBJ   	'company.EAGLE80.OBJ'
SEND  A:EAGLE81.OBJ   	'company.EAGLE81.OBJ'
SEND  A:EAGLE82.OBJ   	'company.EAGLE82.OBJ'
SEND  A:EAGLE83.OBJ   	'company.EAGLE83.OBJ'
SEND  A:EAGLE84.OBJ   	'company.EAGLE84.OBJ'
SEND  A:EAGLE85.OBJ   	'company.EAGLE85.OBJ'
SEND  A:EAGLE86.OBJ   	'company.EAGLE86.OBJ'
SEND  A:EAGLE87.OBJ   	'company.EAGLE87.OBJ'
SEND  A:EAGLE88.OBJ   	'company.EAGLE88.OBJ'
SEND  A:EAGV102.DAT   	'company.EAGV102.DAT' 	CRLF ASCII
SEND  A:EAGV102.JCL   	'company.EAGV102.JCL'   CRLF ASCII
SEND  A:INSTALL.JCL   	'company.INSTALL.JCL'   CRLF ASCII


The Install.JCL file contains sample jcl matching the installation section in the User manual.  Use this jcl as a time saver instead of creating your install jcl from scratch.  

Now that your files on the mainframe, refer to the Eagle88 installation Section G for step by step installation. 


John R. Mull
Systech Software Products, Inc.
e-mail jrmull@eagle88.com
Phone  (630) 759-4805

