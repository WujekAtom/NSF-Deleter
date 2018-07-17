# Delete-Migrated-Mailboxes

// IN PROGRESS

Application for IBM Notes.

Application created for a help during migrating OnPremise users account to IBM Cloud.

Application deletes mailboxes from both servers in cluster at once.
But Domino Administrator has an option to deletes mailbox/database's replica from all servers, so why this app can be useful?
Because in case you have 200, 300 etc. mailboxes to delete from both servers, but the only key that is related to all mailboxes is for example "Department" field in person doc, you cannot easily select all 200 mailboxes.

This application first creates a request for each database. Request can be create on 2 ways:
1. By providing in search window the Key for full-text searching. It will search the Domino Directory for all person docs containing that Key.
2. Importing users from text file. Text file needs to contains mailboxes file name. In most of the organization mailbox name is the same as employee number.
//TODO: Create configuration for choosing which data will be import from text file. [ Choosing a Key ]


## HOW TO USE

1. Application shows output in Java Debug Console of IBM Notes.
On Linux you need to apply following changes to java.security files:


/opt/ibm/notes/java.policy
/opt/ibm/notes/jvm/lib/security/java.policy

and add:

grant{
	permission java.security.AllPermission;
}

2. Before you start, open Java console: from top menu TOOLS -> SHOW JAVA DEBUG CONSOLE.


