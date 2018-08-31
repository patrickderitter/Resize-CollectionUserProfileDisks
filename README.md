# Resize-CollectionUserProfileDisks.ps1
## .SYNOPSIS
Extends all existing User Profile Disks to new maximum size configured on the collection
## .DESCRIPTION
After you reconfigure User Profile Disk maximum size on a RD Session Collection, the already existing User Profile Disks do not automatically get the new maximum size. This script iterates all the User Profile Disks to resize and extend them, unless in use. In case a User Profile Disk already has a larger maximum size, we skip it.
## .PARAMETER CollectionName
The RD Session Collection Name. You can get this using Get-RDSessionCollection on your RD Connection Broker.
## .PARAMETER ConnectionBroker
(optional) The FQDN to the RD Connection Broker. If omitted, the local FQDN will be used.
## .NOTES
Version:        1  
Author:         Patrick de Ritter  
Creation Date:  2018-08-31  
Purpose/Change: Initial script  
License:        MIT License

    Copyright (c) 2018 Patrick de Ritter

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.
## .EXAMPLE
````powershell
PS C:\> .\Resize-CollectionUserProfileDisks.ps1 -CollectionName somecollection.deployment.tld -ConnectionBroker somebroker.deployment.tld
````
Resizes all User Profile Disks already created for the specified collection to the maximum size.
