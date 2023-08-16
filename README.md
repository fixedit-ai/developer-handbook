# FixedIT Developer Handbook
This repository contains information about how we work with code, what tech stacks we use, how we format code and how we deploy artifacts.

## Nice to see you at our developer handbook!
Reading this probably means that you are already a colleague of ours (gratulations!), or that you are interested in becoming one (again, gratulations!). In this handbook we will explain what we do during the days, how we do it and why we do it. We will look at what programming languages, frameworks and tech stacks we use, how we deploy our code and how we decide what to build.

## Who are we?
We are an early-stage startup working with product development, research, and consultation in edge computer vision. We work exclusively with a niche edge camera platform (AXIS ACAP) for which knowledge is hard to find. We believe EdgeAI and edge-based computer vision will be everywhere in the future; but to enable this, we need to make it easier and faster to develop products for the edge platforms. That’s why we are developing tools, frameworks, and platforms that other companies can make use of to build applications for the cameras. We are sure this will change the world and create a massive market for us. Sounds hard? That’s what we love!

We are curious individuals who are always looking for ways to improve things. We learn new things every day regardless of if we are at the office, at the coffee machine or at a conference. We love mentoring people, but sometimes we don’t know the answer. Then you need to find the answer yourself. What is better than writing a small program or some scripts to try out different theories, be proven wrong, try again and finally understand exactly how the black box is implemented?

Our newfound knowledge goes into our own products and the applications we create, the applications we help clients create and the courses we author to teach them about best practices and ways of doing things.

We are not a typical consulting firm; in fact, we are more of a startup than a consulting firm. You will not find any of our developers at someone else’s office working for them. We work from our office as a team. Together we help our clients to success. Our clients expect us to be experts, so on average we spend roughly one third of our time working on projects for clients. The rest of the time we build tools that make us more efficient, we experiment with new technologies that will open new doors for us, and we consume our internal or external training materials to build new skills and know-how.

As a social group who loves to share knowledge and ideas, our main base is our office. We do, however, think you need freedom to do your job when and where you want to, and we strive for empowered individuals that can make decisions and take responsibility themselves. We are inspired by the “Results-Only” mindset (search for “Results-Only Work Environment”). We know that everyone is different; some people value work-life balance and predictable hours, some love working hard but don’t want to miss out on all the chances to travel and some people just want to work as much as possible to earn a big salary so they can buy that house they have been looking for. Having this freedom does also mean that you will be held accountable for delivering results, some tasks can only be done in the office and some collaborative tasks require you to work the same hours as everyone else at the office. At the end of the day, we are a team, and it’s all of ours responsibilities to make it work.

## Your superpowers:
Depending on which role you have you will focus on different tech stacks, but as a general rule you should aim for a skillset something like this:
```
[==========] C
[========  ] Python
[====      ] AWS
[=====     ] Deep Learning
```

Since we are never working as individual contributors at our clients', but instead always working as a team to solve their needs, you will have a greater say over what technologies you want to become an expert in. We encourage the T-shaped knowledge style, where you have a good foundational knowledge about everything we do, but is a valued domain expert in a niche area.

## What we do
The applications we create are analytics services or integration components that run inside network connected cameras. Our clients hire us when they have an idea they want to realize or when they need advice on how to make their product perform better. We are also building command line tools and cloud services that our clients can use in their development efforts.

Our applications often use computer vision to understand the content in the camera's view. It is not always deep learning and AI, sometimes we use simple rule-based analytics. An example of this would be to detect and decode QR tags. Our client used tags on objects and our cameras detecting the tags allowed the whole process to be automated.

Sometimes we do train deep learning models, but more often our clients train models for their specific use cases and they want our help to make the models run in the cameras. This involves researching different means to optimize models for edge deployment, such as quantization and pruning. These models might be used to detect people, cars, or things on an industrial assembly line.

When we learn something new, we like to share that knowledge with others. It might be an internal video in our demo-channel in Slack, it might be in a [LinkedIn post on our company page](https://www.linkedin.com/company/fixedit), a [video on our public YouTube](https://www.youtube.com/@fixeditconsulting/videos), or a full course in our e-learning portal.

## What tech stack do we use?
Our applications are normally written in C, sometimes with a bit of C++. This is a big part of what we do, so we need to feel at home with C. Sometimes we can agree that C is a bit annoying to work with, but we have grown to love it due to the many benefits it offers. Makefiles are an old technology, but their flexibility, portability, ease of writing and other benefits makes us frequent users of them.

We can also write our applications in Python, sometimes. If we do that we need to think extremely much on the efficiency of our code since we handle large amounts of image data on a very constrained device. This means that we often need to understand the internals of Python and have the knowledge to write Python extensions implemented in C or C++.

Python is however our primary choice when it comes to desktop CLIs, scripts and cloud services. We love the fast prototyping and the readable code it produces. For cloud services we use AWS. We prefer serverless architectures and are often using Lambda functions, IoT core and SageMaker. Our infrastructure as code (IaC) is mostly written as CloudFormation templates.

For deep learning we use TensorFlow, and we deploy our models with TensorFlow Lite. We prefer integrating with a modern library or SaaS service whenever it will reduce complexity and make our pipelines more robust. As an example, we use Deeplake and ActiveLoop for our data versioning needs and we run some of our experiments in the Kedro framework.

Working with Docker is something we do every day. We use docker to make builds reproducible, we use Docker images to deploy our tools and we even use a docker runtime in the network cameras!

All our code lives in git-repositories. Learning about the git-workflow will be some of the first tasks you get. The repositories are mostly located in GitHub, so if you are working with open-source projects in your spare time you will feel at home. Our automated builds and tests are done in GitHub Actions. With code review on most of the code we produce we make sure that we share knowledge within the teams by learning from reading others code and sharing tips and ideas with each other to improve the implementations.

Our C and C++ code is unit tested with GTest and our Python code with PyTest. We let clang-format decide our code style in the C/C++ applications and black/PEP8 decide our code style in Python files. In our C code, we are always on the look for memory leaks. We do this with the gcc-sanitizers and with valgrind. In production code we catch the errors and issues with [Sentry.io](https://sentry.io).

If you like project management and project management methodologies, you will enjoy spending time in our GitHub Issues tracker where we keep most of our tickets, our Confluence wiki where we share knowledge and information and Compass where each project has its information and you can see the dependencies of each project collected in a centralized place. Of course, we are Agile, dynamic, and reflective.

## Constant learning
We wake up with a smile every day knowing that today will be easier than yesterday since we have automated the boring tasks, built better tools, and improved our processes. To make the market grow, our goal is to reduce the cost for application development by 10x-100x compared to today. To reach this goal, we need to be constant learners and inventors.

You will spend a lot of time experimenting, looking for better ways to do something. Your ideas are valuable, and your mind is our primary asset. Therefore, you will visit conferences, read books that you find interesting and take every opportunity to learn. When you have learned you are eager to share your knowledge both internally and with our clients.

Found a boring task? Try to create a script to automate it. When the script is your daily sidekick, share it with the rest of the team. With our collaborative effort, the script will be transformed from a script to a CLI tool or a cloud service. Soon thereafter, the tool is mature enough to be added to our product catalog for our clients to use.

Well done, you are now a valuable expert in our team!
