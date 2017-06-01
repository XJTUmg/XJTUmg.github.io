---
layout: post
title: GSoC2017 Bonding Period 
date: 2017-06-01
tag: pgRouting 
---

### Conclusion
   In this period, I have learnt a lot about pgRouting and git.  
   I made my first template function using ```create.sh``` file and fixed it to make all the tests passed.  
   And I already set up my wiki page.  
   About the teamwork, there are three of us working in this GSoC period, so, we first make a PR to vicky's fork to verify that we don't have any conflicts.  
   I didn't work much last month. (I had three exams last month, and the other three are still pending...)
   Details of what I have done last month, please see below.

### Fix the installation of PostGIS on AppVoyer

   - [x] AppVeyor: changed ```PG_VERSION``` to ```2.3.2``` in the build because ```2.3.1``` is no longer availabe.
Here is the contents of the site where it gets the binaires http://winnie.postgis.net/download/windows/pg94/buildbot/
   - [x] updated to latest changes on develop

### Get familiar with C++
   
   Watch videos about C++:

   - [x] [https://www.youtube.com/watch?v=1OEu9C51K2A](https://www.youtube.com/watch?v=1OEu9C51K2A)
   - [x] [https://www.youtube.com/watch?v=YnWhqhNdYyk](https://www.youtube.com/watch?v=YnWhqhNdYyk)
   - [x] [https://www.youtube.com/watch?v=u5senBJUkPc](https://www.youtube.com/watch?v=u5senBJUkPc)

### Practice teamwork
   
   - [x] use ```create.sh``` to create my dijkstra
   - [x] make a PR to Vicky's fork 
   - [x] fix appvoyer

### Set up my wiki page

   A wiki page contains

   - [x] A brief introduction about your project
   - [x] Plan for the week
   - [x] A detailed list of tasks you need to accomplish during the week
   - [x] Links to your weekly reports

   Table of contents

   **Links, don't open a page, must be in the same page**.

   - [x] Have a look at 
     - https://github.com/pgRouting/pgrouting/wiki/GSoC-2016-Contraction#table-of-contents
     - https://github.com/pgRouting/pgrouting/wiki/GSoC-2016-Flow#table-of-contents

   Weekly reports

   **Send a report to the mailing list and copy it to wiki page weekly**.
   **Do mention about my meetings with the mentors in the weekly reports**.

   - [x] Have a section which has the links to all the weekly report. For example, 
     - https://github.com/pgRouting/pgrouting/wiki/GSoC-2016-Contraction#status-reports
     - https://github.com/pgRouting/pgrouting/wiki/GSoC-2016-Flow#table-of-contents

### GSoC practice linting

   Learning the basics of linting code

   depart from develop: (updated the fork)
   ```
   git checkout develop
   git checkout -b lint/trsp
   git push
   ```
   do the linting
   ```
   git push
   ```
   and make a pull request to main repo's develop
   lint ```src/trsp/src/GraphDefinition.h```
   - [x] update my fork
   - [x] depart from develop
   - [x] linting
   - [x] make a pull request
