### Replace a git branch by another:
This effectively replace all files in master by the files from mybranch
`git checkout mybranch`
`git merge -s ours master`
`git checkout master`
`git merge mybranch`


### List all programs installed on a computer:
`dpkg --get-selections > list.txt`

### Install all programs from a txt file:
`sudo dpkg --set-selections < list.txt && sudo apt-get -u dselect-upgrade`

### List all atom packages installed on a computer:
`apm list --installed --bare > package-list.txt`

### Install all atom plugins from a list:
`apm install --packages-file package-list.txt`

### Show the current directory:
`pwd`

### Show files modified in latest commit :
`git show --stat`

### Put a window always on top:
Alt-space => t

### Singleton design pattern allows access to a class from anywhere in any class:
http://stackoverflow.com/questions/1008019/c-singleton-design-pattern

### Change Okular thingies:
`qtconfig-qt4`

### Obtain the translation of an english word:
`dict -d fd-eng-fra mot`

### Encrypt a file:
`gpg -c myfinancial.info.txt`

### Decrypt a file:
`gpg -d myfinancial.info.txt.gpg`

### Update "locate" command:
`sudo updatedb`

### Chage webp to png:
`find . -name "*.webp" | xargs -I {} dwebp {} -o {}.png`

### Change uubntu login screen dots:
`xhost +SI:localuser:lightdm`
`sudo su lightdm -s /bin/bash`
`dconf-editor`

navigate to
com/canonical/unity-greeter

`set draw-grid to false`

### Toggle volume from command line:
`amixer -D pulse set Master +1 toggle`

### Change volume level:
`amixer -D pulse sset Master 20%+`

### Disable touchpad
`xinput list`
`xinput --disable xx`

### Merge all pdf in a folder
`pdftk *.pdf output name.pdf`

### Convert all .doc to .pdf
`for FILE in *.doc ; do unoconv "$FILE" ; done`

### Return the current location in a command line
`cp /home/archangel/Templates/latex.tex $PWD/newfile.tex`

### Lookup a keyword in the man pages:
`apropos Stallman`

### Restart KDE5 Plasma
`kquitapp5 plasmashell && kstart plasmashell`
`killall plasma-desktop && kstart plasma-desktop`
`sudo service sddm stop`

### Change the wallpaper based on the hour, in "sudo crontab -e":
`* * * * * su archangel -c "DISPLAY=:0.0 $(which python3) /home/archangel/Pictures/DrWho/DrWho.py"`

### Give information on commands website
tldr.sh (yes, a website)
cheat.sh (yes, a website)

### List the new name of files after removing the first 4 characters (remove -n to apply changes):
`rename -n 's/.{4}(.*)/$1/' *.`
	
### CopyFolderStructure
First, in the directory with the folder structure you wish to copy, lauch:
`find . -type d > dirs.txt`

Then replace all space characters by \[space]
Finally, in the folder where you want the folder structure to exist, launch:

`xargs mkdir -p < dirs.txt`

### Access WSL files from Windows Explorer
WSL files and folders are stored in
`\\wsl.localhost\Ubuntu-22.04`

## Matlab Notes
### Change default figure size & position
`set(0, 'DefaultFigurePosition', [-1079,-161,1080,1843]);`
`opengl('save', 'hardware')`

#### WFH Setup
`set(groot, 'DefaultFigurePosition', [-4519 -77.4000 1068 1.8048e+03]);`

#### WFO Setup
`set(0, 'DefaultFigurePosition', [-1079,-161,1080,1843]);`

###  Roundcasting
Rounding to the closest multiple of 7: `round(day_tmp/7)*7`

Same but systematically want the greater bound: `ceil(day_tmp/7)*7`

### List Membership
To check whether an element is part of a list: `ismember(dataTable.Time, dataTable.Time([1,2,33])`
To check whether a datetime is between two datetime: `isbetween(t, tlower, tupper)`
### Array Operations
To reverse the order of an array: `flipud`
Moving mean of a matrix: `movmean(posMat(:,1), 30)`


### Convert mongo time to matlab times
`local_start_time_timestamp = user_data_mongoDB(idx).localDate.x_date;`
`local_start_time_datetime = datetime(local_start_time_timestamp/1000,'ConvertFrom','posixtime');`

### Extract recordings from multiple subjects at once
`test = Extract_mongoDB_data('{$in:[203, 204]}', 'measurements');`
`test = Extract_mongoDB_data('{$in:[203, 205, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 267, 268, 269, 270, 271, 272, 273, 274]}', 'measurements');`

### Prevent MATLAB from automatically adding objects to legends
`legend(ax(ax_idx), 'AutoUpdate', 'off')`

### Find the position of a string in a cell array (multiple matches/patterns possible)
`find(contains({visitMarkers.Label}', {'Sync', 'mama'}))`

### Generates list of mail adresses
`strcat(repelem("studyName+p", 40)', string([1:40]'), repelem("@gmail.com", 40)')`

