---
layout: post
title : PDQ Deploy + Fog = Awesomesauce
---

I've been using the [FogProject](https://fogproject.org) for imaging for quite a while now. It's been a fantastic answer to most of my 
imaging needs, as well as a quick solution for managing my gear. One problem, however, has been that it's still tied to the
older style of fat client imaging. Fat client imaging, if you're not familiar, is the old style of slapping everything you 
need into one single image, and pushing it out. It works great, until you need to change something down the line. A good example
would be updates to Java or something like that. With a fat client image, you need to make the change, rebuild the whole image, 
and go from there. It works, but it could be better. 

An easier solution is a thin client image. In this, you push down just a base, bare bones image. In my case, that includes Win7
and Office 2013. Nothing else on top of it. After the image is applied, you push out the rest of your software independantly. The
real benefit of this is that you can change your software deployment, while not having to worry about your image. You can also change your
image deployment without worrying about the software! 

Now, FOG doesn't really have a solid way to do this completely on it's own. Enter another great piece of sofware, [PDQ Deploy}(http://adminarsenal.com).
PDQ Deploy by Admin Arsenal is a tool to deploy software to Windows based clients quickly and easily. It allows you to basically take any exe, msi, or batch 
files and send it out to clients via the network from one screen. With the professional license, which is super cheap, you can also schedule these out. 
They also have a tool called PDQ Inventory that allows you to collect an inventory on these units, and thats where it gets awesome. You can filter 
these inventorys based on a scriptable interface. So, if you want to update Chrome on clients that aren't at the current version, but don't want to 
waste time reinstalling those that already have it up to date, you can create a collection in PDQ inventory that only includes machines whose Chrome is
not at a current date. Then, you can deploy Chrome to that collection either on a schedule, or even when the machines turn on next on the network. 
It's been a life saver on its own. But when we tie it into Fog, magic happens

## Lets make some magic

