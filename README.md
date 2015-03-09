# Minisat-2.2.0-for-windows

Minisat 2.2.0 compiled with mingw for Windows. It should work in Windows 2K and more recent versions.

(<b>PRELUDE:</b> this Minisat binary for windows was deployed in Keepandshare a couple years ago, but as of now (March, 2015) that site has ended as a repository. So I am moving it for here and replicating the emails sent to the Minisat list, two years ago in March 2013, with the relevant information. I hope it still is useful for some people. I haven't used minisat since then, so the version 2.2.0 can eventually be outdated.) 

########################## 

Thanks to Niklas & Niklas for building such a useful and nice CAD tool. 

I'm attending Coursera's course "VLSI CAD: Logic to Layout" lectured by Prof. Rob Rutenbar where we are using minisat. I saw that the Windows binary provided at minisat site is a bit outdated (v. 1.14 and cygwin based) and so, after a few tries, I ended up tweaking a bit the official minisat 2.2.0 sources and being able to compile them with mingw in a Win2K windows box. 

The tweak was basically commenting out the code that sets/checks CPU limits and memory limits (using Linux kernel constants, such as SIGXCPU, etc...), so I think the SAT algorithm is not affected and probably the binaries are usable. I compiled also in a Linux box and the limits given in "minisat --help" are equal to those in the windows binaries. 

I checked a couple of small examples and they seemed to work well, but I didn't test extensively (didn't found many examples, but I didn't google too much...). 

I posted an announce and a public link to the binary at the CAD course forums, which I copy below (you probably cannot access the forums). If you can point to me some more examples suitable to do testing, I'll be glad to do it. It you want to post the link in the minisat page (supposing the binaries work well), that would also be nice. The link I give is from an anonymous "warehouse" -- Keepandshare.com -- but I can also put the binaries in a server of my institution (Inesc-id, Lisboa, Portugal). 

So, without further ado, the <b>UPDATED link</b> with the zip file is https://www.dropbox.com/s/unr78t14q8d6ir6/minisat.zip?dl=0 

And the post I did in VLSI-CAD forums which give a few more expplanations is below. 

Kind Regards, 

José Soares Augusto 

########################## 

Hi all, 

I tried to find a recent minisat version for windows and didn't found it. Then I tried to compile the recent minisat 2.2.0 with mingw but there were problems with the code that sets the limits of CPU and memory (certain constants defined in the Linux kernel, absent in windows). So I patched the ministat source (i.e. commented a few parts) until it compiled. IMHO only the limits (of memory and CPU resources) stay very large in these binaries, so beware using them with large (or evil :-)  boolean functions. 

There are 4 executables of minisat in the zip archive. The standard version, and another version with simplification algorithms (read the info in the minisat page,  http://minisat.se/Main.html), both in static and non static versions. The non static versions rely in Windows libs or in mingw libs (or both?). 

The archive can be downloaded in this <b>UPDATED link:</b> https://www.dropbox.com/s/unr78t14q8d6ir6/minisat.zip?dl=0

I didn't try these executables extensively, but they seemed to work in a few small cases. Use at your own risk, but I think that the large limits are the only "issue". These limits are large (seen with 'minisat --help'): 

  -cpu-lim      =   [   0 .. imax] (default: 2147483647) 
  -mem-lim      =   [   0 .. imax] (default: 2147483647) 

If someone gets into some problem in using the binaries, please comment under this thread and I'll try to fix (iff its related with the modified sources...) 

P.S - In Linux Mint 11 (Ubuntu-12 derived) minisat compiled flawessly from the sources with gcc 4.5.2 toolchain. 

############################### 
