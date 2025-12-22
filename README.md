A simple script that uses demucs to split an audio file then loads those parts into Audacity.  
An audio file  can be selected from Dolpin file manager context menu which starts the demucs process.
When finished, the split parts are opened as separate tracks in Audactiy.
(Also see the simple alternate ways at the bottom)

Tested setup has/requires
- Ubuntu 24.04 KDE using Dolphin file manager (using right click menu to launch process)
- An install of demucs https://github.com/facebookresearch/demucs/tree/main
- Pyenv to separate python environments. Recommend using a discreet pyenv environment
  for this as requires numpy not current numpy2 etc
- Audacity audio application

Initial setup is manual.
- Once pyenv and a suitable python version is installed, install demucs in that environment
- Copy demucs_me.desktop file to ~/.local/share/kservices5/ServiceMenus/
- Edit the line starting with Exec for correct username. Make it executable.
   (a restart may be required to make it visible)
- Copy the mydemucs file into a location in your path. Eg  ~/.local/bin 
- Edit the mydemucs file. Enter correct pyenv info at top, and edit the required outfile location.
- Make it executable. 

To run 
- Select an audio file by right clicking the file in Dolphin
   > Actions > Split Audio File
- Terminal should open with some information and commence the demucs process. A normal length pop
  song takes about a minute on my machine.
- Files are created in the outfile location
- Audacity should start with the four tracks
- Press play etc to use
- After closing the same files can be relaunched by right clicking the demucs.lof file that has been added,
  and select
  > Open with > Audacity

Alternativly don't do any of this, instead
- Run demucs
- Select all required files and drag into an open audacity session
- OR
- Copy the demucs.lof file into the same directory as the new files then open Audacity and select
  > File > open > demucs.lof
