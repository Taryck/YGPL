
# Context #
When developing transactional or complexe application in SAP, you'll need to perform locks. While read operation leads to short time and easy lock actions (Lock => Read => Release), write operation leads to more complexes locks : Lock => Write => Commit => Release.
Lock shouldn't be release before commit occurs. When you do commit just after database update it's quite easy, but what append commit are not made on the same procedure ?

# Features #
With this SAP framework you could register for a lock release on Commit (lock are automaticly released on rollback).

# Screen shoots #
None yet.

# Installation #
You must first use [ZAPLink Framework](http://www.zaplink.info/) to install this tool. Download [the last version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3ALastVer+label%3AComp-ULOC) and use transaction ZLINK from the [ZAPLink Framework](http://www.zaplink.info/) to install this tool.
You can also choose [a different version](http://code.google.com/p/ygpl/downloads/list?can=2&q=label%3AComp-ULOC) of this tool.