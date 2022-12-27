# List of tasks for the Project: Juul Timesedler

## Developer workflow
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

## Frontend tasks
* Fetch timesheets from BE and present them to user in FE app
* Fetch and present predefined tasks

## Backend tasks
* **WIP** Add some kind of list (datatype) to content type in Umbraco so multiple workers can be assigned to a project
  * By default there is no multi-user picker

* Build API that serves all timesheets for a given worker
* Build API that serves tasks defined in Umbraco