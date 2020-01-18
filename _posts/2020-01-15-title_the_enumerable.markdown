---
layout: post
title:      "MY FIRST CLI PROJECT"
date:       2020-01-15 18:25:12 -0500
permalink:  title_the_enumerable
---


I can’t believe I am here to write a blog about my 1st project. Time went so fast and it was full of ups and downs. Since this is my 1st project I am trying to keep it very simple and short. 

In this project, my goal is to list the name of “Best desserts of 2019!” and a short note about these desserts. So users can first pick if they want to see the list of desserts. They have yes/no options in the beginning. If they pick no, it will give them a goodbye message and exit. If they pick yes, it will list all the desserts. Then from that list, they can pick any number to see a short note about particular dessert. Besides that, the few things I work on are: if users put wrong number or random text it will give them error message; If they want to go back and see list again, they can do it by typing list or if they are done they can simply type exit, which will give them a goodbye message and exit. I used while loop method and if/else statement for this section to execute. 

In order to collect all data, I scraped those data from a webpage https://www.purewow.com/food/best-desserts-2019
 In scraping part, I created an object “dessert” and gave attributes “name” and “description”, where I stored all data. Then pulled those data to “cli ruby file” and implemented it inside the method. I used “.each” method to iterate and collect those data separately, because those data were inside nested array. 

Final step was connecting all of ruby files to bin directory to see actual behavior, which was my CLI. Upon a call “./bin/filename(In this case it will be bestdessertsof2019_cli)”, my  program starts running and user can interact. Sounds very simple right? In reality, it was not simple at all. There were struggles, excitements, frustrations, pairing with cohort and so on. This whole journey of building project will be memorable. The most frustrating part was in the beginning when I had no idea how to start? I kept going back and forth on lessons, walkthrough videos and Google. I felt like I needed 48 hours a day while doing this project. However, it was fun, and I am really looking forward for next project.

The most import lessons I learned from this project were: read the instructions very carefully before you jump into the actual work; stay focused and concentrated on task; Don’t afraid to ask questions; learn from mistakes and last but not the least, do more pairing with your cohort. My cohort rocks. Without them I would be lost. Those tip really helps. 

Thanks for reading. See you in next blog. 



