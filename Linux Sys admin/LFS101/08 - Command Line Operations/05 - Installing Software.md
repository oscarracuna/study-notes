
# Package Management Systems on Linux

The core parts of a Linux distro and most of its ad-on software are installed via the [[Package Management System]]. Each package contains files and other instructions needed to make one software component work well and cooperate with the other components.
**Packages can depend on each other**. For example, a package for a web-based application written in Python will require the appropriate Python packages to be installed first.

| Debian | RedHat |
| ------ | ------ |
| APT    | RPM    |

# Package Managers: Two Levels

Both systems operate on two distinct levels: 
**Low level tool**: 
- dpkg or rpm. Takes of the details of unpacking individual packages, running scripts, installing software correctly.
**High level tool**:
- apt, dnf or zypper. Works with groups of packages, downloads them from the vendor and figures out dependencies.

![[Pasted image 20251103203943.png]]

# Working With Different Package Management Systems

The Advanced Packaging Tool ([[apt]]) is the underlying package management system that manages software on Debian-based systems. Distros like Ubuntu use it for their GUI (Ubuntu Software Center), it's CLI native.
`apt-get` 

[[dnf]] is the open source CLI package management utility for the RPM-compatible systems (Red Hat family).

[[zypper]] is the package management system for the SUSE/openSUSE family and it's also based on RPM.

![[Pasted image 20251103204458.png]]

| **Operation**                     | **rpm**                               | **deb**                     |
| --------------------------------- | ------------------------------------- | --------------------------- |
| Install package                   | **rpm -i foo.rpm**                    | **dpkg --install foo.deb**  |
| Install package, dependencies     | **dnf install foo**                   | **apt install foo**         |
| Remove package                    | **rpm -e foo.rpm**                    | **dpkg --remove foo.deb**   |
| Remove package, dependencies      | **dnf remove foo**                    | **apt autoremove foo**      |
| Update package                    | **rpm -U foo.rpm**                    | **dpkg --install foo.deb**  |
| Update package, dependencies      | **dnf update foo**                    | **apt install foo**         |
| Update entire system              | **dnf update**                        | **apt dist-upgrade**        |
| Show all installed packages       | **rpm -qa** or **dnf list installed** | **dpkg --list**             |
| Get information on package        | **rpm -qil foo**                      | **dpkg --listfiles foo**    |
| Show packages named **foo**       | **dnf list "foo"**                    | **apt-cache search foo**    |
| Show all available packages       | **dnf list**                          | **apt-cache dumpavail foo** |
| What package is **file** part of? | **rpm -qf file**                      | **dpkg --search file**      |
