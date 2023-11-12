# Useful Article And Qs

-   Useful Q&A: [What is the difference between Non-Repeatable Read and Phantom Read?](https://stackoverflow.com/questions/11043712/what-is-the-difference-between-non-repeatable-read-and-phantom-read)
-   Useful article by Microsoft [Transaction Isolation Levels](https://learn.microsoft.com/en-us/sql/odbc/reference/develop-app/transaction-isolation-levels?view=sql-server-ver16)
-   [Lost Update Phenomena](https://www.zghurskyi.com/lost-update/)
-   [Phantom Read Concurrency Problem in SQL Server with Examples](https://dotnettutorials.net/lesson/phantom-read-concurrency-problem-sql-server/)



# Notes

-  when a transaction reads the same row twice but gets different data each time. For example, suppose transaction 1 reads a row. Transaction 2 updates or deletes that row and commits the **update** or **delete**. If transaction 1 rereads the row, it retrieves different row values or discovers that the row has been deleted


   
----

### Q1:
when a transaction reads the same set of rows twice but gets different data each time. For example, suppose transaction 1 reads some rows. Transaction 2 updates or deletes these rows and commits the **update** or **delete**. If transaction 1 rereads these rows, it retrieves different set of rows?
### 	A: phanton

   
----

### Q2: What are the Differences between Repeatable Read and Serializable Isolation levels?

### A:
-   The Repeatable Read Transaction Isolation Level prevents Non-Repeatable Read, Dirty Read, and Lost Update concurrency problems. In order to do this, the Repeatable Read adds additional locks on the data read by the transaction, which ensures that once a transaction reads the data, then those data will be prevented from being read, update or delete by any other transaction. But it allows to insertion of new data into the database, as a result, it does not prevent Phantom Read Concurrency Problem.

-   On the other hand, the Serializable Isolation Level prevents all sorts of concurrency problems such as Non-Repeatable Read, Dirty Read, Lost Update, and Phantom Read. In order to do this, it places a range lock on the data return by the transaction which ensures that once a transaction reads the data, then no other transaction can read, update, delete or insert new data within that range.




