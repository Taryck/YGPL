
# Context #
When using [transaction SAP SGEN](http://help.sap.com/saphelp_sm32/helpdata/en/b1/52583c65399965e10000000a114084/frameset.htm) you can either :
  1. Generate All Objects of Selected SAP Software Components (excluding home)
  1. Regenerate After an SAP System Upgrade
  1. Regenerate the objects of the last run
  1. Regenerate Existing Loads
  1. Generate the objects of a transport request
  1. Generation of BSP Application
  1. Generation of Web Dynpros
This limited choice prevent you from making your own selection like :
  1. All customer specific components (Software component HOME)
  1. All objects of a package
  1. ....

# Features #
This SAP tool allow you to make more flexible selection of _programs_ to generate based on :
  1. Source system
  1. Software Component (including home)
  1. Package (can be extended to sub-package)
  1. Component type
  1. Component name
  1. Person Responsible

By _programs_ we means :
  1. Programs (SE38)
  1. Classes (SE24)
  1. Function groups (SE37)
  1. Type pools (SE11)
  1. Logical Databases
  1. ...

# Screen shoots #
Please find below some screen shots :
  1. Selection screen that define the range of the scanned programs
  1. Result list providing the list of the indexes updated

## Selection Screen ##
![http://wiki.ygpl.googlecode.com/hg/YSGEN.Sel.scr.jpg](http://wiki.ygpl.googlecode.com/hg/YSGEN.Sel.scr.jpg)

## Result list ##
![http://wiki.ygpl.googlecode.com/hg/YSGEN.Res.scr.jpg](http://wiki.ygpl.googlecode.com/hg/YSGEN.Res.scr.jpg)

# Installation #
You must first use ZAPLink Framework to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-SGEN) and use transaction ZLINK from the ZAPLink Framework to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-SGEN) of this tool.