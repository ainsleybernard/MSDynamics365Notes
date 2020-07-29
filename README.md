# MSDynamics365Notes


Visual Studio Setup
1. Get VS extension "Web Essential 2017"
2. Get "Microsoft Dynamics 365 Developer Toolkit", which will provide templates
Note: the template creates a custom project ("CrmPackage in VS"), cant load without installing (downfall of using the template at least in version 8.)  __unable to get version 9 up yet__


## Naming solutions
One option is make the prefix specific to the solution that we're actually creating because it's acts like are namespace i.e.

## Extra
1. If you are using PowerShell and are writing a custom script but cannot edit your system’s registry keys, you can also set your TLS settings using __ServicePointManager.SecurityProtocol:__

[Net.ServicePointManager]::SecurityProtocol = [Net.ServicePointManager]::SecurityProtocol -bOR [Net.SecurityProtocolType]::Tls12

## Installs
https://community.dynamics.com/crm/b/dynamics-ce-tech-blog/posts/dynamics-365-developer-toolkit-for-visual-studio-2017
