
# Context #
When developing in SAP ABAP, you'll probably use READ TABLE command to read internal tables. This command might have the following variants that will impact the performance :
  1. Standard Table : READ TABLE BINARY SEARCH WITH KEY
  1. Sorted Table : READ TABLE WITH TABLE KEY
  1. Hashed Table : READ TABLE WITH TABLE KEY
Which variant should you use?

# Features #
This tutorial makes severals READ TABLE on each kind of table with different table size and providing you read speed (count & delay).
Please find below the result for READ from tables with 1K entries up to 32M :

http://wiki.ygpl.googlecode.com/hg/READ_TABLE.JPG

As you can see :
  1. Hashed table (H) are barely impacted by table Size
  1. Sorted table (S) are more resistant with high table size (> 1M)
  1. Standard table with Binary Search (B) are as fast as Sorted table with low table size (< 1M)
**Note :** Please also note that table line size might impact the read results, make your own tests with this tools.

# Installation #
You must first use ZAPLink Framework to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-RT) and use transaction ZLINK from the ZAPLink Framework to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-RT) of this tool.