# MSDynamics365Notes


Visual Studio Setup
1. Get VS extension "Web Essential 2017"
2. Get "Microsoft Dynamics 365 Developer Toolkit", which will provide templates
Note: the template creates a custom project ("CrmPackage in VS"), cant load without installing (downfall of using the template at least in version 8.)  __unable to get version 9 up yet__


Twp types of solutions __Manage__ and __Unmanaged__
How to Deploy?
Solution is the vehicle for which we deploy thinngs it includes
1. meta data i.e. entities
2. code

Managed
What it does not do
Does not enforce a good deployment process or make deployment easier

What it does
When we import a managed solution it will make it __read only__
Does allow solution layering and patching ( make changes to managed solution without affecting others solutions that sit on top)

Recommendation from the SDK
"When the unmanaged solution is complete and want to __distribute__ it, export it and packagae it as a managed solution"

 2 Types of distribution
1. (When we control all the target environments) i.e. DEV--> Build Server --> QA--> UAT--> Production (managed and unmanged makes no difference in this scenario)

2.

Solution Layering

Effective Customisations
__Unmanaged__ Layer, i.e. Account Form
__Solution Managed Layer__ i.e. Account Form, Custom attribute
__System Layer__ i.e. Account Entity, Account Form (all the stuff that comes out of the box)

## Naming solutions
One option is make the prefix specific to the solution that we're actually creating because it's acts like are namespace i.e.

## Extra
1. If you are using PowerShell and are writing a custom script but cannot edit your system’s registry keys, you can also set your TLS settings using __ServicePointManager.SecurityProtocol:__

[Net.ServicePointManager]::SecurityProtocol = [Net.ServicePointManager]::SecurityProtocol -bOR [Net.SecurityProtocolType]::Tls12

## Installs
https://community.dynamics.com/crm/b/dynamics-ce-tech-blog/posts/dynamics-365-developer-toolkit-for-visual-studio-2017
