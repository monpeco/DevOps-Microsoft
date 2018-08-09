#### DevOps Fundamentals   Module 1 Learning Objectives   Learning Objectives

Learning Objectives
After completing this module, you will be able to:

* Define DevOps and describe its value, history, and building blocks.
* Define a sustainable DevOps process.
* Identify appropriate compliance, security, and secrets management strategies.
* Identify ways to motivate key stakeholders along the DevOps journey.

---

#### DevOps Fundamentals   Why DevOps   What is DevOps

What Is DevOps?
> "DevOps is the union of people, process, and products to enable continuous delivery of value to our end users.

> You cannot buy DevOps and install it. DevOps is not just automation or infrastructure as code. DevOps is people following a process enabled by products to deliver value to end users."

> – Donovan Brown, Microsoft DevOps Program Manager

For more information, see Donovan Brown's blog post, “[What is DevOps?](http://www.donovanbrown.com/post/what-is-devops)”

---

#### DevOps Fundamentals   Why DevOps   Video: Core Values of DevOps

#### DevOps Fundamentals   Why DevOps   Is DevOps Real

In the video in the next unit, Sam Guckenheimer of Microsoft Visual Studio Team Services reflects on a question that he receives quite often: Is DevOps Real? He discusses:

* How DevOps is moving from a niche undertaking to a mainstream presence in the enterprise.
* The value that DevOps will bring to your organization.

Definition of terms: The phrase OODA loop mentioned in the video refers to the decision cycle observe, orient, decide, and act, developed by military strategists and United States Air Force Colonel John Boyd. Boyd applied the concept to the combat operations process, often at the strategic level, in military operations. It is now often applied to describe commercial operations and learning processes. This approach favors agility over raw power in dealing with human opponents in any endeavor.

---

#### DevOps Fundamentals   Why DevOps   Fast Delivery Cycles

One of the core values of DevOps is a shortened release cycle. John Allspaw, who was an employee at Flickr when he pioneered much of the DevOps thought process, and is now a leading thinker at Etsy, created the following visual to demonstrate the difference between a slow and fast delivery cadence:

The chart on the left shows the rate of change for a slow delivery cadence. If you look along the time vector, you see a long time between deliveries. Maybe this is three months. Maybe this is three weeks. Whatever the time frame is, if we wait a long time and then deliver into production, we will deploy a massive amount of change, including many lines of code, lots of features, and lots of things that can go wrong.

Oftentimes, organizations think that this is the right way to deliver. They think that when they stretch out their delivery times, they can perform a lot of regression testing and full testing, and ensure that everything is complete. It is considered safe when change does not occur too frequently.

This is not the case. As you lengthen the delivery cycles and increase the amount of churn, it becomes very, very difficult for to go back and fix anything bad that happened in the release. There is so much change that it becomes difficult to identify where the problems occurred, which results in a lot of dysfunction. When we spend more time in regression and testing, we also spend more time waiting and making sure the deployment is absolutely perfect.

If we move to a fast delivery cycle, in which we deploy very frequently, the changes are smaller at each individual release. The goal is to create faster and faster release cycles with less and less change, to ensure that what goes into production has limited impact and we can test very specifically. Consequently, we can get things into production quickly, get feedback rapidly, and learn from our customers at a much faster cadence.

---

#### DevOps Fundamentals   Sustainable DevOps   DevOps Lifecycle

Over the past 15 years, agile software development has gained immense popularity among software development teams. The agile process accelerates the software development process and forced a faster release cadence.

Traditional IT operations teams struggle with a fast release cadence because their practices make the release and operations processes reliable, but not agile. Additionally, the disconnect between development and operations increases the likelihood of mistakes and lead time when issues occur.

Within a DevOps culture, all team members who are involved in creating, delivering, and monitoring software, work together closely to ensure high-quality releases at increasing frequencies.

---

#### DevOps Fundamentals   Sustainable DevOps   DevOps Practices and Habits

The video in the next unit provides further information about the following seven practices and habits of a successful DevOps culture. These include:

**Seven key DevOps practices:**
* Configuration management
* Release management
* Continuous integration
* Continuous deployment
* Infrastructure as Code
* Test automation
* Application performance monitoring

