# List of tasks for the Project: Juul Timesedler

## Refactor

* For more flexibility all workers should be able to access and send in their timesheets on all current projects
* Is class ApplicationStartingNotificationHandler necessary ?
* Refactor FE, separation of concerns - move code into classes and services

## TODOs and Errors

* Ask Rasmus about settings for case sensitivity in DTOs / NewtonSoft

## Frontend tasks

* Populate all weekdays (not only Monday) with GUI functionality
  * **WIP** Start out using hardcoded values
  * Refactor models so each weekday has it´s own set of variables
    * Maybe use arrays to hold these
* Fetch timesheets from BE and present them to user in FE app
* Add calendar so workers can browse back in time to see submitted timesheets (and download PDF documents of the given week)
  * From calendar populate tabs with weekdays with dates
    * EG. Monday 14th, Tuesday 15th etc.
* Add extra button for downloading PDF for given week to UI. This button can only be pressed when the given week has been submitted to backend

## Backend tasks

* Build API that serves ~~all~~ the timesheet for a given worker for a given week
* Build API and BE service that can provide a PDF for download of the week the worker has browsed to in the calendar

## Umbraco

---

## DONE tasks :)

* Add clear seach button and functionality to search box
* Defined tasks fetched from BE does not appear on FE task list
  * Fixed with async / await
  * Can fetch tasks - ~~~cannot~~~ can present them in FE
  * Fetch and present predefined tasks
    * Not using predefined tasks any longer
    * Using tasks defined in BE through GUI
* StartTime and EndTime does not contain hours + minutes when recieved on BE
  * times should be passed down to component
* Build API that serves tasks defined in Umbraco
  * Tasks are now grouped
  * Tasks can be created and edited through Umbraco GUI
* Pass down StartTime and EndTime to time-picker component
  * Learned about Input(), Observable/subscribe
* Build model for a task (in Umbraco)
* Build a holder model for tasks (in Umbraco)
* Instantiate task holder and examle tasks (in Umbraco)

---

## Developer workflow

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

## OBSOLETE

* ~~Add some kind of list (datatype) to content type in Umbraco so multiple workers can be assigned to a project~~
