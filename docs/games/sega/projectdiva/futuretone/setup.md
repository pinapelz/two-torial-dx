<img class="header-logo" src="/img/sega/projectdiva/futuretone/logo.webp">
# Setup

--8<-- "docs/snippets/common/data_warning.md"

--8<-- "docs/snippets/sega/common/data_old.md"


## Preparing data

--8<-- "docs/snippets/sega/common/data_driveletter.md"

--8<-- "docs/snippets/common/data_readonly.md"

--8<-- "docs/snippets/sega/common/data_preparation.md"

    ```
    📂rom
    📄ConfigureMTU.ps1
    📄ResetAdapter.ps1
    ▶️diva.exe
    📝firewall.cfg
    ▶️game.bat
    ⚙️glut32.dll
    ▶️oxGetHwInfo.exe
    ⚙️oxGetHwInfo.ini
    ```

!!! warning ""
    If your data does not have an `amfs` folder, you can still proceed with the guide. However, you may or may not experience issues with connecting to a network.


## Updating data

--8<-- "docs/snippets/sega/common/data_updating.md"


## Installing option data

!!! tip ""

    SEGA games receive content updates through option folders rather than direct game file updates.

    For Project Diva, official options are named `M???`, where `???` represents a sequence of numbers.  
    Community-created options often use letters instead of numbers to differentiate them from official releases.

    After downloading option files, extract them into your game's `Option` folder.
  
    Finally, once you have all your option files. Move the `Option` folder into `App` and rename it to `mdata`

    ```
    📂amfs
    📂App
    ┗━📂mdata
      ┣━📂M215
      ┣━📂M220
      ┣━📂M230
      ┗━ etc.
    ┗━ etc.
    📂AppData
    ```

!!! info "Option numbers don't always follow a sequential pattern<br>It's common to see the numbers jump, for example `M215` then `M220`"

## Installing PD-Loader and segatools

!!! tip ""

    1. Download the latest version of [PD-Loader](github.com/PDModdingCommunity/PD-Loader/releases/tag/latest) and extract the contents of the archive into `App`
    
    2. Download the segatools [PD-Loader plugin](https://files.catbox.moe/eises8.zip) and extract the contents of the archive into `App`
  
    3. Download this corresponding version of [segatools](https://files.catbox.moe/6owt7w.zip) and extract the contents of the archive into `App` (overwriting files when necessary)
    
    **Its imperative that you do these steps in order**
  
## Configuring segatools

!!! info ""    

    You'll need to manually edit `App\segatools.ini` as segatools has no graphical configuration tool.
    
    We recommend using a text editor with syntax highlighting such as [Notepad++](https://notepad-plus-plus.org/).

    The following sections match those found in `segatools.ini` - skip any sections not listed below.

    If a key already exists in a section, simply change its value after `=`, do not add another key.

    ```ini
    [system]
    dipsw1=1
    dipsw1=1 ; WRONG!
    ```

=== "[vfs]"

--8<-- "docs/snippets/sega/common/segatools_relativepaths.md"

    !!! tip ""

        If you've followed our recommended file structure, use these values:

        ```ini
        [vfs]
        amfs=../amfs
        option=mdata
        appdata=../AppData
        ```

        If not, point those to their respective folders.

    ??? tip "If you do not have an `amfs` folder"
  
        Disable the use of `vfs`

        ```ini
        [vfs]
        amfs=.\
        option=.\
        appdata=.\
        enable=0
        ```


=== "[gpio]"

    !!! tip ""
      
        ```ini
        [gpio]
        dipsw1=1
        ```
      
        >If you are NOT using the recommended segatools release, the [gpio] section in segatools has been renamed to [system] on newer versions
  
=== "[gfx]"
    !!! tip ""
        
        Ensure that `[gfx]` is disabled
      
        ```ini
        [gfx]
        enable=0
        ```

## Connecting to a network

--8<-- "docs/snippets/sega/common/network_preamble.md"

--8<-- "docs/snippets/sega/common/network_remote.md"

--8<-- "docs/snippets/sega/common/network_local.md"

## Installing VCRedist & DirectX

--8<-- "docs/snippets/common/setup_vcredist_directx.md"


## Configuring PD-Loader
!!! tip ""

    If you've followed all instructions correctly, you're now finally ready to launch the game!
  
    Start PD-Loader by launching `diva.exe`
    
    - In the `Options` tab, scroll to the bottom and enable `Use divahook.bat/start.bat`
    - In the `Plugins and Patches` tab, enable `segatools.dva`
    
    ** Make sure you press `Apply` to save changes **


## Controllers
!!! tip ""
    Using controllers with PD-Loader is well documented on the <a href="https://github.com/PDModdingCommunity/PD-Loader/wiki/3)+Usage%2C+Modules+(Costumes)%2C+Troubleshooting#controllers)">PD-Loader Wiki</a>

## First launch

--8<-- "docs/snippets/sega/common/service_jp_googlelens.md"

!!! tip ""

    If you've followed all instructions correctly, you're now finally ready to launch the game!
    
    Start the game by opening `diva.exe` (if its not open already), then press `Launch`
  
    Allow the game to load, it may take some time.


--8<-- "docs/snippets/sega/common/success.md"

## Help

--8<-- "docs/snippets/common/help.md"

    PD-Loader is also very well documented. See the <a href="https://github.com/PDModdingCommunity/PD-Loader/wiki/3)-Usage,-Modules-(Costumes),-Troubleshooting#known-issues">Known Issues</a> for potential solutions.
  
    There are also additional resources available on the [Project DIVA Modding 2nd Discord Server](https://discord.gg/projectdiva)
