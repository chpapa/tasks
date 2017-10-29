## Background:

Execrise to write a todo apps, 100% modeling Ben's workflow. To learn Haskell.

## Data Model

Annotations:
? have a
* have many

task:
* name
* description
* links
* project
* area
* ? time tag
* ? delegate
* due date
* follow up
* *checklist items

area:
* name
* * projects
* * tasks

project:
* name
* * tasks

repeat project:
* name
* * tasks
* ? repeat-by

repeat tasks:
* (inherit tasks, except follow up and due date)
* ? repeat-by
* ? follow up (day-in-future)
* ? due b (day-in-future)

time tag: name, time
delegate: name
checklist: name

## Command

### Tasks
* tasks add [project id/name, or area id/name] [name]
* tasks list
* tasks show [id or name]
* tasks done [id or name]
* tasks rm [id]
* tasks follow-up [id] [date]
* tasks due [id] [date]
* tasks delegate [id] [who]
* tasks time [id] [tag name / time]
* tasks add-link [id] [url]
* tasks desc [id] [desc] (or STDIN, or vim if no arguments)
* tasks checklist add [id] [description]
* tasks checklist rm [task-id] [checklist-id]

### Projects
* tasks project add [name] [area]
* tasks project rm [id or name]
* tasks project mv [id or name] [new-name]
* tasks project list [with-deactive]
* tasks project activate [id]
* tasks project deactivate [id]

### Areas
* tasks area add [name]
* tasks area rm [id or name]
* tasks area mv [id or name] [new-name]
* tasks area list

### Repeated tasks / projects

### Reporting
* tasks today: show all follow-up, dued tasks, sorted by time tag, list delegate at bottom
* tasks upcoming: show 7 days of today
* tasks anytime: show all tasks without follow-up date
* tasks inbox: show all tasks without project / area
* tasks log: show completed tasks for last 7 days

