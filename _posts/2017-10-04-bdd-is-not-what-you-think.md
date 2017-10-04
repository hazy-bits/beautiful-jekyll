---
layout: post
title: BDD is not what you think
subtitle: Actually it is, but there is more
date: "2017-10-04 14:29:12 +0300"
tags:
 - process
 - build
---

> "Don't call me a mindless philosopher, you overweight glob of grease."  
> C-3PO - A New Hope

![](/img/2017-10-04/todo.jpg)

**BDD** is usually stands for *[Behavior Driven Development](https://en.wikipedia.org/wiki/Behavior-driven_development)*.
A lot has been said about this technique, but this post is a different thing altogether.
Incidentally, it has the same acronym - **Build Driven Development**.

The automated build is the **first** thing you need to do after you started a project. Literally, it
should have **-1** index on your list of things to setup. It doesn't matter if you are working on a
side project or you are a team of many - automated build is the foundation you want to have.

DevOps trend is quite popular nowadays, but Build Driven Development is about *technical
hygiene* - the most trivial things to keep your project healthy. You can start from here to
go to a gym and become a cross-fit champion, but please clean your hands first :)

## Builds are simple
The build is the simplest activity you can perform over a bunch of sources. Still, it does a
crucial job - it *proves* that your code is not gibberish. It may sound trivial, but it is a huge
step forward. If your sources are syntactically correct, *there is a chance* that they work.  
They do not have to and often they do not, but having a chance is always a good thing :)

Defining a build can be as simple as

```
msbuild project.sln
```

if you are working on Microsoft stack or something along these lines for your target platform.
Usually, in the most simple form, it is a one-line script that you can run from the console. If you
can run this script on your dev environment, you can run it automatically on a build server.

## Builds serve as a foundation
Once you have an automated build, it is easier to add more ingredients to the soup:

- unit tests
- code coverage
- static analysis
- versioning
- installers
- documentation
- packaging
- deployment
- etc.

These are steps of continuous delivery pipeline that you eventually want to add into your process.
But it all starts with the builds and simple automation infrastructure you create around them.

The minimal setup I would recommend is plain build paired with some kind of notification mechanism -
it could be emails, Slack notifications, whatever - the point is that you and your team need to
know **immediately** when the build is broken. The green build should be the top priority.

Start simple, build on top of it.

## Builds boost your performance
Automated builds actually help the team to be more productive. No time is wasted on getting
*not even compilable* sources and finding, after 10 minutes of investigation that somebody
checked in broken code. Therefore, automated procedure reduce frustration and actually have a
positive effect on relationships in the team :)

Builds also simplify communication - instead of ad-hoc procedures, you can just pass the
following piece of advice to SQA team *"feature X is available in build N"* or *"bug Y is fixed in
build M"*  to kick off the testing process (or even better, this information could be added
automatically into notifications). This implies that your builds should be accessible to
everyone in the team and have a unique version number associated with them. **Everyone** should be
able to grab a build and get it running in a matter of minutes.

## Builds are free (well, almost)
It is much easier to setup build infrastructure these days - there are plenty cloud services
available and most of them provide some free build time. Advanced features may have
associated price, but usually, you can get going for free, at least for a start. If you keep your
sources (as you should) in source control system, you can setup an advanced build infrastructure
with a few mouse clicks.

It is amazing, actually, what you can achieve **for free** if you select the right tools.
Here is a small list of tools we use in HazyBits (I certainly missed some):

 - Source Control ([GitHub](https://github.com), [BitBucket](https://bitbucket.org))
 - Builds ([VSTS](https://www.visualstudio.com/team-services/), [BitBucket](https://bitbucket.org), [Travis](https://travis-ci.org/))
 - Team Communication Hub ([Slack](https://slack.com/))
 - Project Management ([VSTS](https://www.visualstudio.com/team-services/), [Trello](https://trello.com/))
 - Log management ([Loggly](https://www.loggly.com/))
 - Metrics ([DataDog](https://www.datadoghq.com/))
 - Package Management ([NuGet](https://www.nuget.org/), [npm](https://www.npmjs.com/))
 - Password Management ([LastPass](https://www.lastpass.com/))
 - Web Site Hosting ([GitHub Pages](https://pages.github.com/), [Jekyll](https://jekyllrb.com/))
 - Wiki / Documents ([MkDocs](http://www.mkdocs.org), [GitHub Wiki engine]((https://github.com)), [Google Docs](https://www.google.com/docs/about))

## There is no excuse not to build
Having said all that, you should rush to create your build infrastructure, if you don't have one
already. Google around - there are many amazing services available that you can utilize to make
a big step towards DevOps nirvana.

It is far easier than you think.

See you, folks,
Dmitry
