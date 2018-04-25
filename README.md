Services
===

## Move to WPP
---
This service is useful for people who would like to keep their downloaded wallpapers in one place and stored in folders by their `<width>x<height>` folders with one click.

### Dependencies
* **Identify** (part of **Imagemagick**) https://www.imagemagick.org/script/identify.php. Install with brew by issuing `brew install imagemagick`. If for whatever reason you do not have brew installed, follow the instructions at https://brew.sh/

### How to use it
Copy or symlink the `service/Move to WPP.workflow` file to `/Users/$USER/Library/Services/Move to WPP.workflow`. Follow instructions below for either option..

1. Open terminal
2. `cd <path to project>`
3. Choose either Copy or Symlink
Symlink: `ln -sf $PWD/service/Move to WPP.workflow /Users/$USER/Library/Services/Move to WPP.workflow`
Copy: `cp service/Move to WPP.workflow /Users/$USER/Library/Services/`

### Default place for wallpaper files
By default, the files will be placed in `/Users/$USER/Pictures/wpp/<width>x<height>` folder. If you want to change this, you will have to open the workflow and change `/Users/$USER/Pictures/wpp`whatever path you want your resolution folders to reside in.

### The workflow
Workflow will perform following steps for **each** file the service is run for.
1. Find out the input image file resolution
1. Make sure the destination directory exists
1. Move the image file to the destination directory

---