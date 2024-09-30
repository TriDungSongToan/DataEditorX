# [DataEditorX]
Note: This is a modified version. You can download the original version here:

[URL]https://github.com/247321453/DataEditorX/raw/master/win32/win32.zip [URL]

## Operating Environment
This program is developed based on .Net framework 2.0 (3.5).
Required DLLs:
System.Data.SQLite.dll Database Operations
FastColoredTextBox.dll Script Editing
WeifenLuo.WinFormsUI.Docking.dll Multiple Tags
winXP (need to install .Net2.0)
win7 (comes with .Net2.0)
win8 (need to install .Net3.5 including 2.0)

## Application Configuration Settings
You can set up the Application Configuration in the Application Configuration window.
Do not edit the data grid in the Application Configuration window or edit the config file directly unless absolutely necessary.

## File association
.cdb (required)DataEditorX
.lua (optional) Notepad++/Sublime text/DataEditorX
### Method:
Left Click on File Menu, select Open File, browse for file, select, click OK.
Right Click on File, select Open File with, browse for application, select, click OK.
Note: By default, .lua will be opened by this program. If you need to modify it, set Open File in Application Configuration window to false.

## Settings
★ DataEditorX.exe.config
★ Language settings
★ Image settings
★ CodeEditor settings
★ data/language_xxx.txt Interface language and display text.
★ data/cardinfo_xxx.txt Series, Type, Race, Archetype, Attribute, Configuration/Ranking/Association Level, Category.
★ data/constant.lua List of (most) constants and their descriptions used in EDOPro
★ data/_functions.txt List of (most) functions and their descriptions used in EDOPro

## Language settings
You can add language files to the data folder yourself. At least 2 files are required. The language file name must be in the format:
language_xxx.txt
cardinfo_xxx.txt
Where xxx is the language you want.
For the list of functions and constants, you can delete everything in the data/constant.lua and data/_functions.txt files
Then copy everything in the corresponding files from the data/constants and data/functions folders and paste them into the deleted files.
NOTE: Make sure you have all the language files when doing this.
Available languages:
- English
- Vietnamese
- Traditional Chinese
- Simplified Chinese
- Japanese

## Application configuration settings
Left Click Windows, Configuration, Load Data.

### Image settings
- Image quality: accepts integers from 1~100
- Default size: accepts integers in the format a,b (only integers are accepted, a for width, b for height)

- Image size: The size of the two output images.
- Other size: The size of the cropped part of the regular image.
- eXceed Size: Size of the cropped portion of the eXceed image.
- Pendulum Size: Size of the cropped portion of the pendulum image.
Accepts integers in the format a,b,c,d

### Setting the rarity stamp
★ The stamp position on the exported image is in the following order: Stamp on small image - Stamp on large image.

Available positions:
- Top_Left
- Top_Right
- Bottom_Left
- Bottom_Right
★ Stamp size: accepts natural numbers in the format a,b,c,d
★ Stamp alignment: accepts integers in the format a,b,c,d as the stamp coordinates (Oxy coordinate system, with O in the upper-left corner, Ox pointing to the right, Oy pointing down).

Accept negative coordinates, but they must not be smaller than (stamp size * (-1)) and must not be larger than the size of the exported image (according to each corresponding side).

### Acceptable values:
★ "a,b,c,d"
- a: Small image width
- b: Small image height
- c: Large image width
- d: Large image height

★ For stamp margins
- a: Distance from the stamp edge (edge ​​parallel to the Oy axis, left edge if the stamp position is X_Left, right edge if X_Right) to the corresponding edge of the base image (small image).
- b: Distance from the stamp edge (edge ​​parallel to the Ox axis, top edge if the stamp position is Top_X, bottom edge if Bottom_X) to the corresponding edge of the base image (small image).
- c: Distance from the stamp edge (edge ​​parallel to the Oy axis, left edge if the stamp position is X_Left, right edge if X_Right) to the corresponding edge of the base image (large image).
- d: Distance from the stamp edge (edge parallel to the Ox axis, left edge if the stamp position is Top_X, bottom edge if Bottom_X) to the corresponding edge of the base image (large image).

### Code Settings
★ Font: Font used in the CodeEditor window, default is Consolas font
★ Font Size: Font size used in the CodeEditor window, default is size 14.5
★ Input Method: Using the input method will display text as usual, but the response speed will be slower
★ Line Wrap: Automatically wrap lines.
★ Tab-Space: Automatically convert Tab to Space
★ Async Load: true: Load background data asynchronously (display quickly), false: Load data directly
★ Change Card File: When modifying or deleting a card, the card image and content will also be deleted, modified or copied.
★ Open File: Open lua with the built-in script editor.
★ Check Update: Check for updates
★ Auto Rarity: Automatically use rarity for MSE images

