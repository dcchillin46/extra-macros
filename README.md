<h1 align="center"> Extra Macros </h1>
  <p align="center"><i>Useful Macros for Common Functions and Tuning </i></p>
    <br>
  <p align="center">Written with a Neptune 4 Pro on <a href="https://github.com/OpenNeptune3D/OpenNept4une">Open Nept4une</a> firmware. However, the macros should be useful for any Klipper printer </p>

<h2 align="left"> Installation:</h2>
If you've installed <a href="https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging">KAMP</a> then it should be fairly familiar. With advice from its author, Kyleisah, I've essentially copied the process.</p>

**1. SSH into your printer.**
</br>
   *  For Neptune 4 owners USER: _mks_ PASSWORD: _makerbase_ (USER: _root_ will break the process as far as I can tell)

**2. Run the following commands in order:**
  ```
   cd ~/
 
   git clone https://github.com/dcchillin46/extra-macros.git
 
   ln -s ~/extra-macros ~/printer_data/config/extra-macros

   cp ~/extra-macros/extra_macros.cfg ~/printer_data/config/extra-macros/extra_macros.cfg
 
  ```
 _This will:_
 - _Change to the home directory (mks for Neptune 4)_
 - _Clone the extra-macros repo_
 - _Create a symbolic link between the clone repository and the printers config folder_
 - _Create a copy of the extra_macros.cfg for local editing that wont invalidate (dirty) the local files_

**3. (Optional) Open moonraker.cfg through SSH or your front end of choice (fluidd, Mainsail, etc) and add:**

```
[update_manager]
channel: dev
refresh_interval: 168
```
_This enables Moonraker Update Manager with a refresh rate of once every 7 days_
</br>
</br>
```
[update_manager extra-macros]
type: git_repo
path: ~/extra-macros
origin: https://github.com/dcchillin46/extra-macros.git
managed_services: klipper
primary_branch: main
```
_This will allow moonraker to handle updating the extra_macros.cfg with any changes pushed to the repo_

<h2>Alternatively:</h2>
1. Download raw extra_macros.cfg from repo </br>
2. Place in ~/printer_data/config
</br>
</br>

*This method will require manual updating*

</br>
</br>

<h5>It's probably pretty evident I'm new to all of this. If you run into any issues with the macros, install process, or updater please let me know and I'll try to refine things as I can.</h5>
