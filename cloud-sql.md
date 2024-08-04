## Cloud SQL

### Cloud SQL - Point-in-time-recovery (PITR)  
Point-in-time recovery (PITR) helps you recover an instance to a specific point in time. For example, if an error causes a loss of data, you can recover a database to its state before the error occurred.

`PITR` always creates a new instance; you can't perform a PITR to an existing instance. The new instance inherits the settings of the source instance, similar to how clone creation works. However, for the new instance to inherit these settings, the instance's state must be `RUNNABLE`.  

When you create a Cloud SQL instance in the Google Cloud console, PITR is enabled by default.  
`PITR` uses binary logging to archive logs.  
