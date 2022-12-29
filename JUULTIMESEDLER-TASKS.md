# List of tasks for the Project: Juul Timesedler

## Refactor
* For more flexibility all workers should be able to access and send in their timesheets on all current projects

## Frontend tasks
* Fetch timesheets from BE and present them to user in FE app
* Fetch and present predefined tasks
* Add extra button for downloading PDF for given week to UI. This button can only be pressed when the given week has been submitted to backend 
* Add calendar so workers can browse back in time to see submitted timesheets (and download PDF documents of the given week)

## Backend tasks
* **WIP** Add some kind of list (datatype) to content type in Umbraco so multiple workers can be assigned to a project
  * By default there is no multi-user picker

* Build API that serves all timesheets for a given worker
* Build API that serves tasks defined in Umbraco
* Build API and BE service that can provide a PDF for download of the week the worker has browsed to in the calendar

---

## DONE :)
### Developer workflow
[https://github.com/Brianmanden/juultimesedler-tools/tree/main/DB%20Backup-restore](https://github.com/Brianmanden/juultimesedler-tools/tree/main/DB%20Backup-restore)
* Create script / batch file / console app to create backup and restore of database files
  * Locations
    * Source - [E:\]PROJEKTER\juultimesedler-be\juultimesedler-be\umbraco
    * Destination - [E:\]PROJEKTER\juultimesedler-backup\be
  * Config file
    * Used for locations
  * Parameters
    * --BU
      * Used for backup
      * Should be named with current date and timestamp - EG.[YYYY-mm-dd_hh-mm]
    * --RS
      * Gives a list of backups to choose from
      * List is generated from the backups found in the destination folder given in config file
      * User's choice of backup should be restored (overwrite files) to source folder given in config file