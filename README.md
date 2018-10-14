# NSF Deleter

// IN PROGRESS

Application for IBM Notes.

Application lets to delete many NSF files from single instance or cluster instance servers. You can import files names from a text file and in configuration set the folder path where files resides.
Or you can search in Domino Directory person docs by providing key.

This application first creates a request for each database. Request can be create on 2 ways:
1. By providing in search window the Key for full-text searching. It will search the Domino Directory for all person docs containing that Key.
2. Importing users from text file. Text file needs to contains mailboxes file name with or without folder name. This can be set in CONFIGURATION page.


## HOW TO USE

1. Application shows output in Java Debug Console of IBM Notes.
On Linux you need to apply following changes to java.security files:
```
/opt/ibm/notes/java.policy
/opt/ibm/notes/jvm/lib/security/java.policy
```

and add:
```
grant{
	permission java.security.AllPermission;
}
```

2. Before you start, open Java console: from top menu TOOLS -> SHOW JAVA DEBUG CONSOLE.


## PREPARATION - CONFIGURATION

Before you start, fulfill the configuration tab.
- "Server with Domino Directory" - use in SCENARIO 1. Server where you can search for users' mailboxes. This can be one of cluster's node. Important: this should be the replica of cluster's nodes Domino Directory.
- "Delete databases from single server" - name of the single instance server, non-clustered. Databases will be delete only from this one server.
- "Delete from single server - YES/NO" - If you set YES, then deletion will perform only on server pointed in corresponding field. If you set NO, then deletion will perform on both cluster's nodes selected in Configuration
- "Delete db from cluster 1" - name of the first cluster's node, if you want to deleted from clustered servers
- "Delete db from cluster 2" - name of the first cluster's node, if you want to deleted from clustered servers
-Default prefix for databases" - in case you are importing databases file name form the file and file does not contains path, only file names, you can set it globally here. If you leave empty, then the file path will be read from file, example: mail/qazwsx.nsf

All outputs and errors you can find by opening Java console form top menu Tools -> Show java debug console.

## SCENARIO 1: Search in Domino Directory
Searching in Domino Directory is useful if you need to find databases/mailboxes for a users that has something in common: the same department code, the same mail server, the same mail path, the same surname of first name, the same location etc.

1. Click button "Search in Domino Directory" and provide key to search. Key can be anything. Searching in Domino Directory is make by FullTextSearch.
2. In case you are going to delete databases from cluster's server, you should push the button Check replicas on server". Method will lookup to both cluster's node you specified in Configuration and check if databases exist on that nodes.
3. If you check the existing in cluster's nodes, you can push the button "Delete databases"

## SCENARIO 2: Import databases from file

Text file with one database file name in row, for example:
mail/qazwsx.nsf
mail/trew.nsf
...

If file name does not contains extension ".nsf", application will add it automatically.

1. In configuration set prefix/path for files. If empty, then it will read it from file.
2. Push the button "Import from file", choose file.
3. In case you are going to delete databases from cluster's server, you should push the button Check replicas on server". Method will lookup to both cluster's node you specified in Configuration and check if datasbes exist on that nodes.
