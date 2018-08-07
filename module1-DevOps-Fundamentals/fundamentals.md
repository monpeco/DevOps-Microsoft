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
