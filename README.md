# Eden Anderson
## Streaming Data 44671 / Module 5 Assignment

# streaming-05-smart-smoker
Streaming Data 44671 Module 5 / Creating a Producer

# The Problem / Challenge To Solve

## Using a Barbeque Smoker
When running a barbeque smoker, we monitor the temperatures of the smoker and the food to ensure everything turns out tasty. Over long cooks, the following events can happen:

1. The smoker temperature can suddenly decline.
1. The food temperature doesn't change. At some point, the food will hit a temperature where moisture evaporates. It will stay close to this temperature for an extended period of time while the moisture evaporates (much like humans sweat to regulate temperature). We say the temperature has stalled.
 
## Sensors
We have temperature sensors track temperatures and record them to generate a history of both (a) the smoker and (b) the food over time. These readings are an example of time-series data, and are considered streaming data or data in motion.

## Streaming Data
Our thermometer records three temperatures every thirty seconds (two readings every minute). The three temperatures are:

1. the temperature of the smoker itself.
1. the temperature of the first of two foods, Food A.
1. the temperature for the second of two foods, Food B.

## Assignment Tasks
1. Please read about the Smart Smoker - DONE
1. Access the smoker data file here Download smoker data file here. - DONE

# We want to stream information from a smart smoker. 
Read one value every half minute. (sleep_secs = 30)

smoker-temps.csv has 4 columns:

[0] Time = Date-time stamp for the sensor reading

[1] Channel1 = Smoker Temp --> send to message queue "01-smoker"

[2] Channel2 = Food A Temp --> send to message queue "02-food-A"

[3] Channel3 = Food B Temp --> send to message queue "03-food-B"

# Requirements
* RabbitMQ server running - Verified working (see screenshot)
* pika installed in your active environment - DONE

RabbitMQ Admin
* See http://localhost:15672/Links to an external site.

# Prerequisites
* RabbitMQ server
* Localhost established
* Installation of pika
* Working conda environment
* Access to .csv data file 
* Prior python producer process from Module 4

# General Design Questions

1. How many producers processes do you need to read the temperatures: We need one producer (just one .py file) to read the temperatures
1. How many queues do we use: The one producer process will create 3 queues.
1. How many listening callback functions do we need (Hint: one per queue): We need one listening callback function for each of the 3 queues.

If that is all you need to get started, you can begin the project now. Apply everything you've learned previously. 

# Task 1. Create a Place to Work
1. In GitHub, create a new repo for your project - name it streaming-05-smart-smoker - DONE
1. Add a README.md during the creation process. (If not, you can always add it later.) - DONE
1. Clone your repo down to your machine. - DONE
1. In VS Code, add a .gitignore (use one from an earlier module), start working on the README.md. Create it if you didn't earlier. - DONE
1. Add the csv data file to your repo. - DONE
1. Create a file for your bbq producer. - DONE

# Task 2. Design and Implement Your Producer
1. Implement your bbq producer. More detailed help provided in links below. - DONE
1. Use the logic, approach, and structure from Module 4, version 2 and version 3. - DONE
1. These provide a current and solid foundation for streaming analytics - modifying them to serve your purpose IS part of the assignment.
1. Do not start from scratch - do not search for code - do not use a notebook.
1. Use comments in the code and repo to explain your work. 
1. Use docstring comments and add your name and date to your README and your code files. 
1. Explain your project in the README. Include prerequisites and how to run your code. - DONE
1. Document your project works - display screenshots of your console and maybe the RabbitMQ console. 
1. If you only have a producer, you won't have a consumer showing messages yet, so you'll need to be creative. We'll build the consumers next.

# Required Approach
* Use your Module 4 projects (Version 2 and Version 3) as examples. - DONE
* Remember: No prior coding experience is required to take this course. Rely heavily on the working examples from earlier modules. 
* The more similar your code looks to the examples - the more credit earned. - DONE
* Vastly different approaches can be expected to earn less credit not more.
* This project should clearly build on skills and code we've already mastered. If not, let me know and more help will be provided. 
* The primary difference should be going from 1 to 3 queue_names and from 1 to 3 callbacks. - DONE
* Part of the challenge is to implement analytics using the tools and approach provided (don't significantly refactor the codebase during your first week of work!) 
* AFTER earning credit for the assignment, THEN create and share additional custom projects. 
 

# Why? Professional Practice
* At work, you'll be expected to contribute meaningfully and solve a variety of issues on your own.
* You'll also be part of a team. We all need to balance working on our own, and maintaining productivity by asking for help to get past obstacles.
* The goal is to be ready to be onboarded effectively into an existing team, with pre-established ways of doing things.
* At this point in your career, don't get too attached to any preferences.
* Many things will be set by your team lead.
* On a team, you'll likely autoformat your code on commit (have you read about Black?) and use various automatic static analysis tools and linters like Prospector and flake8. Commits may need to pass unit tests before you can push. 
* Focus on being a great team player, able to join a team with little disruption, follow your team's conventions, and begin contributing productively. 
 

# More Guidance
* To be guided through the producer design, read Module 5.1: Guided Producer Design.
* For a bit more guidance on the coding implementation, read Module 5.2: Guided Producer Implementation
* Use the discussion forum when you get stuck.
* Try to help without giving away code. 

# Anaconda screenshot
This shows the 3 queue messages being sent simultaneously through code

![Window Example](A5_Anaconda.png)

# RabbitMQ screenshot
This shows that the messages are being sent every 30 seconds.  I liked this visual.

![Window Example](A5_RabbitMQ.png)