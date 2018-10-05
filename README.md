# NSF Deleter

// IN PROGRESS

Application for IBM Notes.

Application lets to delete many NSF files from single instance or cluster instance servers. You can import files names from a text file and in configuration set the folder path where files resides.
Or you can search in Domino Directory person docs by providing key.

This application first creates a request for each database. Request can be create on 2 ways:
1. By providing in search window the Key for full-text searching. It will search the Domino Directory for all person docs containing that Key.
2. Importing users from text file. Text file needs to contains mailboxes file name. In most of the organization mailbox name is the same as employee number.
//TODO: Create configuration for choosing which data will be import from text file. [ Choosing a Key ]


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


