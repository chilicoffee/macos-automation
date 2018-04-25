# Services

1. [Move to WPP](#move-to-wpp) - Automatically move image file(s) to their resolution folder
1. [Set Desktop Picture on Display N](#set-desktop-picture-on-display-n) - Assign selected image file as wallpaper for desktop `N`

More about MacOS services here: https://support.apple.com/kb/PH25241?viewlocale=en_US&locale=en_US

### How to install a service
Copy or symlink the `service/<worfklow file>` file to `/Users/$USER/Library/Services/<worfklow file>`. Follow instructions below for either option..

1. Open terminal
2. `cd <path to project>`
3. Choose either Copy or Symlink
Symlink: `ln -sf $PWD/service/<worfklow file> /Users/$USER/Library/Services/<worfklow file>`
Copy: `cp service/<worfklow file> /Users/$USER/Library/Services/`

Move to WPP
---

This service is useful for people who would like to keep their downloaded wallpapers in one place and stored in folders by their `<width>x<height>` folders with one click.

### Dependencies
* **Identify** (part of **Imagemagick**) https://www.imagemagick.org/script/identify.php. Install with brew by issuing `brew install imagemagick`. If for whatever reason you do not have brew installed, follow the instructions at https://brew.sh/

### Default place for wallpaper files
By default, the files will be placed in `/Users/$USER/Pictures/wpp/<width>x<height>` folder. If you want to change this, you will have to open the workflow and change `/Users/$USER/Pictures/wpp`whatever path you want your resolution folders to reside in.

### The workflow
Workflow will perform following steps for **each** file the service is run for.
1. Find out the input image file resolution
1. Make sure the destination directory exists
1. Move the image file to the destination directory

Set Desktop Picture on Display N
---

While MacOS has built in service for setting the wallpaper for the main display, it does lack support for other displays. This service will apply the selected picture to as the wallpaper of `N` display

### Dependencies
None