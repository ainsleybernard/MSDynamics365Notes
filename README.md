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

2. When we do not have control over the target environments i.e. Development (solution V1 and then patch to v2) --> customer 1 (customizations), customer 2 (customizations), customer 3 (customizations)

Example 1

Solution Layering - concept

Effective Customisations, i.e Account Entity, Account Form, Custom attribute ( is combination of the three layers below it)

__Unmanaged__ Layer, i.e. Account Form (unmanaged layer being the layer that takes precedence as its the top most layer)

__Solution Managed Layer__ i.e. Account Form, Custom attribute

__System Layer__ i.e. Account Entity, Account Form (all the stuff that comes out of the box)

Example 2

Solution Layering - Managed Solution Layering

Effective Customisations, i.e Account Entity, Account Form A.2, Custom attribute ( is combination of the three layers below it)

__Managed Solution A (Version 1.2 Path)__ ie. Account Form A.2

__Managed Solution B (Version 1.2 Path)__ i.e Account Form B, custom attribute

__Managed Solution A (Version 1)__ i.e Account Form A

__System Layer__ i.e. Account Entity, Account Form (all the stuff that comes out of the box)

__Important The managed infastructure is so complex, must choose for the right reason.__

__Advantages__
Can control what customisations to our can be made
Can update and patch our solution without overwriting the customers customisations
Allows customer to delete the solution and fully unde the import

__Disavantages__
If the customer created dependencies on our solution, they cannot delete it
Historically there have been many bugs with managed import system
Unmanaged customizations are to overwrite (i.e forms)


## Naming solutions
One option is make the prefix specific to the solution that we're actually creating because it's acts like are namespace i.e.

## Import Manage Solution
if managed layer is sitting at the bottom, need to perform an upgrade which create a new solution on top of the layering, and once upgrade is complete the bottom layer is moved to the top.


## Package Deployer
Solution (i.e. entities, attributes) + Data (lookups, duplicate detections rules) = Pkg folder ( creates like installer wizard)
Multiple solutions can be included in package and export data using the __configuration migration tool__, which creates zip file that can be included in the package


## Creating plugin + deploy with spkl
1. add the pluginBase.cs from the sdk to your solution which contains should contain plugin library.
Note: common models, is to create a seperate class or assembly per plugin. __but we have control of entire project easier to have single entry point for plugins (benifit we can manage the order of execution, without worrying about the meta data, worrying about registrations__

## Adding NuGet Dependencies
Adding the latest version of micorosoft.crm.sdk.CoreAssemblies 9.0.2.26 requires at least .net 4.7.2

## Extra
1. If you are using PowerShell and are writing a custom script but cannot edit your system’s registry keys, you can also set your TLS settings using __ServicePointManager.SecurityProtocol:__

[Net.ServicePointManager]::SecurityProtocol = [Net.ServicePointManager]::SecurityProtocol -bOR [Net.SecurityProtocolType]::Tls12

## Installs
https://community.dynamics.com/crm/b/dynamics-ce-tech-blog/posts/dynamics-365-developer-toolkit-for-visual-studio-2017
