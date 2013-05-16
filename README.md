astra_schedule_custom_theme
===========================

Custom theme for the Ad Astra Schedule application.  This repo only has the modified files for the custom theme.

Servers:
  OIT-CLS-SCHED01.oit.umn.edu (alias: astra-tst.oit.umn.edu)
  OIT-CLS-SCHED02.oit.umn.edu (alias: astra-prd.oit.umn.edu)

File Shares:
  smb://OIT-CLS-SCHED01.oit.umn.edu/d$ (dev/ent)
  smb://OIT-CLS-SCHED02.oit.umn.edu/d$ (prod)

Instances:
  Dev/Test 	- https://astra-tst.oit.umn.edu/AstraDev
  Ent      	- https://astra-tst.oit.umn.edu/AstraEnt
  Prod		- https://astra-prd.oit.umn.edu/AstraProd

Deployment:
  Hand copy all files in the repository except the README.md file.  Connect to the file share for the instance your wish to deploy to and navigate to the following directory structure:
Share
	Program Files (x86)/
		Ad Astra/
			[current version number]/ (example: 7.5.7.199/)
				Instances/
					[Astra instance]/ (example AstraDev/, AstraEnt/ or AstraPrd/)
						/Schedule   

Copy all files in the repository to the schedule folder.  Refresh the instance to ensure the server is now branded appropriately.

Access:
  Chris Dinger and Eric Eklund have admin access to the Astra Schedule servers.  Bob Quinney is the technical contact in OCM.  I will request that the ASR Web team AD group be added as admin to the box (05-16-2013).




Additional Information on Theming Astra:

Default Astra Schedule Theme Files

The default Astra Schedule theme consists of image and color backgrounds that are controlled by a series of CSS files.  The core default styles reside in base.css (App_Themes/Default).  The default styles may be overridden by customizations in a zcustom.css file placed in the zcustom folder.  If this file exists, you should never need to edit base.css.
 
Astra Schedule versions 7.4+ utilize an additional set of CSS files and graphics in order to support a new user interface framework.  The application is evolving to use this new framework, and eventually the plan is to remove the CSS controls in the App_Themes directory.  For now, style changes must be made in both locations in order to support the two separate framework structures.  These files are located in the Theme directory.  For custom changes please make those changes, and add additional graphics in the Theme/custom directory.  Specifically, style adjustments made here are set up to overwrite styles and graphics that are set in the CSS files in the Theme directory.

Customization Notes

NOTE: Before any custom work is started, a copy of the App_Themes and Theme directories should be archived on a storage device.  External storage is recommended to eliminate the possibility of your custom work being overwritten by a backup.
 
The best way to customize Astra Schedule styles is to use zcustom.css to overwrite existing styles from base.css, and custom-extjs.css to overwrite existing styles from AstraExtTheme.css.  Two great tools for sniffing styles to edit are either Firebug or wedev toolbar.  Both are usable with FireFox.

Customization File Locations

All custom files (CSS and images) should be added to the zcustom directory within the App_Themes/Default folder and Theme/custom for 7.4+ versions.  Custom files should be placed in the zcustom directory because your custom CSS files will be inherited alphabetically.  Also, placing all custom files in these directories will help identify which files are custom.  To revert to the default Astra Schedule theme, simply remove the custom files from the appropriate directory.

Current install path: d:\Program Files (x86)\Ad Astra\7.5.7.199\Instances\AstraDev\Schedule (may change depending on version)

App_Themes/
	Default/
		AstraStyleLibrary/
		Images/
		zcustom/
			zcustom.css (This is the main file for customization)
			
Theme/
	custom/
		custom-base.css
		custom-calendar.css
		custom-extjs.css

zcustom.css, custom-base.css and custom-extjs.css were all blank CSS files that were there to be utilized for custom branding.  These are the files that should be edited rather than the base.css files.  Custom images can be placed within the respective zcustom or custom folder.
 
NOTE: There is no guarantee that custom theme work will be preserved when upgrading Astra Schedule.  It is recommended to create a backup of the zcustom directory once work is complete, as well as another backup just before an upgrade.  Additionally, it may be possible that future versions of Astra Schedule could have style structure changes that would obsolete some or all customizations.
 
The CSS file that custom styles need to be added to is named zcustom.css, and custom-extjs.css for 7.4+.  By default, these files are blank CSS files.  Any other CSS files added to zcustom will not be utilized by Astra Schedule.
 
If the zcustom directory does not exist on your build of Astra Schedule, you will need to add the custom styles to base.css in the Default directory.  All images can be placed in the zcustom directory.  If a directory is created and a CSS file is placed in that directory, the application will not recognize the file.  Therefore, a blank zcustom.css is currently deployed in the zcustom directory to support customizations.

