---
layout: post
title: "Buildbot as open-source CI/CD alternative"
description: "Buildbot is a powerful, open-source CI/CD system which offers a flexible configuration that comprises mostly Python code."
author: "Fabian Stadler"
categories: tech
tags: [tools]
image: assets/img/screw.jpg
image_description: "Screws, shims and nuts on a brown, marbled table."
image_title: "Image source: <a href='https://pixabay.com/de/photos/schraube-gewinde-technik-1924174/'>PIRO4D auf Pixabay</a>"
permalink: 2023/11/ci-ci-with-buildbot.html
lang: en
---

CI/CD software has now become a standard for development departments in a wide range of industries. As a result, there are now services from a wide range of providers, all of which more or less have their raison d'être. Examples include Microsoft with Azure Devops Pipelines, Gitlab with Gitlab CI, Atlassian with Atlassian Bamboo or Github with Github Actions.

However, you don't always want to rely on a commercial platform that makes you dependent on other technologies from the same provider. That's why I'd like to talk about an open-source alternative called [Buildbot](https://www.buildbot.net/), which I've had the pleasure of working with in recent months and which most people may not be familiar with.

## Master server as central interface

![A diagram of the architecture of Buildbot](/assets/img/buildbot_architecture.png)
_Buildbot uses a master-worker pattern as architecture, image source: [Buildbot](http://docs.buildbot.net/current/manual/introduction.html)_

At its core, Buildbot is quite similar to the large CI/CD systems mentioned above. However, it is focussed precisely on its use case, i.e. it does not offer code management, an artefact repository or a sprint dashboard.

The main application, also known as the build master, ensures that continuous integration management runs as defined. It is controlled via the so-called master.cfg, a configuration file consisting of Python code, and is available as an interface for all other components.

For example, Buildbot supports code management systems such as Git and Subversion, which can also be automatically queried and checked for changes. It is also possible to connect artefact repositories for built code. Last but not least, users have access to a clearly organised web application in which they can manually view the running CI/CD pipelines.

![An image of the landing page from the Buildbot web interface](/assets/img/buildbot_example_web.png)
_A clear web interface simplifies the overview, image source: [Limepepper](https://limepepper.co.uk/techtiles/buildbot.html)_

## Connection of different environments

However, in order to be able to run tests and build jobs in the form of pipelines on the required environments, Buildbot requires so-called workers in addition to the master server, which must be configured in the master.cfg with an authentication method.

Workers can simply be installed as a Python package on systems on which Python is installed and then executed as a service. This saves a time-consuming installation and a worker can be set up relatively quickly, even in a virtual machine or a container.

This is then available for any jobs that the master server assigns to this worker. Whether randomly via round-robin distribution or as a dedicated worker for specific jobs that should only run under a specific operating system can be flexibly customised in the configuration.

## Buildbot comes without an editor

The latter is done by specifying to the builder, the link between the scheduler and the finished job, which workers it may use. The manner, i.e. how often and when certain jobs should run, can also be set via the scheduler used, which manages under which circumstances or whether a job should be executed periodically.

![A diagram of the individual components of the Buildmaster](/assets/img/buildbot_config_architecture.png)
_The build master controls several individual components, image source: [Buildbot](http://docs.buildbot.net/current/manual/introduction.html)_

Unfortunately, Buildbot does not offer a graphical editor for such purposes, which could be used to edit the configuration without programming knowledge. Other systems are more advanced here and even offer ready-made templates. There are even only a few parameters available for the configuration in the interface, so that you have to adapt the configuration file and reload the system. At least buildbot offers a tool called `bbc`, buildbot check, to check the configuration for syntactical correctness before reloading.

## Configuration as Python code

As this is Python code, this can be a hurdle under certain circumstances, as the entry hurdle for developers is higher than with simpler definitions such as YAML. Python developers certainly have it a little easier here.

However, this also offers more flexibility. By using code, logic can be implemented that is difficult or impossible to realise in YAML. Alternatively, a large part of the build or test logic can also be mapped via scripts in Bash, Powershell or Make. Very simple pipelines can then be created in Buildbot, which are project-independent and reusable.

## Metadata can be managed by the user

Buildbot still uses a database to store data, which can be selected from several options. Thanks to the use of [SQLAlchemy](https://www.sqlalchemy.org/), MySQL and PostgreSQL work just as well as SQLite3. Buildbot then uses this database to save jobs, history, source code changes and certain settings, among other things. This means that the data is retained even in the event of short-term failures or restarts.

This also makes it possible to take care of backups and scaling yourself. It is also possible to integrate Buildbot into an existing company database. Metadata, which commercial providers are often unable to export, is therefore always in your own hands.

## Open source and free of charge

In my opinion, the biggest advantage is that Buildbot is open source software. This means that you are not primarily dependent on the manufacturer's decisions and can decide for yourself what you get.

If you rely on commercial solutions (with the exception of Gitlab, where large parts are also open source), you always have to trust that the provider will not release an update at short notice that causes maintenance work or renders certain functions unusable. Not to mention the high costs that you save without a subscription.

Of course, this can also be a disadvantage, as you have no guarantee from the project managers in the event of bugs. You are dependent on a group of volunteers for support and updates and have to maintain the system yourself. However, the project has been continuously maintained and developed for several years. And as it is also used by large projects such as Chromium, this is unlikely to change any time soon.

## Constant costs vs. high costs when needed

![Picture of a man lying under an old Beetle carrying out repairs](/assets/img/man-362150_640.jpg)
_Like an old car, you can repair Buildbot by yourself, image source: [RyanMcGuire](https://pixabay.com/de/photos/mann-wagen-reparatur-autoreparatur-362150/)_

At the same time, it can also be an advantage to rely on Buildbot, as the code can be adapted at any time, even if the developer has not yet implemented a certain bugfix or functionality.

Provided you have employees who are familiar with Python and Twisted. However, this should be a prerequisite in larger development departments. It should be borne in mind that Buildbot is licensed under GPLv2, which means that changes must be published again.

Nevertheless, fixing bugs yourself can also incur high costs, so it can be cheaper and easier to plan if you opt for a fixed monthly subscription that includes bug fixing. Critical bugs can otherwise become a bottleneck, especially if you don't have a lot of specialised staff.

## Buildbot is sustainable

Nevertheless, even with commercial systems, it is not always guaranteed that problems will be fixed quickly or at all. Sometimes weeks, if not months, can pass before a major update is released.

If you really need a quick fix, in the case of Buildbot you can also rely on external personnel. This means you can continue to use Buildbot and older versions of it for several years, whereas experience shows that you have to migrate commercial solutions as they are usually linked to managed infrastructure.

## Enterprise workloads are no problem

![Diagram of the Multimaster setup from Buildbot](/assets/img/buildbot_multimaster.png)
_Buildbot can be scaled by using a Multimaster setup, image source: [Buildbot](http://docs.buildbot.net/current/manual/configuration/multimaster.html)_

Even hundreds of pipelines are no problem for Buildbot in a setup with a single master. With a large number of users and many changes, however, it can become slow, at least in the web interface.

To counteract this, Buildbot can also be operated in a multi-master setup. In this case, several master servers exist side by side, which communicate via middleware such as Crossbar and distribute the load of the workers via load balancers such as HaProxy. Even the database can be scaled by replication as the load increases or secured accordingly by a capable administrator, as it is self-managed.

These masters can also use different configurations so that one is only used for the web interface while the others take over the actual tasks. Unfortunately, this type of setup is still officially experimental, but can certainly be used productively in self-tests.

## Conclusion: Buildbot keeps you independent

There is no question that Buildbot involves more administrative effort and complexity compared to commercial and managed solutions. SaaS cloud solutions can therefore also offer advantages in terms of scaling, as they work with on-demand infrastructure and often come from a single source. In addition, the monthly or annual cost structure is lucrative, as you quickly receive a ready-made system and support from a large provider.

However, with capable staff, Buildbot basically offers similar, if not more, functionality that can be expanded with infinite flexibility. And without any upfront costs, as familiarisation is also necessary for other systems. Whether on your own infrastructure or in the cloud, on physical or virtual machines or in a Kubernetes cluster, Buildbot is scalable and can be used for enterprise workloads. Another advantage is that you retain full control over the code and have access to all metadata, which is not usually the case with commercial systems.

If you want to work with a sustainable and open system, Buildbot is certainly not the worst choice. In the ever-growing landscape of CI/CD tools, it stands out due to its high flexibility and the right to repair.

_Further information regarding Buildbot you can find in the [official documentation](http://docs.buildbot.net/current/tutorial/index.html)._