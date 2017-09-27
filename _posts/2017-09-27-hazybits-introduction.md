---
layout: post
title: "Introduction"
date: "2017-09-27 21:45:22 +0200"
tags:
 - architecture
---

> "I find your lack of faith disturbing."  
> Darth Vader - A New Hope

I'd like to introduce **HazyBits** company - a venture I founded along with [my fellow developers](/pages/about)
to work on a problem that always interested us - how to make image processing right from application
architecture perspective.

Over and over, we see the same pattern - if you want to do something with images - from simple
[scaling](https://en.wikipedia.org/wiki/Image_scaling) (which is not so simple after all) to more
advanced operations like [thresholding](https://en.wikipedia.org/wiki/Thresholding_(image_processing)),
[OCR](https://en.wikipedia.org/wiki/Optical_character_recognition) and
other computer vision tasks - most likely you will take 3rd party library that provides such
a service, throw it into your app, google some snippet to make it work and, fingers-crossed,
forget about it for a while. Until it breaks. Repeat the cycle.

That is a feasible approach since application developers usually need to bother about many other
things while image processing is a small piece of a big puzzle. So what is the problem here?

We see many:

 - Application developers are usually **not** imaging experts. It takes some knowledge and painful
 experience to know differences between image formats and compressions, learn how to properly prepare
 an image for OCR processing, etc. Unfortunately, developers just throw what they have at imaging library and complain about the results,
 blaming innocent OCR engine, ignorant to the fact that the problem was with input image, not the algorithm
 - ‎**Performance** is another major problem. Let's face it - image processing is slow. It just is.
 OCR can easily take *seconds*, if not *minutes* for extreme cases, consuming a lot of memory
 and CPU resources. The most awful scenarios we've seen is when heavy image processing is performed
 on a web server, in context of a web request. No matter how powerful your server is, a handful of
 parallel requests that do OCR processing will kill your application. Typical solution is to scale
 web servers horizontally under load (it is easy with modern cloud techniques), but it may cost
 you a fortune.
 - **Difficulty** of integration with imaging libraries. Many decent libraries you may want to use
 can be difficult to integrate into your application. Either programming languages are not super
 convenient to play together or platforms are incompatible (you target Mac while the library is
 Windows-based). These problems can be addressed but there is a cost associated with that.
 And remember, image processing is not a goal, it is just a small component for your application.

The problems above lead as to think that there should be a clear architectural solution. We think
that modern advancement in [microservices](https://martinfowler.com/articles/microservices.html)
architectures, [Web APIs](https://en.wikipedia.org/wiki/Web_API) and
[FaaS](https://martinfowler.com/articles/serverless.html) stacks finally make it
possible to design and execute efficient, robust, scalable and most important relatively
**cheap** solution.

HazyBits started as a prototype with a single goal - prove that such a solution exists and we can
build a service to expose our knowledge and ideas to the fellow application developers. We've built
a running system and verified that it enables aggressive scaling we are aiming for. Now it is time
to do things right for the prime time.

Not sure if this term was used already, but it clearly describes my intention - HazyBits is all
about **Open Source Architecture**. It is like one step further than Open Source - we expose not only
all the sources behind the platform, we also make public all architectural documentation and grow
the platform before your eyes.

That is a tough move and I'm sure we will make a lot of mistakes along the way. The more we do,
the better the final result will be. At least that is my belief :)

At the beginning, we are going to concentrate on small things - trivial image operations like
format conversions, scaling, thresholding, and rotation. It doesn't look impressive, but doing that,
we have a chance to invest into infrastructure and test the whole framework. Once we are confident enough
that the project is on the right track, we'll turn towards more advanced blocks like OCR and barcode
recognition. Other computer vision problems will follow.

An important piece that should not be forgotten is an **architecture-first development**. We believe that
clear intention of the architectural vision is crucial for such a project where we rely on
the community to jump in as quickly as possible. Therefore, this blog and documentation area of
the site will be the main arenas, along with our source code repository. We also have a weekly
newsletter and I encourage you to use these tools to be on top of everything that happens in the
project. I'll post some links to additional services and resources we use to communicate within
the team in separate blog post.

See you,  
Dmitry
