# What is Kurumi?

A way to get root by modifying the kernel on Android

# How does it work?

Kurumi has two ways of working KPI(Kernel Patch Interface) and LKM.(Loadable Kernel Module) KPI modifies the Linux kernel to provide an interface for manipulating kernel space. LKM modifies Ramdisk to call kernel function for authorisation.They all do one thing.：Mount the su binaries into userspace via Systemless .Managing authorisations through whitelisting in the Control Centre.Available only to whitelisted applications su. The authorisation process will operate in kernel space

# Invisibility

It is difficult for detection software to find it when using only the Kurumi core mode. If you are using a non-LKM module, then you may need to flash in the appropriate hidden modules

# Compatibility

LKM can run on third-party kernels, provided the kernel author allows you to do so.. The KPI just provides an interface and does not modify the kernel too much, and it works fine with the consent of the kernel author.
Although KPI can theoretically run on third-party kernels, I still don't recommend that you run it on a third-party kernel; Kurumi may suddenly stop working!
If you're using some of the KVM exploit kernels, the KPI works fine (and should)

# Safety

Kurumi has a super key, which is added to the kernel at patch time, and is verified each time a module is licensed or installed using Kurumi
In Kurumi, you can have the shell validate the superkey before executing dangerous commands like rm dd (not yet)

# Current situation

As of 2024.12.22, the KPI interface is working, but authorisation is failing and LKM is still under development as to. why it's so slow
1：I'm not the kind of person who copies other people's work indiscriminately, even if it takes me a few more months, I'm not going to go around copying code and end up creating a sewing monster with a lot of problems
2：I'm a newbie, I'm thankful that this thing can be made, and I'm not looking for any production speed (I'll update it more often later when I get better at it)
You'll probably be able to use it before 2026 arrives.