**Seven DevOps habits:**
* Team autonomy and enterprise alignment
* Rigorous management of technical debt
* Focus on flow of customer value
* Hypothesis-driven development
* Evidence gathered in production
* Live-site culture
* Manage infrastructure as a flexible resource

Learn more
See also: [Sam Guckenheimer's talk on the 7 habits of successful DevOps.](http://devops.com/2015/12/03/11626/)

For a case study on the process of implementing DevOps practices at Microsoft, see [Our DevOps Journey](http://stories.visualstudio.com/devops/).

---

#### DevOps Fundamentals   Sustainable DevOps   Video: DevOps Practices and Habits

1. **Configuration management**, understanding
what we're deploying, how we're deploying it,
what is the configuration of what's going into production.

2. **Release management**, understanding and controlling
how we're building a release pipeline that we can trust.

3. **continuous integration**.
This idea that we should be testing our code, compiling it
at every single check in, every single version control commit.

4. **continuous deployment**.
Getting it out into a test environment at the very least,
and potentially all the way out to production
on a very rapid cadence, you'll see the word continuous
quite a bit when we're talking DevOps.

5. **Application performance monitoring**,
is another one that sometimes get short shift with DevOps and
here we're looking at in production monitoring and
watching our applications to get not just performance and
error information but usage information.
Insights into how we can then evolve our application
in the future.

6. **Test automation** is one of the most difficult of the core
DevOps practices, and that's automating your tests, not just
unit tests from the developer, but potentially deployment
tests, integration tests, user experiences tests or UI tests.

7. **infrastructure as code**.
It's making sure that when we deploy our code,
we've got a related infrastructure and
that infrastructure is also checked into version control.
So if there's anything that we need to change
in our environment,
we should be able to do that in an automated fashion.
In other words, we want to change the infrastructure,
we simply change configuration, which is checked in as code, and
that gets pushed up and actually does the changes through
something like Chef, or Puppet or
Desired State Configuration or any number of tools.

Now let's talk about the seven habits for
DevOps:

1. **team autonomy and enterprise alignment** is one of my favorites.
And Sam tells it brilliantly but I want to come back to it.
There's this balance between autonomy and
letting teams do what they want to do in alignment.
And we need to get the business alignment mapped with that
enterprise or that team autonomy.
2. **Rigorous management of technical debt**.
Technical debt can come up and bite you, and slow down your
ability to deliver code effectively and value.
And so we want to focus on that and manage it rigorously,
take time in our schedule to reduce that technical debt.
3. **focusing on the flow of customer value**.
This is a mind shift.
It's a strong one for development and operations.
These are developers need to think not, I got my code checked
into version control, now it's off to be tested and deployed.
The developer mindset along with the tester, and the IT mindset
needs to be we get credit when the customer gives us their
first piece of feedback from actually using that feature, and
that mindset is one that helps drive towards that DevOps
culture strongly.
4. **Evidence gathered in production** is another one that I
appreciate.
We're looking at production,
we're gonna figure out ways to gather insight from
what our customers are doing in production to inform new ways of
doing things

5. **hypothesis driven development**.
Sometimes, even in an agile world you don't know exactly
what you're going to build, instead you build a hypothesis,
you think I believe that if we do this one piece of code,
it's gonna result in this type of beneficial behaviour and
usage patterns for our end users.
And you try it with the smallest possible code that you can
put out there.
And then you find out, did it have the impact?
If it didn't don't invest further, pull it back.
There are lots of great examples of hypothesis driven
development in industry.
And it's one of those things that curiosity and
the scientific method that really drives the culture
at DevOps teams.
6. **Live site culture**.
This is a hard one, this is a hard one, and it's this goal,
this desire from the entire organization to say,
we need to get to production.
It's getting things to production,
it's pushing the production.
It's this mindset that says, there's no place like
production, there's no place like production.
And to do that we need to shift a lot of people's
attitude.
You don't get benefit from any code that's not in production.
If it's not in production,
you're not able to impact the lives of your end-users.
Get that focus, get that desire to go to live site.
7. **managing infrastructure as a flexible resource**.
And I love this one, I love that Sam put it in habits because of
all of those, it sound so technical, but it's not.
It's this idea that we need to treat our infrastructure
as you might hear it cats versus cattle.
We treat them as cattle not as pets.
We don't know their names.
We're willing to get rid of an infrastructure and
replace it with a brand new infrastructure if necessary.
We have a definition of our infrastructure as code.
So we should be very happy with throwing away our
old infrastructure and spinning up a new one in it's place.
And then just swapping over to that,
when we go live with our new version.
These attitudes, these behaviors
are things which can really drive that DevOps culture.
So those are some of the foundational aspects of DevOps.


---


#### DevOps Fundamentals   Sustainable DevOps   Build and Release Pipeline

DevOps believes in the automation of builds and deployments. Conceptually, a release pipeline is a process that dictates how you deliver software to your end users. In practice, a release pipeline is an implementation of that pattern. The pipeline begins with code in version control and ends with code deployed to production. In between, a lot can happen. Code is compiled, environments are configured, many types of tests are run, and finally, the code is considered done.

By done, we mean that the code is in production. For some organizations, a release pipeline strategy and structure needs to cover services, database, web, and mobile application components, and includes:

* Binary package consumption
* Continuous integration builds
* Package publishing
* Automated testing
* Continuous delivery

It is important to recognize that mobile deployments are different than web and server deployments. How you get your mobile app out for feedback is different than the process you use to obtain server application feedback.

### Binary package consumption
Package management allows you to reuse trusted components. An example is NuGet feeds. If you consume and reuse packages consistently, then you can keep your application fresh as those packages are updated. This is particularly important for security and compliance as the packages can be scanned, uniquely identified, and, in the event of new vulnerabilities, automatically updated.

Packages should not usually be included in version control because they may significantly increase the size of version control repositories. Better to have the packages stored in package management, such as internal NuGet feeds.

### Continuous integration builds
Continuous integration builds are builds that are triggered upon every check-in of code. They should be quick to complete and include automated tests (such as unit tests). They may or may not drop artifacts upon completion.

### Package publishing
Package publishing may tie into binary package consumption. You should use a version that matches the build and deployment number for full transparency (if a deployment breaks, you should be able to find the matching package quickly). The package should be hosted somewhere accessible by projects, such as NuGet feeds.

### Automated testing
Testing could include unit, integration, automated UI, web performance, and load tests. Tests should be able to run independently and as often as possible without breaking, such as in continuous integration builds or automated deployments.

### Continuous delivery
Continuous delivery means that deployments are triggered automatically after a build completes. The process should include picking up a compiled package of code, setting the target environment in the desired configuration state, and deploying automatically to environments. It may include approvals into QA or production environments.

---

#### DevOps Fundamentals   Sustainable DevOps   Backlog

### Backlog
One of the primary cultural shifts required for adopting DevOps practices is at the backlog level. The novel The Phoenix Project designates the following types of work:

* Business projects. Work that comes from business initiatives.

* Internal IT or engineering projects. Infrastructure/operations projects from a business project, or internal improvement projects. These items should be tracked in the same backlog.

Note: To continuously improve the system of work and adaptability, it is recommended that at least 20% of development and operations teams' time is allocated toward nonfunctional requirements such as security and infrastructure, among others, to make the process significantly better and more stable. If time is not allocated to this work, technical debt will accumulate and create more unplanned work.

* Unplanned/recovery work. Operational incidents tacked onto planned work, which might cause bottlenecks and confusion with handoffs. This work can also cause long lead times with high utilization, and it is often the result of not removing technical debt or improving practices.

Lead time is the cycle time from when a team starts writing code to its first successful deployment in the production environment. Lead time is considered a measurable metric that could be improved with DevOps practices.

---

#### DevOps Fundamentals   Sustainable DevOps   Version Control

Most organizations use some form of version control to manage their source code. However, not all organizations use version control effectively. Two version-control strategies that are sometimes overlooked are:

* Setting up an appropriate branching strategy.
* Enabling transparency by linking work items to code.

One approach is to have a single branch (such as the master or main branch) that gets built in an automated continuous integration build, then deploys to a development environment upon every commit or check-in that occurs to the branch. This way, it is easier to know which changes have been released into the development environment, and eventually, into production.

The changes automatically deployed into the development environment will then get promoted or copied to the test or staging environment, and then into production. The same compiled code will get deployed to production so that there is never a situation in which unchecked code gets promoted to production. Before deploying to any environment, it is important to ensure that the changes made align to the business strategy.

**Connecting work to code**
An easy way to verify that deployed code has value and is related to work on the backlog (rather than code that does not tie back to any work items) is by linking work items to code changes so that metadata is kept with the changes, and then with build and deployment. By connecting work in progress to code, you can validate feedback from users and the changes that were made in the code.

Some organizations use different branching strategies depending on the type of application being deployed, the degree of coupling, the organizational structure, and the deployment cadence. A general rule is to promote the simplest branching strategy possible to keep maintenance low and sustainability high. If you have long-lived branches that are infrequently merged, you accumulate a subtle form of technical debt.

If your organization does not currently use version control, it is important to start using it to version your code. A good way to start is to learn about Git repositories, and distributed vs. centralized version control.

In DevOps organizations, infrastructure is treated in the same way that software code is treated. Infrastructure as Code (IaC) is the management and provisioning of machines through code. This code is versioned in public or private repositories and shared across individuals and teams to enable more collaboration while keeping a track on changes using version control systems like Git.

---

#### DevOps Fundamentals   Sustainable DevOps   Testing in DevOps

### Continuous testing
Continuous testing is the execution of tests repeatedly against a code base and deployment environment. In practice, continuous testing is the most difficult part of a continuous delivery pipeline to keep up to date. Continuous testing provides quality gates throughout the pipeline and increases confidence in code long before production.

Automation is the key. Automated unit, integration, coded UI, and load tests are common in continuous testing.

Use an iterative and incremental approach. Depth of testing often progresses as an environment gets closer to production.

### Beta testing and progressive exposure
Beta testing and progressive exposure are important strategies in DevOps to receive critical feedback in production.

**Beta testing**. This is a form of external user acceptance testing where beta versions of an application are released to a limited audience, known as beta testers. Versions are released to groups of people for more testing, and sometimes made available to the public for more feedback.

**Progressive exposure**. This technique entails switching small numbers of users over to a new version of software for feedback, then progressively exposing more users to the features over time.

Both techniques involve a small group of users who test new versions of an application. Rapid feedback means that you will quickly know which features are relevant and that you will have the information you need to strategize and implement ways to improve the application. Any performance issues will only affect the small number of users testing the new version. These topics are covered in more depth in the section on application performance monitoring later in this course.

---

#### DevOps Fundamentals   Compliance and Security in DevOps   Compliance in DevOps

Compliance in DevOps
If you work at a financial institution, healthcare company, government agency, or in any heavily regulated industry, compliance is often the first concern when you are thinking about moving to DevOps. When dealing with compliance requirements associated with the U.S. Sarbanes-Oxley Act, the Health Insurance Portability and Accountability Act (HIPAA), or the Criminal Justice Information Services (CJIS), some organizations must be more careful than others might when they make process decisions.

A primary benefit of many deployment solutions now is that they offer secrets management, for example, by using services such as Microsoft [Azure KeyVault](https://docs.microsoft.com/en-us/azure/key-vault/). A secrets store gives you the ability to abstract passwords, connection string information, and any other variables from all users so that there is no direct access to sensitive data in databases or on machines. Administrators set up access for the deployment solution to the machine and abstract the passwords.

An automated release pipeline ensures consistent versions across assemblies, packages, builds, and deployments, using automated tests, infrastructure as code, and frequent releases. It also makes compliance more predictable and straightforward. With fast feedback loops, if noncompliance issues arise, corrections can be made more quickly and the changes can be tracked automatically.

Ken Cheney, formerly with the company Chef and now with Qumulo, Inc., offers this perspective:

"The key to making compliance an advantage is to specify compliance requirements as code, allowing that code to be tested just like any other piece of code in the software development pipeline. Previously manual verification tasks—often tracked through spreadsheets or other arduous methods—can now be proactively addressed as embedded tests in an automated workflow. Security risks are brought to the surface early for faster remediation, so out-of-date software is identified and updated quickly.”

Every organization treats compliance differently, so different tools might be needed depending on your organization's requirements. Whichever tools you adopt for compliance, DevOps practices offer predictability and simplification toward maintaining compliant practices.

For more information, see http://devops.com/2016/03/18/devops-help-hinder-compliance/.

---

#### DevOps Fundamentals   Compliance and Security in DevOps   Security in DevOps