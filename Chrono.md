

# Features #
This SAP framework provides a chronometer tools that records program's parameter at chrono start. This framework is usefull on report program that sometimes get into timeout or too long processing time.

This framework allow to record all set of program parameters used by user in order to analyse them one by one or all at once in order to :
  1. Improve report performances => reduce runtime or prevent timeout
  1. Provide wanring to user => Send warning message to user on parameter's configurationt that is known to lead to timeout
  1. other analyses

This framework is **only** a way to gather informations you'll have to analyse afterward.

Here is the features/methods :
  * START : Start a new Chonometer
  * STOP : Stop the created Chronometer
  * RESTART : Start the created Chronometer
  * RESET : Cancel the created Chronometer
  * ADD : Add number of objects processed during start and stop

# Method START #
The start method do the following actions :
  * Get Workprocess Informations (Server name, Workprocess ID, ...)
  * Get transaction informations (Transaction ID, ...)
  * Get background job informations if applies (Job Name, ... )
  * Get program informations (Program name, Variant name, User, date & time, ...)
  * Create new Chronometer record
  * Get program's parameters values
  * Strore in database

# Method STOP #
The stop method do the following actions :
  * Check that curent Chronometer exists (Start has been called)
  * Get curent time
  * Compute elapse time
  * Update database

# Method RESTART #
The restart method do the following actions :
  * Check that current Chronometer exists (Start has been called)
  * Save curent time for the next stop
  * Refresh elapse time
  * Update database

# Method RESET #
The reset method do the following actions :
  * Clear all current information
  * cancel current Chronometer

# Method ADD #
The add method do the following actions :
  * Add specified number of processed items to the total items processed
  * Add specified number of returned items to the total items returned
This to fields could use to compute, report by report, run speed based either on processed items (record read) or returned items (lines provided to the output either file or screen).

Note : This could also be used on injection program where processed items (or returned item) is the number of object created into SAP.

The goal of this quantity record is to create (either on processed or returned item) a "speed" value that is quite stable on all (or almost all) run of a report. Archiving this allow to monitor change on this "speed" value and trigger alarms on report's performance that may be due to database volume increase and need reaction like :
  1. Rebuilding indexes statistics
  1. Running report with ABAP trace on
  1. Create new index
  1. Ask report change
  1. ...

# Standard Method call order #
Here is the order methods should be generally called :
  1. Start
  1. Add
  1. ...
  1. Add
  1. Stop
  1. Restart
  1. Add
  1. ...
  1. Add
  1. Stop
  1. Reset
  1. Start
  1. ...
  1. Stop

# Installation #
You must first use ZAPLink Framework to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-DBA) and use transaction ZLINK from the ZAPLink Framework to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-DBA) of this tool if exists.