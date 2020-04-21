# Week 6 - Project Week

Week 6 is our first group project week and we get to work in teams.

We are team Sataa and on Monday I was elected team leader.

I really enjoyed my leadership roll, it was great fun to be in charge of a team of developers.

We used the following methodolgies:

- Extreme Programming principles
- SCRUM meetings each day
- Daily Retrsopective
- Kanban board on trello
- Group diagramming on a Miro board
- Slack for communication
- Zoom for video conferencing
- We worked pair programming, solo working, and working in mobs, depending on the requirements of the situation.

On the first day, by lunch we finished planning and had all agreed on our MVP, domain model, and work allocation, so we set off to work.

On Tuesday we were ready to merge our different code, and by lunch we were ready to start building the front end for our MVP.

Now I am looking into using Travcis-CI on our project. As we are using Javascript, this is slightly different than before.

Here are my instrunctions:

In the travis.yml file enter:

```yml
language: node_js
node_js:
  - 12.16
```
Can use the above ^ However using ```lts/*``` is reccomened, however I am not sure whether that should be entered with the ```/*``` or exactly how:

```yml
language: node_js
node_js:
  - lts/*

services:
  - postgresql

before_script:
  - psql - U postgres -c 'CREATE DATABASE example_name_test;'
  - psql - U postgres -d example_name_test -f db/migrations/01_create_example_table.sql
  - psql - U postgres -d example_name_test -f db/migrations/01_create_other_table.sql
  - psql - U postgres -c 'CREATE DATABASE example_name;'

script:
  - bundle exec rspec
```

This is a rough example of how it works using postgres^.