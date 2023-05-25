# File Transfer for Linux/Unix #

## General ##
The example program shows the usage other the following Natural File Transfer functionality:

* DOWNLOAD PC COMMAND - Send a command to the client
* DOWNLOAD PC - Client downloads data
* UPLOAD PC - Client uploads data

## Requirements ##

You can use Entire Connection of NaturalONE as client. For NaturalONE you need the following setup:

* NaturalONE version 9.2.1 Fix 5 or newer
* Natural on Linux 9.2.1 Fix 6 or newer

## Program Description ##
Step by step:

* Enable use of Natural Connection & define work file type as transfer
* Setup user input page
* Check if D for download of U for upload is set by the user
* If a path is given use DOWNLOAD PC COMMAND to set the target path for download or upload
* Download or upload the #MESSAGE field
