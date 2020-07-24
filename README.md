# MSDynamics365Notes

## Naming solutions
One option is make the prefix specific to the solution that we're actually creating because it's acts like are namespace i.e.

## Extra
1. If you are using PowerShell and are writing a custom script but cannot edit your system’s registry keys, you can also set your TLS settings using __ServicePointManager.SecurityProtocol:__

[Net.ServicePointManager]::SecurityProtocol = [Net.ServicePointManager]::SecurityProtocol -bOR [Net.SecurityProtocolType]::Tls12
