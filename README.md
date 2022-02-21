# things3-db

_Exploring my Things 3 Data_
___

## Step 1. Find the Things 3 Database

On MacOS the Things 3 Database is located here:

```
~/Library/Group Containers/JLMPQHK86H.com.culturedcode.ThingsMac/Things Database.thingsdatabase
```

Inside the 'Things Database.thingsdatabase' package you'll find:

```text
➜  ~ ls -la /Users/danlsn/Library/Group\ Containers/JLMPQHK86H.com.culturedcode.ThingsMac/Things\ Database.thingsdatabase
total 1800
drwx------@ 5 danlsn  staff     160 19 Jan 19:33 .
drwx------  7 danlsn  staff     224 20 Jan 15:48 ..
-rw-r--r--@ 1 danlsn  staff  856064  3 Feb 14:31 main.sqlite
-rw-r--r--  1 danlsn  staff   32768  7 Feb 21:00 main.sqlite-shm
-rw-r--r--  1 danlsn  staff   32768  3 Feb 14:31 main.sqlite-wal
```

Let's see what inside that SQLite Database shall we?

```sqlite
select name
from main.sqlite_master
where type = 'table';
```

** The Stuff I'm interested in is in **Bold**

| name | description |
| :--- | :--- |
| Meta | |
| **TMTask** | Task Table |
| **TMArea** | Area Table |
| **TMTag** | Tag Table |
| TMContact |
| TMMetaItem |
| BSSyncronyMetadata |
| TMSettings |
| **TMTaskTag** | Task-to-Tag Relationship Table |
| **TMAreaTag** | Area-to-Tag Relationship Table |
| **TMChecklistItem** | Checklist Items under Tasks |
| TMCommand |
| TMTombstone |
| ThingsTouch\_ExtensionCommandStore\_Meta |
| ThingsTouch\_ExtensionCommandStore\_Commands |
| sqlite\_sequence |

___

## Step 2. Hack Around the Data

### 1. Output a List of Tasks

```sqlite
select *
from TMTask
limit 5;
```

| uuid | userModificationDate | creationDate | trashed | type | title | notes | dueDate | dueDateOffset | status | stopDate | start | startDate | index | todayIndex | area | project | repeatingTemplate | delegate | recurrenceRule | instanceCreationStartDate | instanceCreationPaused | instanceCreationCount | afterCompletionReferenceDate | actionGroup | untrashedLeafActionsCount | openUntrashedLeafActionsCount | checklistItemsCount | openChecklistItemsCount | startBucket | alarmTimeOffset | lastAlarmInteractionDate | todayIndexReferenceDate | nextInstanceStartDate | dueDateSuppressionDate | leavesTombstone | repeater | repeaterMigrationDate | repeaterRegularSlotDatesCache | notesSync | cachedTags |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 8kkrafXt5aTAzLC3YjErtR | 1642998373.559945 | 1642581216.092397 | 0 | 0 | Convert a to-do into a project | Sometimes you might create a to-do, but realize later that it’s actually a more complex project. No problem! In the toolbar below, click ••• and choose Convert to Project.<br/><br/>These checklist items will become to-dos inside your new project: | NULL | 0 | 2 | 1642998373.559494 | 1 | NULL | -1 | 0 | NULL | NULL | NULL | NULL | NULL | NULL | 0 | 0 | NULL | TzVLEEjjGzMDBCtmezY1Mw | -1 | -1 | 2 | 2 | 0 | NULL | NULL | NULL | -62135769600 | NULL | 0 | NULL | NULL | NULL | 1 |  |
| AsHds3dSiBSHxDtVvT6gB8 | 1642998373.5700321 | 1642581216.088084 | 0 | 0 | Tag your to-dos | Tags allow you to customize your workflow in Things.<br/><br/>For example, you can…<br/>- Use tags for places like “Office” or “Home”.<br/>- Tag all your “Errands”.<br/>- Prioritize to-dos with an “Important” tag.<br/>- Tag the things you’re working on with “Kate”.<br/>- Or you can invent your own tags.<br/><br/>To add a tag, click the tag button below. To see all to-dos with a given tag, use Quick Find to search for it. | NULL | 0 | 2 | 1642998373.5696201 | 1 | NULL | -71 | 0 | NULL | NULL | NULL | NULL | NULL | NULL | 0 | 0 | NULL | TzVLEEjjGzMDBCtmezY1Mw | -1 | -1 | 0 | 0 | 0 | NULL | NULL | NULL | -62135769600 | NULL | 0 | NULL | NULL | NULL | 1 |  |
| XNNTSudVak3rWc7mid9VKZ | 1642998373.5516791 | 1642581216.0918589 | 0 | 0 | Open multiple windows | As you organize your to-dos, it can be very helpful to have multiple lists open side by side. Right-click any list in the sidebar to open it in a new window. | NULL | 0 | 2 | 1642998373.5512 | 1 | NULL | -2 | 0 | NULL | NULL | NULL | NULL | NULL | NULL | 0 | 0 | NULL | TzVLEEjjGzMDBCtmezY1Mw | -1 | -1 | 0 | 0 | 0 | NULL | NULL | NULL | -62135769600 | NULL | 0 | NULL | NULL | NULL | 1 |  |
| XKFidKUa7vZjVSHG7dqCQd | 1642998373.53539 | 1642581216.082135 | 0 | 0 | You’re done! | That’s all you really need to know. Feel free to start adding your own projects and to-dos.<br/><br/>You can come back to this project later to learn the advanced features below. When you’re done with the project, click the progress ring at the top to mark it complete.<br/><br/>We hope you’ll enjoy using Things! | NULL | 0 | 2 | 1642998373.534682 | 1 | NULL | 0 | 0 | NULL | NULL | NULL | NULL | NULL | NULL | 0 | 0 | NULL | GL4GmfkNosDjNcVJMpmTXy | -1 | -1 | 0 | 0 | 0 | NULL | NULL | NULL | -62135769600 | NULL | 0 | NULL | NULL | NULL | 1 |  |
| N1mPguaiucsEAFw2QerTLg | 1642998373.554414 | 1642581216.081061 | 0 | 0 | Create a project | On to bigger things! At the bottom of the sidebar, click “+ New List” to add a project of your own. | NULL | 0 | 2 | 1642998373.553951 | 1 | NULL | -28 | 0 | NULL | NULL | NULL | NULL | NULL | NULL | 0 | 0 | NULL | GL4GmfkNosDjNcVJMpmTXy | -1 | -1 | 0 | 0 | 0 | NULL | NULL | NULL | -62135769600 | NULL | 0 | NULL | NULL | NULL | 1 |  |

### 2. Output a list of Tasks with an Area Name

```sqlite
select TMTask.title task, TA.title area
from TMTask
         cross join TMArea TA on TMTask.area = TA.uuid
where area is not null
limit 3;
```

| task | area |
| :--- | :--- |
| Clear My Stuff from Old Lounge Room | At Home |
| Supermarket | Out & About |
| Publish More Photographs on Social Media | Making Stuff |

### 3. List Tasks Tagged with '@Home'

```sqlite
select distinct (TMTask.title) task_title, TMTag.title tag_title
from TMTask
         cross join TMTaskTag TTT on TTT.tasks = TMTask.uuid
         cross join TMTag on TTT.tags = TMTag.uuid
where TMTag.title like '@Home'
```
| task\_title | tag\_title |
| :--- | :--- |
| Download Govee Temperature Data | @Home |
| Cut Your Hair | @Home |