<!-- markdownlint-disable MD001 MD013 MD025 MD036 -->
# Azure : Overview for AZ-400

### Version des outils

| Os / Tool | Version |
| :-------: | :-----: |
|   Azure   |  X.X.X  |

* * *

# Evolve your DevOps practices

DevOps is the union of people, process, and products to enable continuous delivery of value to your end users. Azure DevOps is a set of services that gives you the tools you need to do just that. With Azure DevOps, you can build, test, and deploy any application, either to the cloud or on premises. DevOps practices that enable transparency, cooperation, continuous delivery and continuous deployment become embedded in your software development lifecycle.

## Assess your existing software development process

### The team's release process

The first step to setting up a DevOps practice is to assess your current process. This means analyzing:

- Your existing artifacts, such as deployment packages and NuGet, as well as your container repositories.
- Your existing test management tools.
- Your existing work management tools.

### Assess process efficiency with value stream maps

Creating a value stream map, or VSM, helps you analyze your current release cycle process. The purpose of a VSM is to visually show where in the process a team creates value and where there's waste. The goal, of course, is to arrive at a process that delivers maximum value to the customer with minimum waste. A VSM can help you pinpoint those areas that either don't contribute any value or that actually reduce the value of the product.

## Get started with Azure DevOps

### What is DevOps?

DevOps is the union of people, process, and products to enable continuous delivery of value to our end users

- **Agile planning**.
    Together, we'll create a backlog of work that everyone on the team and in management can see. We'll prioritize the items so we know what we need to work on first. The backlog can include user stories, bugs, and any other information that helps us.

- **Continuous integration (CI)**.
    We'll automate how we build and test our code. We'll run that every time a team member commits changes to version control.

- **Continuous delivery (CD)**.
    CD is how we test, configure, and deploy from a build to a QA or production environment.
    Monitoring. We'll use telemetry to get information about an application's performance and usage patterns. We can use that information to improve as we iterate.

- **Deploy more frequently**
    In fact, some teams deploy up to dozens of times per day.
    Practices such as monitoring, continuous testing, database change management, and integrating security earlier in the software development process help elite performers deploy more frequently, and with greater predictability and security.

- **Reduce lead time from commit to deploy**
    Lead time is the time it takes for a feature to make it to the customer. By working in smaller batches, automating manual processes, and deploying more frequently, elite performers can achieve in hours or days what once took weeks or even months.

- **Reduce change failure rate**
    A new feature that fails in production or that causes other features to break can create a lost opportunity between you and your users. As high-performing teams mature, they reduce their change failure rate over time.

- **Recover from incidents more quickly**
    When incidents do occur, elite performers are able to recover more quickly. Acting on metrics helps elite performers recover more quickly while also deploying more frequently.

### What is Azure DevOps?

- **Azure Boards**
    These are agile tools that help us plan, track, and discuss our work, even with other teams.

- **Azure Pipelines**
    These will let us build, test, and deploy with CI/CD that works with any language, platform, and cloud.

- **Azure Test Plans**
    These are manual and exploratory testing tools.

- **Azure Repos**
    These provide unlimited, cloud-hosted private, and public Git repos.

- **Azure Artifacts**
    These let us create, host, and share packages.

### Measures

**Faster Outcomes**

- Deployment Frequency. Increasing the frequency of deployments is often a critical driver in DevOps teams.
- Deployment Speed. As well as increasing how often deployments happen, it's important to decrease the time that they take.
- Deployment Size. How many features, stories, and bugfixes are being deployed each time?
    Lead Time. How long does it take from starting on a work item, until it is deployed?

**Efficiency**

- Server to Admin Ratio. Are the projects reducing the number of administrators required for a given number of servers?
- Staff Member to Customers Ratio. Is it possible for fewer staff members to serve a given number of customers?
- Application Usage. How busy is the application?
- Application Performance. Is the application performance improving or dropping? (Based upon application metrics.)

**Quality and Security**

