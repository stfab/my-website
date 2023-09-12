---
layout: post
title: "How I Became Azure Data Engineer Associate in Twenty Days"
description: "Do you want to become an Azure Data Engineer Associate? Here I describe how I did it and go into detail about the exam content."
author: "Fabian Stadler"
categories: [tech,journal]
tags: [data-engineering]
image: assets/img/coffeeandbooks.png
permalink: 2022/12/how-i-became-microsoft-certified-azure.html
---

At the beginning of December 2022, I had the spontaneous idea to complete a Microsoft certification for the Azure Platform. I worked for about a year as a data engineer on a project for an international pharmaceutical company. The technology stack here included the Azure Platform, specifically Data Factory and Data Lake Storage, but also Azure Databricks and processing data using Python.
I had considered applying for a certificate at the beginning of the year, but due to other urgencies, I did not find the motivation to do it in the end. What a misjudgment. Based on my experience, my choice fell on the DP-203 exam, i.e. the exam to become a certified Azure Data Engineer Associate.
DP-203 roughly covers the technologies: Azure Storage, Azure Data Factory, Azure Synapse Analytics, Azure Stream Analytics, Azure Event Hubs, Azure Databricks. As a data engineer, I had hands-on experience as far as half of the services are concerned.

## Preparation Time

Since I had not yet completed an Azure certification, my first step was to look for guides on how to prepare for the exam. Here I found a wide variety of information, ranging from a required learning time of over 2 months to 2 weeks. These values depend on different prior knowledge. Microsoft advises several years of practical experience. In general, I think it depends on the available time of the examinee.

I booked my exam for the next date in about twenty days. This date was optimal because I felt well prepared about a day or two before the exam. To someone with little to no experience, I would recommend about 1-2 months. Especially if you are not familiar with the platform at all and have little time. It may even be a good idea to take the fundamentals certifications.

## Exam Contents

According to the [study guide](https://learn.microsoft.com/en-us/certifications/exams/dp-203), the following topics are tested:

  * Design and implement data storage (40-45%)
  * Design and develop data processing (25-30%)
  * Design and implement data security (10-15%)
  * Monitor and optimize data storage and data processing (10-15%)

The guide goes into further detail on individual points, but I did not pay any further attention to them. There's different types of questions that Microsoft uses. Commonly, you get multiple choice questions with one correct answer.

## E-Learning Courses

Initially, I divided my exam preparation into three parts: Going through online courses, studying the Microsoft Learn modules, and preparing with practice exams.

I spent the first few days watching the [A Cloud Guru course](https://learn.acloud.guru/course/microsoft-certified-azure-data-engineer-associate-dp203/overview) on DP-203 by Brian Roehm and Landon Fowler. In addition, I went through [Alan Rodrigues’ course on Udemy](https://www.udemy.com/course/data-engineering-on-microsoft-azure/). Mostly, I skipped using the labs because of my prior knowledge and watched the courses at 1.5x speed to get a quick overview of the topics. For some people, the labs may provide useful hands-on experience.

In my first practice exams, I achieved a value of about 70-80%, which I could quickly increase to 90%. However, this did not satisfy me.

## Using Microsoft Learn

I spent the next few days going through the Microsoft Learn modules that can be found on the exam site. Again, I avoided the labs and skimmed many topics. For a detailed run through you need 40-50h, which I didn’t have.

While I was reading the modules, I tried the official practice exam, which you can [buy separately](https://eu1.mindhub.com/dp-203-data-engineering-on-microsoft-azure-microsoft-official-practice-test/p/MU-DP-203). Here I only scored about 60% on the first attempt. On the second attempt, it was a little over 70%. Too low for me. As a goal, I set myself 95% to prevent the case of unfamiliar and special questions.

About four days before the exam, I finished the last modules of the Microsoft Learn learning path. So I had a few days to prepare with the tests I had. As I kept taking the tests, I made a note of the topics I was having trouble with. These included the different authentication methods for Azure Storage and encryption via Always Encrypted or TDE. To fill my gaps, I read through the documentation until I understood them.

## Final Preparation

After ten attempts on the official practice test, I increased my average score to over 90%. In order to have seen all 200 questions at least once, I used the study mode to answer all the questions in one test. This cost me two hours, but showed me I had prepared well with 89% correct answers (ironically, my later score).

On the last day of my preparation, I got several 100% results in the tests I had now. I learned nothing new. After having a consistent score of about 97% on all of my tests and solving them in about 5-10 minutes, I knew it was time to stop and relax some more the evening before the exam.

## The Exam

I was slightly nervous, but had a good feeling because of the preparation. In the end, I found the 100-minute exam relatively difficult and on the same level as the official practice test.

There was a case study which took me about twenty minutes to complete. For the normal questions, which made up about 80% of my exam, I often had second thoughts about my answer. I marked 14 questions for review. Last, I had a section with several questions on the same topic, in this case windows when streaming. This was probably the easiest part of the exam. I took the last thirty minutes to review the questions I was unsure about.

Even though I felt I had only just passed, I had passed with 89%, far from the required 70%. I was a bit stunned, but had perhaps also thought too much about the questions. Microsoft does not try to trick you in general.

## Conclusion

What remains after passing the exam? First, the realization that I should have taken the exam half a year earlier. Much of what I already knew I could have learned during the exam instead of in practice. Also, some best practices are best learned before doing something, even though I usually consult the documentation first. It’s something else to learn on your own than when you’re preparing for an exam. Further, the knowledge of the other services, which I did not know yet, sharpens the view on alternative approaches.

Taking the exam was worth it for me. Even if some certificates are now ridiculed due to certificate inflation, I could accumulate new knowledge for myself and see it as a confirmation of the quality of my work over the past year. Someone with this certificate and demonstrable practical experience is definitely more trustworthy than someone without a certificate. Just having it without relevant experience seems less beneficial to me. Unless you’re doing it to learn the theory as part of learning the ropes on a project. Anyway, for the new year I have more motivation to learn new things. I still want to take one of the Microsoft Azure specialization exams or another associate. We’ll see what comes after that.
