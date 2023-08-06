# List of tasks for the Project: Juul Timesedler

## Known problems

* How to best handle transitioning to a new year ?

## Refactor

* For more flexibility all workers should be able to access and send in their timesheets on all current projects
* Is class ApplicationStartingNotificationHandler necessary ?
  * Mostly likely not
* Refactor FE, separation of concerns - move code into classes and services
  * Refactoring into using Blazor instead.
* Refactor into components
  * Each component should fetch it´s own data from BE
  * While loading data for each component a spinner should be shown - remove spinner when data is loaded

## TODOs and Errors

* In general use more precise wording of classes and services !
* Separation of concerns and good code practises are still important. There is room for improvement here !

## Frontend tasks

* Disable all fields / editors / pickers on the form if timesheet is in 'locked' state
* Make a check on starting time comes before ending time
  * Mark with visual warning of some sort if rule is broken
* Show spinner (or other similiar gfx) while loading data
* Show error message if loading of data does not work
* Populate all weekdays (not only Monday) with GUI functionality
  * **WIP** Refactor models so each weekday has it´s own set of variables
* Fetch timesheets from BE and present them to user in FE app
* Add calendar so workers can browse back in time to see submitted timesheets (and download PDF documents of the given week)
  * From calendar populate tabs with weekdays with dates
    * EG. Monday 14th, Tuesday 15th etc.
* Add extra button for downloading PDF for given week to UI. This button can only be pressed when the given week has been submitted to backend

## Backend tasks

* When sending a timesheet older than current week it should have a 'locked' state set (property) so the worker can´t keep on editing it
* Build API that serves ~~all~~ the timesheet for a given worker for a given week
* Build API and BE service that can provide a PDF for download of the week the worker has browsed to in the calendar

## Umbraco

---

## DONE tasks :)

* Make a switch to using MudBlazor instead of Angular => works great :)
* Upgrade Angular (ver. 15. seems to work)
* Populate weekday tabs by looping over data fetched for current timesheetweek
* Refactor models and DTOs - FE & BE
* Add hardcoded GUI to weekday tabs
  * Start out using hardcoded values
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