- Deployment Failure Rates. How often do deployments (and/or applications) fail?
- Application Failure Rates. How often do application failures occur, such as configuration failures, performance timeouts, and so on?
- Mean Time to Recover. How quickly can you recover from a failure?
- Bug Report Rates. You don't want customers finding bugs in your code. Is the amount they are finding increasing or decreasing?
- Test Pass Rates. How well is your automated testing working?
- Defect Escape Rate. What percentage of defects are being found in production?
- Availability. What percentage of time is the application truly available for customers?
- SLA Achievement. Are you meeting your service level agreements (SLAs)?
- Mean Time to Detection. If there is a failure, how long does it take for it to be detected?

**Culture**

- Employee Morale. Are employees happy with the transformation and where the organization is heading? Are they still willing to respond to further changes?
- Retention Rates. Is the organization losing staff?

**Common quality metrics**

- Failed Builds Percentage - Overall, what percentage of builds are failing?
- Failed Deployments Percentage - Overall, what percentage of deployments are failing?
- Ticket Volume - What is the overall volume of customer bug tickets?
- Bug Bounce Percentage - What percentage of customer or bug tickets are being reopened?
- Unplanned Work Percentage - What percentage of the overall work being performed is unplanned?

## Choose an Agile approach to software development

### What is Agile?

- Individuals and interactions over processes and tools
- Working software over comprehensive documentation
- Customer collaboration over contract negotiation
- Responding to change over following a plan

### What is Azure Boards?

There are four processes to choose from. We can use:

- **Capability Maturity Model Integration (CMMI)**. This is really for large organizations and it's pretty complicated so I didn't use it.
- **Scrum**. Scrum depends on a Scrum master who leads the Scrum team. The Scrum master makes sure everybody understands Scrum theory, practices, and rules. We don't have a Scrum master; that's someone who's usually received some training and certification so I didn't pick that one either.
- **Agile**. This seemed like the obvious choice since I'm always talking about Agile, but it has a few more things to consider than the simplest option.
- **Basic**. Basic is, well, basic. It's simple but gives us enough power to start doing effective planning right away, and that's why I picked it. In the Basic workflow, you move work from To Do to Doing to Done.

* * *

# Build applications with Azure DevOps

## Create a build pipeline with Azure Pipelines

### Introduction

