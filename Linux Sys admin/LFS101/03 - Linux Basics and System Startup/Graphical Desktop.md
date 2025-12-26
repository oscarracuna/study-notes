
Skipping the intro for this one.

# X Window System
Loading the graphical desktop is one of the final steps of the boot process.

A service called the Display Manager keeps track of the displays being provided and loads the X server to X clients.

X is a rather old software as it dates back to the mid 1980's. It has certain deficiencies due to its age since it was stretched far from its original purposes. A newer system, known as [[Wayland]], is gradually superseding it.
![[Pasted image 20251004232603.png]]

# More About the Graphical Desktop
A DE consists of a session manager, which starts and maintains the components of the graphical session, and the window manager, which controls the placement and movement of windows, window title-bars, and controls.

If the display manager is not started by default in the default runlevel, you can start the graphical desktop in a different way, by running `startx` from the CLI.
![[Pasted image 20251004233122.png]]
