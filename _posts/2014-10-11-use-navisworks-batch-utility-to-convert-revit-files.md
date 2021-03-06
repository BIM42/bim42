---
id: 633
title: Use Navisworks Batch Utility to convert Revit files
date: 2014-10-11T10:00:45+00:00
author: Simon Moreau
layout: post
guid: https://www.bim42.com/?p=633
permalink: /2014/10/use-navisworks-batch-utility-to-convert-revit-files/
categories:
  - Coordination
image: /assets/2014/10/Project.jpg
tags:
  - Automation
  - BIM Manager
  - Navisworks
  - Tips
---
A few days ago, I had to convert a large set of Revit files to NWC in order to create a general Navisworks File Set.

I used the Navisworks Batch Utility ![ScreenClip1]({{ "/assets/2014/10/ScreenClip1.jpg" | absolute_url }}), accessible through the Navisworks main menu:

![ScreenClip-12]({{ "/assets/2014/10/ScreenClip-12.jpg" | absolute_url }})

You first have to select files to be included in your Navisworks File Set.

To quickly retrieve the list of Revit files to be converted, I'm using the Windows Command Prompt. I was quite afraid of this tool not so long ago, but it is actually pretty simple.

![ScreenClip-21]({{ "/assets/2014/10/ScreenClip-21.jpg" | absolute_url }})

First, go to the root folder of your project:

{% highlight posh %}
cd C:\Projects\myRevitProject
{% endhighlight %}

and type :

{% highlight posh %}
dir /s /b *.rvt >ListRevitFiles.txt
{% endhighlight %}

This line requires a bit of an explanation:

* _dir_ : command for searching and displaying file in the current directory
* _/s_ : search in the current directory and all its subdirectories
* _/b_ (or bare) : remove for each file its metadata to display only the file path
* _*.rvt_ : search specifically for Revit files
* _>ListRevitFiles.txt_ : the ‘>’ character allows us to output the result of our research to a text file (here ListRevitFiles.txt) instead of displaying it.

We get the results of our research as text file listing paths to every Revit model contained in our project folder:

{% highlight posh %}
C:\Projects\myRevitProject\CENTRALS\ARC.rvt
C:\Projects\myRevitProject\CENTRALS\MEP.rvt
C:\Projects\myRevitProject\CENTRALS\STR.rvt
{% endhighlight %}

Back on the Navisworks Batch Utility, we open this text file to import file paths: File -> Open -> Select ListRevitFiles.txt

![ScreenClip-31]({{ "/assets/2014/10/ScreenClip-31.jpg" | absolute_url }})

As we want to create a single Navisworks File Set (.nwf), we select the "As Single File" Tab, and set the path to our future Navisworks File.

![ScreenClip-4]({{ "/assets/2014/10/ScreenClip-4.jpg" | absolute_url }})

I also select "View file on output" to automatically start Navisworks when conversions are done.

We add a path to a log file in order to know what may happen, and hit "Run Command".

Here, I was confused by the fact that nothing seems to happen, but after checking my computer processes, I was able to see that the Navisworks Scene Convert Server was up and running.

![ScreenClip-5]({{ "/assets/2014/10/ScreenClip-5.jpg" | absolute_url }})

After a while, Navisworks starts automatically and appends every previously created .nwc file to a new Navisworks File Set.

![Project]({{ "/assets/2014/10/Project.jpg" | absolute_url }})

I am also using this feature to create a NWD file for a set of Revit file.

To do so, you just have to select the "Multiple file" tab and define a target folder for the export.

![ScreenClip-61]({{ "/assets/2014/10/ScreenClip-61.jpg" | absolute_url }})

The Navisworks Batch Utility will convert every Revit file to a NWC cache file, and made it a NWD on the run.