## Background:

Execrise to write a todo apps, 100% modeling Ben's workflow. To learn Haskell.

## Data Model

task:
* name
* description
* links
* project
* area
* time tag
* delegate
* due date
* follow up
* have many checklist items

area:
* name
* have many projects
* have many tasks

project:
* name
* have many tasks

repeat project:
* name
* have many tasks
* repeated by:

repeat tasks:
* (inherit tasks, except follow up and due date)
* repeated by:
* follow up by: +N days, next N weekday
* due by: +N days, next N weekeday
