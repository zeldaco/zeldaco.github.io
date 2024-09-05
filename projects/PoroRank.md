---
layout: project
type: project
image: img/Branding_.png
title: "PoroRank"
date: 2024
published: true
labels:
  - AWS
  - Software Development
  - React
  - GitHub
  - Hackathon
summary: "PoroRank is a web application that allows you to view the top ranking esports teams in league of legends with the option to filter the rankings by team names."
---
PoroRank is a web application that I helped create as a team project for the Global Power Rankings Hackathon hosted by Riot. Our task was to build a working method for a League of Legends Global Power Ranking System using esports data provided by Riot Games and an Amazon Web Services (AWS). We decided early on that we wanted to build the application using the server-less model to reduce friction with infrastructure managment and to enable all the benefits of the cloud such as auto scaling with no additional work required. 

<img class="img-fluid" src="../img/Home Page.png">

Our main goals were to build a web application that implements the best standards to ensure scalable based applications. These goals led us to creating a common yet performant pattern of creating a restful api fronted by AWS API Gateway and integrated with multiple lambda functions per endpoint, allowing each endpoint to scale up and down as needed. 

This was my first time working on both UX Designs and software development for a project. I developed a style guide, branding, and working prototype and then worked to transfer it to react. I learned how to work in an agile environment to produce a working web application. Creating our very first anything in AWS was really exciting, let alone the fact that we did it all serverless! 

We learned quite a lot on AWS, Lambda types, API Gateway, API Gateway fronted by Lambda, DynamoDb single-table design, AWS boto3 client vs resource, and rating system history and their differences (elo vs truskill vs glicko). Our DynamoDb single table design is something we were also extremely proud of. We went through countless different iterations of our single-table design before we landed on the one use today and we are quite proud with the current product.

<iframe class="img-fluid" src="https://www.youtube.com/embed/5zIIq0fF3gU?si=kCi2VLXjKErQLlFW" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

There were quite a few features we wanted to add that were in our wireframes but ran out of time unfortunately such as: Tournament filtering, Match processing lambda, Rank history, team-specific view with match history, player lists, current events list, etc.. We decided we are going to continue working on PoroRank albeit a bit slower implementing the missing features we wanted to add and creating a truly polished and delightful experience.

You can read more about the process of designing PoroRank [here](https://devpost.com/software/pororank)
