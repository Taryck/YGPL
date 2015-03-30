
# Context #
When developing in SAP ABAP Object, it is often usefull when you have an existing development and you want to provide API, to copy Class to Interface.

Note : Providing API (interface) allow to "hide" the way you realize to services you provide and avoid external component to use directly your components and beeing widely impacted by any of your changes

# Features #
This SAP tool use [ZAPLink Framework](http://www.zaplink.info/) to read Class and his Super-Class, keep only public definitions (type, attributes, interface, methods) and gather it in a interface
Call transaction : **YGPL\_CLAS2INTF**

# Screen shoots #
None yet.

# Installation #
You must first use [ZAPLink Framework](http://www.zaplink.info/) to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-CL2IF) and use transaction ZLINK from the [ZAPLink Framework](http://www.zaplink.info/) to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-CL2IF) of this tool.