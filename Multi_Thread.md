
# Context #
When developing interfaces on SAP ABAP, you might be faced to big (or huge) amount of objet to integrate into SAP :
  1. 100K accounting document
  1. 200K orders
  1. ..
Some of theeses object have "Direct Input" Programs like:
  1. RFBIBL00 : For FI Documents
  1. RFKKBIB0 : For FI-CA Documents
  1. RMDATIND : For Material Document
  1. ...
All theeses Direct Input Program might be used from [Legacy System Migration Workbench (LSMW)](http://help.sap.com/saphelp_nw04s/helpdata/en/ad/2d54a41d7011d2b42e006094b944c8/frameset.htm).
When you can't use Direct Input because:
  1. There is not Direct Input for you object type
  1. Direct Input is not working well for your objects (some part of you object might not be handled by Direct Input)
  1. ...
You might be using [Parallel Processing Jobs with Asynchronous RFC](http://help.sap.com/saphelp_46c/helpdata/en/c4/3a7f1f505211d189550000e829fbbd/frameset.htm) This "technology" allow you to use dialog process to do a "small" part of all the work you have to do.
You will have to create and call function and handle RFC failures.

This SAP Framework is an alternative to the "standard" Parallel Processing.

# Features #
This tool provide you a framework to:
  1. Split what you have to do in many pieces
  1. Handle each piece by a batch process (no time out)
  1. Allow you to add (or remove) some engine to process the whole pieces
  1. Dispatch engine on your servers using round-robin method
  1. Communicate between threads
  1. Watch for job ends
  1. ...
All theese features could be used together or one by one.

# In memories #
This application is dedicated to the memories of Pascal CUENIN, a collegue of mine, who died during the finalization of this framework.
![http://wiki.ygpl.googlecode.com/hg/Pascal.CUENIN.jpg](http://wiki.ygpl.googlecode.com/hg/Pascal.CUENIN.jpg)

RIP.

# Installation #
You must first use ZAPLink Framework V0.0.009 (or higher) to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-MT) and use transaction ZLINK from the ZAPLink Framework to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-MT) of this tool.
This tools needs "[Unlock on Commit](Unlock_on_Commit.md)" framework.

# How to use it ? #
  * Please look at demo program YGPL\_MT\_TUTORIAL
  * Use program YGPL\_MT\_RUN\_CHANGE to add/remove engine or stop all.
  * Use program YGPL\_MT\_RUN\_CLEAR to delete a finished run
  * Use table YGPLMT\_CATEGORY to define your own message categories
  * Use table YGPLMT\_STATUS to define user's status

# Sample code #
No sample code is provided but the tutorial. If you require support on this tools please [join us](https://code.google.com/p/ygpl/#Join_us) and ask for specific support.