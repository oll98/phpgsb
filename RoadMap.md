# Introduction #

phpGSB is a PHP implementation of the Google Safe Browsing API. It's purpose is to allow the creation of PHP applications that can easily make use of the Safe Browsing API without having to worry about the underlying commands.


# Details #

  1. The first task is to enable MAC integrity checks on all lists. Unfortunately this isn't as easy as it first appears as finding a place to store the requested secret key could be troublesome. A configuration type file could be used (with a PHP extension to stop people just opening the file). A table could be used in the database but I'm reluctant to put any more reliance on MySQL.<br><br>
<ol><li>The second task is to export any database related functions to an abstract class. This should allow the use of other database systems than MySQL. A problem that would have to be overcome would be the lack of "transaction (start, commit, rollback)" in other database systems. A log may have to be kept in memory in this case and using this a rollback could then be performed.<br><br>
</li><li>After the class allows other database systems it would be a good idea to create a flat-file XML system out-of-the-box. This would allow users without access to a database system to use phpGSB straight away. Unfortunately this would not benefit from many of the optimizations that database engines have and so optimizations would have to be made in the storage method where possible.<br><br>
</li><li>???<br><br>
</li><li>Implement Google Safe Browsing V3 (if/when its released!)