[Gestionnaire de package Ubuntu 18,04-installer .NET Core](https://docs.microsoft.com/fr-fr/dotnet/core/install/linux-package-manager-ubuntu-1804)

### What is Azure Pipelines?

**What is continuous integration?**

Continuous integration (CI) is the process of automating the build and testing of code every time a team member commits changes to version control.

**Implement and manage build infrastructure**

- **Build agents** :
    As you know, a build agent is a piece of installable software that runs one build or deployment job at a time. To build your code or deploy your software you need at least one agent. As you add more code and people, you'll eventually need more than one. Let's examine build agents in a bit more depth.

- **The differences between implementing hosted and private agents**
    You can use either a Microsoft-hosted or a private agent. What are the differences?

    If your pipelines are in Azure Pipelines, then you've got a convenient option to build and deploy using a Microsoft-hosted agent. With Microsoft-hosted agents, maintenance and upgrades are taken care of for you. Each time you run a pipeline, you get a fresh virtual machine. The virtual machine is discarded after one use.

    For many teams this is the simplest way to build and deploy. You can try it first and see if it works for your build or deployment. If not, you can use a self-hosted agent.

    An agent that you set up and manage on your own to run build and deployment jobs is a self-hosted agent. You can use self-hosted agents in Azure Pipelines. Self-hosted agents give you more control and let you install any software you need for your builds and deployments.

    You can install the agent on Linux, macOS, or Windows machines. You can also install an agent on a Linux Docker container. After you've installed the agent on a machine, you can install any other software on that machine as required by your build or deployment jobs.

- **Agent pools**
    Instead of managing each agent individually, you can organize agents into agent pools. An agent pool defines the sharing boundary for all agents in that pool. In Azure Pipelines, agent pools are scoped to the Azure DevOps organization so you can share an agent pool across projects.

    A project agent pool provides access to an organization agent pool. When you create a build or release pipeline, you specify which pool it uses. Pools are scoped to your project so you can only use them across build and release pipelines within a project.

    To share an agent pool with multiple projects, in each of those projects, you create a project agent pool pointing to an organization agent pool. While multiple pools across projects can use the same organization agent pool, multiple pools within a project cannot use the same organization agent pool. Also, each project agent pool can use only one organization agent pool.

- **Agent queues**
    If you are a project team member, you create and manage agent build queues from the agent pools tab in project settings.

- **Service endpoints for integration with third-party systems**
    Service endpoints are a way for Azure DevOps to connect to external systems or services. They are a bundle of securely stored properties that includes but is not limited to:

    Service name
    Description
    Server URL
    Certificates or tokens
    Usernames and passwords

Extensions are then able to access the service endpoint to get the stored details to perform the necessary operations on that service.

- **Concurrent pipelines**
    You can run concurrent pipelines (also called parallel jobs) in Azure Pipelines. One parallel job in Azure Pipeline lets you run a single build or release job at any given time. This rule is true whether you run the job on Microsoft-hosted or self-hosted agents. Parallel jobs are purchased at the organization level, and they are shared by all projects in an organization.

- **Microsoft-hosted CI/CD**
    If you want to run your builds and releases on machines that Microsoft manages, use Microsoft-hosted parallel jobs. Your jobs run on the pool of hosted agents. Microsoft provides a free tier of service by default for every organization. Consult the Azure DevOps documentation to see the criteria.

    If you want Azure Pipelines to orchestrate your builds and releases, but use your own machines to run them, use self-hosted parallel jobs. You start by deploying agents on your machines. You can register any number of these self-hosted agents in your organization. Microsoft charges based on the number of jobs you want to run at a time, not the number of agents registered.

- **Plan a strategy for concurrent pipelines**

Here are some steps to take to plan for concurrent pipelines.
Determine how many parallel jobs you need

Begin by seeing if the free tier offered in your organization is enough for your teams. When you've reached the per-month limit for the free tier of Microsoft-hosted parallel jobs, you can start by buying one parallel job. As the number of queued builds and releases exceeds the number of parallel jobs you have, your build and release queues will grow longer. When you find the queue delays are too long, you can purchase additional parallel jobs as needed. A simple rule of thumb is to estimate that you'll need one parallel job for every four to five users in your organization.

  Think about your scenario

Here are some examples of where you might need multiple parallel jobs.

    If you have multiple teams, and if each of them requires a CI build, you'll likely need a parallel job for each team.
    If your CI build trigger applies to multiple branches, you'll likely need a parallel job for each active branch.
    If you develop multiple applications by using one organization or server, you'll likely need additional parallel jobs, one to deploy each application at the same time.

### Exercise - Get the sample application

### Plan your build tasks

### Exercise - Set up your Azure DevOps environment

### Exercise - Create the pipeline

### Exercise - Publish the result to the pipeline

### Exercise - Build multiple configurations by using templates

### Exercise - Clean up your Azure DevOps environment

### Summary

## Implement a code workflow in your build pipeline by using Git and GitHub

## Run quality tests in your build pipeline by using Azure Pipelines

## Scan code for vulnerabilities in Azure Pipelines

## Scan open source components for vulnerabilities and license ratings in Azure Pipelines

## Manage build dependencies with Azure Artifacts

## Host your own build agent in Azure Pipelines

* * *

# Deploy applications with Azure DevOps

* * *

# Automate your deployments with Azure DevOps

* * *

# Capture feedback and monitoring data to continuously improve your software

* * *

### Source

[AZ-400: Microsoft Azure DevOps Solutions](https://docs.microsoft.com/fr-fr/learn/certifications/exams/az-400?wt.mc_id=learningredirect_certs-web-wwl)
