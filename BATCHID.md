## Creating sample batchid in Talend.

### Code to store in a file
```java
String SRC="CEVA";
String TRAN="MMLG";
String BATCH_ID=SRC+TRAN+TalendDate.formatDate("yyyyMMddHHmmss", new Date());
context.setProperty("BATCH_ID", BATCH_ID);
context.store(new java.io.FileWriter(new java.io.File("D:/batchid.txt")),"My BATCH ID");
```
 ### Code to read from a file
```java
context.load(new java.io.FileReader(new java.io.File("D:/batchid.txt")));
BATCH_ID=context.getProperty("BATCH_ID");
```
