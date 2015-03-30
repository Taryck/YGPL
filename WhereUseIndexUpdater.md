
# Context #
When developing in SAP ABAP, it is often usefull to know where such component is used. This functionality is trigered by the ["Where-Used list"](http://help.sap.com/saphelp_nw70/Helpdata/en/d1/80198c454211d189710000e8322d00/frameset.htm) button and provided by the read of "Where-used" indexes tables.
This table are not always up to date, so usecase result list might be :
  1. Empty
  1. with mising result
How could I reli on this result list ?

**Note :** After an upgrade the optional action is to run program SAPRSEUB that update index for tho whole system. This program submit program SAPRSEUI. This second program allow to update index for only one package.

# Features #
This SAP tool alows to rebuild list of component that a program use. It's action is similar to the menu's action in SE38.
You define a range of objects (report, class, function group, ...) with the following crieteras from TADIR (component repository) :
  1. Source system
  1. Person Responsible
  1. Package
  1. Component type
  1. Component name

By program we means :
  1. Program (SE38)
  1. Classes (SE24)
  1. Function groups (SE37)
  1. Type pool (SE11)
  1. Logical Database
  1. ...

# Screen shoots #
Please find below some screen shots :
  1. Selection screen that define the range of the scanned programs
  1. Result list providing the list of the indexes updated

## Selection Screen ##
![http://wiki.ygpl.googlecode.com/hg/WhereUse.Sel.scr.jpg](http://wiki.ygpl.googlecode.com/hg/WhereUse.Sel.scr.jpg)

## Result list ##
![http://wiki.ygpl.googlecode.com/hg/WhereUse.Res.scr.jpg](http://wiki.ygpl.googlecode.com/hg/WhereUse.Res.scr.jpg)

# Installation #
You must first use ZAPLink Framework to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-WUIU) and use transaction ZLINK from the ZAPLink Framework to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-WUIU) of this tool.