
# Context #
When developing in SAP ABAP you might need to store informations of various format in the database.
You can use :
  1. "[EXPORT parameter\_list TO DATABASE](http://help.sap.com/saphelp_banking463/helpdata/EN/34/8e73a36df74873e10000009b38f9b8/frameset.htm)" to export data to database
  1. "[CALL TRANSFORMATION ID](http://help.sap.com/abapdocu_70/en/ABAPCALL_TRANSFORMATION.htm)" to transform any data to XML
  1. "[Class CL\_ABAP\_GZIP](http://help.sap.com/abapdocu_70/en/ABENCL_ABAP_GZIP.htm) to compress data

# Features #
This SAP tool provide you an easy way to store (and retrieve) information from any format :
  1. Deep-Structure
  1. Tables
  1. Objects
  1. or combinaison of this kind of data

# Installation #
You must first use ZAPLink Framework to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-DS) and use transaction ZLINK from the ZAPLink Framework to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-DS) of this tool.

# How to use it ? #
You just need to create a store using the engine : YGPL\_DS\_ENGINE=>NEW\_STORE( ).
Add content to the store : o\_store->ADD\_INFO( name = name value = value).
Save store to database : o\_store->SAVE( ).

To retrieve your data Get the store from the Database : YGPL\_DS\_ENGINE=>GET\_STORE( id ).
Get content from the store : o\_store->GET\_INFO( EXPORTING name = name CHANGING value = value).
Please look at demo program YGPL\_DS\_TUTORIAL