# Time-sheet Manager
An application to manage time sheet of employees

## use cases
* Users should be able to create account, change password.
* Managers should able to assign hours for users.
* User should able to fill timesheet and submit to Manager(s).
* Managers can approve/reject timesheets sent by users.
* Notification needs to be sent to people who has not filled timesheets and to Managers who has not assigned hours.
* Managers can create custom group of people whom he/she wants to assign timesheets to.
* Various analytics reports like needs to be generated by end of each week or on trigger.
* Admin can add/remove Projects.
* Admin can assign managers to projects.

## System constrains
* This should be highly sacalable. Eg It should support up to one million employees and 10k projects
* Timesheet will be filled on any day of week so the system should be highly availble
* The system load might be irregular. We might have high load on friday/monday

## Abstact design

### system components

* User - [userId,ProjectIds,RoleIds,...]
* Project - [ProjectId,ProjectOwnerIds,...]
* TimeSheet- [timeSheetId,ProjectId,userId,createrId,timeSheetStatus,StartTime,endTime,totalHours...]
* Notification- [eventId,eventDescription,TriggerCondition,...]
* Roles - [roleId,resourceAccess,...]
* Analytics- [batchId,batchExec,frequency,outFormats,...]
