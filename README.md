The code here is what I am using to demucs an audio file selected from my
file manager then open the tracks in Audactiy.

My setup has/requires
- Ubuntu 24.04 KDE using Dolphin file manager (using right click menu to launch process)
- An install of demucs https://github.com/facebookresearch/demucs/tree/main
- Pyenv to separate python environments. Recommend using a discreet pyenv environment
  for this as requires numpy not current numpy2 etc
- Audacity audio application

Initail setup is manual.
- Once pyenv and a suitable python version is installed, install demucs in that environment
- Copy demucs_me.desktop file to ~/.local/share/kservices5/ServiceMenus/
  Edit the line starting with Exec for correct username. Make it executable.
   (a restart may be required to make it visible)
- Copy the mydemucs file into a location in youre path. Eg mine is ~/.local/bin 
  Edit the mydemucs file. Enter correct pyenv info at top, and edit the required outfile location.
  make it executable. 

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