## DataEditor

### ATK/DEF
To set the ATK/DEF index to '?', you can write ?, ?, -2.

The pics and script folders will be in the same parent folder as the .cdb file

### Change Card ID
When clicking Edit, if you select Delete, this will directly change the card ID (create a copy with the new ID and delete the original)
If you do not select Delete, this will only create a copy of the original Card with the new ID.

### Setting Rarity Stamp
Just put any image in the data/stamps folder, and it will show up in the rarity combobox.
Only .png images are accepted
You can use any file name, except "None.png"

### Setting Image Size
★ Auto Size
You can enter the width size of the output image in the width box, then click Auto Size, it will automatically calculate the height size according to the default ratio if the height box is empty.
Similarly, enter the height size to automatically calculate the width size.
If both the height and width boxes are empty, it will automatically set to the default size (set in the application configuration window)
If both boxes contain sizes but are invalid (width > height), it will automatically reverse these two values.

★ Set Size
Set the output image size based on the size from the width and height boxes.
The large image will have the dimensions of the two width and height boxes entered.
The small image will by default have each dimension 1/4 the size of the large image.
You can set the image size in the Application Configuration window.

## Read card list from .ydk file and pics folder

Supports: card ID, card name (.png, .jpg)

## MSE Archive
### Read
Archive file structure (requires: card content, first is "card", last is "gamecode", change gamecode to last part in MSE card_fields

card
...
gamecode: 123456
card
...
gamecode: 456789

### Images
Supports: card ID, card name (.png, .jpg)
When "Set MSE'Image" is selected, the card image will be placed in the MSE Image folder

## Extract data
Example: mydiy.cdb
- New card: deck/mydiy.ydk
- Description: mydiy.txt
- Script
- Pictures

Create mydiy.zip, can be placed in expansions, used directly or can be used for publishing.

## Compare Database
★ Lua search function
Get Lua functions from C++ source code
Return type, parameter type, C++ implementation code.

★ Card copy:
Replace copy: If there is a card, replace the latest card
Copy without replacement: ignore if the card exists

★ Card search
1. Only supports searching for the first Series name and does not support searching for Pendulum Scale.
2. Supports card name, effect description, rule, attribute, level, race, card type, effect type, ID
3.ATK, DEF search:
If it is 0, enter -1 or .search
If it is ?, enter -2 or ? search
4. Look up card name:
AOJ%% starts with "AOJ"
Liu%%tian starts with "liu" and ends with "tian"
%%Warrior ends with "Warrior"
5. Example of searching for password range:
--ID or card with the same name is 10000000. Card ID: 10000000 card with the same name: 0
--Card with the same name as 10000000. Card ID: 0 Card with the same name: 10000000
--Card with ID greater than 10000000 and less than 20000000. Card with the same name: 10000000 Card ID: 200000000

## CodeEditor
Enter the keyword in the text box below and press Enter
Ctrl+F Find
Ctrl+H Replace
Ctrl + left mouse button jump to function definition
Ctrl+K function list
Ctrl+T constant list
Ctrl+zoom text with mouse wheel

# Magic Set Editor 2
下载/更新："Magic Set Editor 2/download.bat"
或者
https://github.com/247321453/MagicSetEditor2

## MSE Archive Creation Settings
Edit \r\n in mse_xxx.txt of each language and it will be replaced by newline and \t will be replaced by tab.
Convert Simplified Chinese to Traditional Chinese,
cn2tw = false
Maximum number of each archive, 0 is unlimited
maxcount = 0
Find an image from the folder below and add it to the archive. The name is pass/card name.png/jpg.
imagepath = ./Images
Magic trap mark, %% is replaced by symbol If it is only %%, you need to put the ST mark after as text: yes.
spell = [Spell Card%%]
trap = [Trap Card%%]
Yugioh game, standard style, CN language, Edition: MSE, monster P middle image does not contain P area
head = mse version: 0.3.8\r\ngame: yugioh\r\nstylesheet: Standard\r\nset info:\r\n\tlingu: CN\r\n\tedition: MSE\r\n\tST mark is text: no\r\n\small pendulum image: yes
Read archive, card description
text =[Sword swing effect]\n%ptext%\n[Monster effect]\n%text%\n
Get P text
pendulum-text = 】[\s\S]*?\n([\S\s]*?)\n♥
Get monster text
monster-text = [fruit | introduction | report description]]\n([\S\s]*)
Replace special digits
replace = ([韟|鱇|・|·]) <i>$1</i>
Replace spaces with ^, (1/3 character width)
#replace = \s <sym-auto>^</sym-auto>
Replace A-Z with other font
#replace = ([A-Z]) <i>$1</i>
