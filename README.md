# CA_notifications
 
Review the existing file.

All entries MUST have a unique ID value AND entry.  This is used for the ability to dismiss any notification

Name is the "title" of the popup.  If this entry is missing, then the text that the system is looking for will be used instead

Banner is what will appear in the banner

PopUp is the full description that appears if the user clicks on more info

email is the short description that will be sent as the description in the email body

NOTE: ANY syntax errors in the JSON will prevent any notification from being sent out.

Searches for docker containers can either be akin to mccloud/ps3netsrv (searches for :latest), mccloud/ps3netsrv:alpine (searches for alpine) or mccloud/ps3netsrv:* (searches for any tag)

Searches for plugins can either be by the filename (disklocation.plg) or via the full pluginURL to refine the search if necessary

The code block if used must return either true (conditions met) or false (conditions NOT met).  IE: the return command has to be present

unraid compares against unraid versions

plugin compares against the version of the installed plugin

The possible operators are: <, lt, <=, le, >, gt, >=, ge, ==, =, eq, !=, <>, ne respectively.  This parameter is case-sensitive, values should be lowercase.


NOTE:  As a general rule, the entry is used as the search parameter to determine if the container or plugin is installed.

But, because the entry must also be unique, if there are multiple warnings that need to be issued against a certain plugin (or if only code is to be used to determine the banner or not, then the entry can be anything and an additional element "Force" should be set to be true.

This means that the tests for the plugin installed or not are skipped and the only test performed is the code block.  This block then would have to determine the appropriate versions, etc 
