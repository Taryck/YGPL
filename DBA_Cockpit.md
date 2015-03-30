

# Features #
This SAP tool provides a cockpit for DBA with the followings features :
  1. Table size (including indexes & blobl)
  1. Check Table's Indexes
  1. Check Table's Indexes using statistics
  1. Check Indexes for mandant

# DBA Cockpit Menu #
Here is the DBA Cockpit menu :
![http://wiki.ygpl.googlecode.com/hg/YGPL.DBA_Cockpit.png](http://wiki.ygpl.googlecode.com/hg/YGPL.DBA_Cockpit.png)

# Selection Screens #
All theese tools have the same selection screen and the same selection process to get table list against which controls have to be made:
![http://wiki.ygpl.googlecode.com/hg/YGPL.DBAC.IndexCheck.Sel.jpg](http://wiki.ygpl.googlecode.com/hg/YGPL.DBAC.IndexCheck.Sel.jpg)

Selection fields :
  * Original System : Original system ID of the table
  * Software Component : Software Component of the table
  * Table Name : Table Name
  * Package : Package of the table
  * Extend to sub-packages : When package range is defined, package included into the selected package are also selected
  * Person Responsible : Person reponsible of the table (responsible in TADIR table)
  * Table Size (MB) : Minimum table size (including indexes and blob) to select the table

# Table size #
Return table size in Database like in transaction DB02OLD and adding table's indexes and table's blob (binary data for table's fields type string, xstring, ....)

Until now this program work **only on Oracle**.

## Result list ##
![http://wiki.ygpl.googlecode.com/hg/YGPL.DBAC.TableSize.Res.jpg](http://wiki.ygpl.googlecode.com/hg/YGPL.DBAC.TableSize.Res.jpg)

Columns :
  * Table Name : Name of the Table
  * Size (MB) : Size in MB of table + Indexes + Blob (if applies)
  * % of DB : % of overall database size that table and indexes (& blob) represents
  * Original System of Object : Object source system ID
  * Pers. Resp. : Person reponsible of the table (responsible in TADIR table)
  * Package : Package that this table belongs to
  * Comp. : Sofware component
  * Component : Application component ID
  * Namespace : Table's namespace

# Check Table's Indexes #
Check the selected tables. This action is exactly the same as the "check button" on table display in transaction SE11.

**Only messages like** "Index &-& completely contains the fields of index &" are returned.

## Result list ##
![http://wiki.ygpl.googlecode.com/hg/YGPL.DBAC.TableIndexCheck.Res.jpg](http://wiki.ygpl.googlecode.com/hg/YGPL.DBAC.TableIndexCheck.Res.jpg)

Columns :
  * Table Name : Name of the Table
  * Idx : Index name that warning is about
  * Size (MB) : Size in MB of table + Indexes + Blob (if applies)
  * % of DB : % of overall database size that table and indexes (& blob) represents
  * Idx : Index name that contains more fields as the other index (column #2)
  * Reason of the waring : Warning message produce in table's protocol (Transaction SE11 check table)
  * Original : Object source system ID
  * Pers. Resp. : Person reponsible of the table (responsible in TADIR table)
  * Package : Package of the index (extension index) or package of the table (normal index)
  * Comp. : Sofware component
  * Component : Application component ID
  * Namespace : Table's namespace

# Check Table's Indexes using statistics #
Check the selected tables. This action is the same as the "check button" on table display in transaction SE11.

**Only messages like** "Index &-& completely contains the fields of index &" are returned.

Before comparing indexes, index's fields that **only have one possible value** are removed from index definition before calling check function. Indexes that do not have common fields list might be reported as because field that make the difference is useless because has **only one** distinct value.

This analyze must be done **ONLY in productive SAP system**. This analyze must be compared with the standard table check in SE11. Only "new indexes" that are not listed in SE11 should be investigated.

## Result list ##
Same as "_Check Table's Indexes_" tool.

# Check Indexes for mandant #
Check that tables with a client field as part of the primary key also have this client field in every indexes of the table.

## Result list ##
![http://wiki.ygpl.googlecode.com/hg/YGPL.DBAC.IndexCheck.Res.jpg](http://wiki.ygpl.googlecode.com/hg/YGPL.DBAC.IndexCheck.Res.jpg)

Columns :
  * Table Name : Name of the Table
  * Field : Field that is part of the table's key and that kind is CLNT (Client)
  * Ind : Index name that do not contains any client field
  * Domain : Domain of the key client field defined in "Field" field
  * Unique : Set an "X" if the index is unique
  * Author : Person who has created the index
  * Date : Index creation date
  * Time : Index creation time
  * Original : Object source system ID
  * Pers. Resp. : Person reponsible of the table (responsible in TADIR table)
  * Package : Package of the index (extension index) or package of the table (normal index)
  * Comp. : Sofware component
  * Component : Application component ID
  * Namespace : Table's namespace
  * Size (MB) : Size in MB of table + Indexes + Blob (if applies)
  * % of DB : % of overall database size that table and indexes (& blob) represents

# Installation #
You must first use ZAPLink Framework to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-DBA) and use transaction ZLINK from the ZAPLink Framework to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-DBA) of this tool if exists.