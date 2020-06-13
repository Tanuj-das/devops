# devops

# 2 Lay down a plan for CI/CD. As there will be tests pertaining to each microservice, how do you plan to run them in tandem in the deployment pipeline. 

Microservices have of course several advantages regarding deployment and development, but they also come with their own challenges. Management of microservice repositories and pipelines becomes much harder as the number of applications grows.
While a company might have to deal with 1–5 pipelines in the case of monolith applications (assuming 1–5 projects), the number quickly jumps to 25 if each monolith is divided into 5 microservices.
These numbers are different per organization. It is perfectly normal for an application to have 10 microservices. So at a big organization that has 50 applications, the operator team is suddenly tasked with the management of 500+ pipelines.

Operators are locating the common parts of pipelines with applications
A shared pipeline segment registry is created that holds all those common parts
Pipelines in existing projects are re-engineered to depend on the common segments
New projects must first examine the library of common pipeline segments and choose what is already there
The final result is that a single pipeline is actually composed of two types of steps, those common to other pipelines and those that are specific to that project only.
This has lead to the development of several solutions which attempt to centralized common pipeline parts and re-use them in the form of “libraries” within software projects. The issue here is that this approach requires a very large time investment as well as a disciplined team that can communicate and cooperates on the following factors:
1 Detecting which pipeline segments are indeed common,
2 Keeping the library of common pipeline segments up-to-date,
3 Disallowing copy-pasting of pipelines,
4 Development of brand new pipelines when needed,
5 Initial setup and pipeline bootstrap for each new project created.

# 3 Prepare a deployment strategy that can be adapted for Staging, UAT and Production. Note that staging setup needs to be less in terms of operating cost. 

Ensure the App Works in a Staging Environment 
Before deploying an app to production, make sure it’s working properly beyond just on your machine. Take the time to test your app in a staging environment before progressing further to ensure it functions as intended. 

A staging environment(link is external) is “a complete copy of the production environment (hardware and software), independent and similar in terms of location and database load.” There are a variety of different types, each with a specific purpose. Consider whether a quality assurance (QA) or user acceptance testing [UAT] space best fits the needs of your development project.

In terms of caliber, testing environments range in functionality and capabilities. Development “sandbox” environments come highly recommended.

Automate the Tests You Run For QA
Once you set up the staging environment, run a full scope of automated functional tests(link is external) to verify that the application works correctly. Developers run these tests to assess whether or not applications function correctly in relation to users and to the rest of the system. 

Some examples of automated functional tests include:

Smoke tests: Preliminary testing to reveal simple failures severe enough to reject a prospective software release
Regression tests: Re-running functional and non-functional tests to ensure the software that’s been previously developed and tested still performs correctly after a change
End-to-end tests: Verifying that applications communicate correctly with other services.

# 5 Prepare a plan to add alerts and monitoring across all of the mentioned components.

Monitoring the app’s performance is the next step to ensuring you’ll be able to quickly isolate any problems that might come up.

Make sure to collect the following types of data:

Usage of CPU
Memory (RAM) Usage
Left Disk Space
Number of Requests Per Second
Response Times of Services. 
Collect, store, and analyze these metrics. Configure alerts to send an email to your team informing them of errors so they’re always aware of the system outages when they occur and can quickly communicate with users accordingly. 

he logs we had collected, stored and analyzed weren’t examined and verified from the business perspective. They worked fine from the development standpoint but lacked value on the business side, which is a common misunderstanding. Our client didn’t grasp the significance of what the documented changes in the system reflected. 

We learned a hard lesson when we experienced an outage just after the release. Nobody knew what happened to the system, or even worse, what its current status was. Since the logs only held meaning for the developers and the team couldn’t link them to real data, it took many long hours of debugging to fix. 

Logs should have equally demanding business requirements as the code itself. They should be easy to read from a technical and business perspective, even when the system deals with sensitive data.

