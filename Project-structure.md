## Repositories
AOSP consists of nearly 800 git projects, all of them are declared in Android manifest. In order to add support for different platforms we should fork AOSP manifest and some other repositories. This could be confusing at first, since one real-world project is split up into gazillions of git repos, but things are a bit easire once you've got used to it. Therefore here's a list of our own repositories, main work are done here:
* [Manifest](https://github.com/glodroid/glodroid_manifest) - Android manifest that declares which repositories should be downloaded from which source/branch to which place.
* [Device](https://github.com/glodroid/glodroid_device) - platform declaration, build flags, included packages, different config files such as fstab, init scripts etc.
* [Forks](https://github.com/glodroid/glodroid_forks) - there are several branches, each has it's own fork: Linux kernel, DRM HWComposer and Mesa3d drivers.

## Directories structure
Android has immense directory structure, so it's easy to get lost at first times when you're trying to do at least something. Therefore here we'd provide at least basic info about different directories, their contents and purpose. We won't cover all, though, only ones that is most commonly touched during day-to-day development. Here's a list of them:
* `build` - Android build system and core Makefile, it contains most of build rules 
* `device` - Has several subdirectories that contains platform declarations and configurations. Our configs are located into device/glodroid/ directory.
* `external` - External projects, which aren't managed by Google and isn't stricly AOSP projects, e.g. Das U-Boot, DRM HWComposer, etc.
* `framework` - Android services that userspace is supposed to interact with. Upper level of Android, if you could say so.
* `hardware` - Contains HAL declarations and AOSP implementations of it, whether full-fledged implementation or a mock one.
* `kernel` - Linux kernel, obviously. Should I say more?
* `packages` - AOSP userspace applications and services that are included into resulting build.
* `system` - Core Android services, such as init process, adb, etc.