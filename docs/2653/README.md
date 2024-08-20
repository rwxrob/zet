# How to separate work and personal stuff on work laptop

These days the line between work and personal IT systems is very hard to define. As more things move to the cloud one's personal phone or laptop can be used for work communications, code commits, and more. So much so that these days some companies don't even issue computers to their employees giving an allowance of money to spend on their own personal preference instead.

These working conditions seriously blur the lines of "proprietary" boundaries with regard to IP law. At one point using a work device even to read or write a personal email on the Internet made whatever was written in the legal property of the company that owned the device. In fact, an entire plot arc from Silicon Valley is based on the protagonist doing exactly that and losing his entire company.

Those days of "work only on work devices" seem long gone. Knowledge workers regularly use personal devices for all sorts of work communications that fall under work ownership. Let's look at some very real use cases:

* Update a zettelkasten entry with a thought perhaps triggered at work but not work related
* Change something in personal dot files and use it both at work and home
* Apply a technique learned at work to an unrelated personal open source project
* Use home lab to test a deployment or scenario that is untestable at work

Obviously, the safest solution is to do everything personal from a personal machine and work from a work machine. This minimally requires carrying around two laptops at the same time in order to context switch in the most separate way possible between work and personal stuff.

Personally, however, I find use of `ssh` and RealVNC to make all the difference. These technologies provide very clear distinction between personally owned and work-owned devices. This is because `ssh` and VNC are merely remote access *clients* providing no more proprietary bonding of the use of that remote device than would be granted to anyone using any cloud-enabled technology. To compare, consider a company attempting to claim ownership of your email because you uses a work computer to access your gmail account over the Internet. Such a claim would be laughed out of court. That company, could, however, perfectly legally monitor the screen of their device while you used it to use these remote access technologies.

* Install RealVNC Server on personal gateway desktop
* Install RealVNC Viewer on work laptop
* Keep RealVNC Viewer easily available during the work day
* Use RealVNC to update dot files, personal notes, and configuration changes during day
* Use work device itself for only work stuff and to `git pull` read-only copies of dot files
