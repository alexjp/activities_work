# File isolation on activities


## Using bwrap to allow file isolation

 - Using bwrap to isolate an app to a home beloging to the activity
 - Bwrap allows to bind some files/folders.
	 + Using that functionality to have common themes/fonts/cursor settings
	 + Having default settings for all dolphin/konsole/etc even though isolated
 - Using systemd-run to launch default apps
	 + Apps which autostart at activity starting
	 + Apps that should always be running
		 * So in my case, if I have 3 apps as default in the activity and I close 2, pressing Meta+1 will launch the 2 I had closed



## Folders/files documentation

- ### apps
	- Folders/files to bind overlay for specific apps. mainly settings I want shared through activities
- ### bin
	- Main activities scripts, being the activities.workspace the big one.
	- activities.id and activities.name are easy way to know which is the current activity
	- activities.run_default runs the default apps for the activity
	- activities.create_firefox creates a firefox profile for the activity
	- All the other files are symlinks to activities.workspace, in order for the script to be run instead of the original
- ### env
	- Setting for plasma to have the path of `bin` before the real binary/app. way to make the activities.workspace be ran.
- ### activities.sync.glocal
	- Basic files/folders to bind overlay in order to have proper theme/gtk theme/mouse cursor/fonts between isolated activities.
- ### windowmanagement.kwinscript
	- Custom kwin script to manage rules for apps in a per activity case.
	- Also does some custom stacking tiling, for my usecase. (not general case use, very custom to my liking only)
	



