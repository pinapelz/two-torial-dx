<img class="header-logo" src="/img/taito/groovecoaster4/logo.webp">
# Game Setup

--8<-- "docs/snippets/common/data_warning.md"

## Preparing data

--8<-- "docs/snippets/common/data_readonly.md"

    The **complete game data** should be approximately **67 GB or larger**.

    Your data structure should look something like: 

    ```
    📂[System]
    📂GwSafeModeDefault
    📂GwCommonShaderf
    📂data
    ▶️game.exe
    📄game.inf
    ▶️NesysService.exe
    ▶️XIO.exe
    ⚙️emxunit.dll
    ⚙️etLib2.dll
    ⚙️ftd2xx.dll
    ⚙️zlib1.dll
    ```
    
    Its possible that your version of the game has `game471.exe` as well. If it exists then use that instead of `game.exe`.
  
    You will also need to obtain `TypeXZEROTemp.dat`

## Installing JConfig

!!! tip ""
    - Download the `iDmacX x86 NESiCA ver 2.0` variant of JConfig
    !!! warning "**You must obtain the correct variant JConfig for the game to launch correctly**"
    - Find `JConfig.exe` and `iDmacDrv32.dll` within the bundled archive, and add both of these to the folder with your game
    ```
    ▶️JConfig.exe
    ⚙️iDmacDrv32.dll
    ```

## Configuring JConfig

!!! tip ""
    - Launch `JConfig` as Administrator (by right clicking and selecting "Run as Administrator")
    - Select `Settings` and on the top right corner select `Load Regedit`
    - Create 3 empty folders (anywhere is fine) and name them: `event`, `log`, and `news` 
    ```
    📂event
    📂log
    📂news
    ```
    > If you have a `D:` its recommended to setup these directories for consistency with how the game works.
    - Input the path of where you created these folders into the corresponding fields in the same format as shown below
    <img src="/img/taito/groovecoaster4/gc471-jconfig-regedit.webp">
    - Then select `Save Regedit` to apply your changes

!!! tip "Configuring Controls"
    - If you are using a controller, on the main menu of `JConfig`, select your controller from the table then the "Joystick Type" (generally DInput either XInput)
    - If you are using a keyboard, then be sure that the "Joystick Type" is set to DInput
    - Map your controls according to the table below. Do this by double-clicking the corresponding row from the right-table.
    
    |   Buttons    |          Key           |
    | :----------: | :--------------------: |
    |   P1 UP      |   Left Booster Up      |
    |   P1 DOWN    |   Left Booster Left    |
    |   P1 LEFT    |   Right Booster Up     |
    |   P1 RIGHT   |   Right Booster Left   |
    |   P2 UP      |   Left Booster Down    |
    |   P2 DOWN    |   Left Booster Right   |
    |   P2 LEFT    |   Right Booster Down   |
    |   P2 RIGHT   |   Right Booster Right  |
    | P1 BUTTON1   |   Left Booster Button  |
    | P2 BUTTON1   |   Right Booster Button |
    
    Your `JConfig` should now look something like the image below:

    <img src="/img/taito/groovecoaster4/gc471-jconfig.webp" width=600px>

!!! tip "Game Configurations"
    - In the game's directory. Navigate to `data/system.cfg` and open it with your text-editor of choice (i.e Notepad)    
    - You will need to add/modify each key within this file to match the ones listed below
    - If a key already exists in a section, simply change its value after `=`, do not add another key.
      ```ini
      WindowMode = 1 
      WindowMode = 2 ; wrong!
      ```
  
      ```
      WindowMode                   = 1 
      WindowSize                   = (720, 1280)
      WindowResize                 = 1
      MouseCorsorDisp              = 0
      CheckDeviceLost              = 0
      IntervalMode                 = 1
      MultiSampleType              = 0
      DebugMode                    = 0
      ShowVersion                  = 0
      
      JudgTimeOffset               = 0
      GameTimeOffset               = 0
      GreatMinTime                 = 32
      SkipMargin                   = 48
      SkipMarginDebug              = 48
      ```
      
!!! tip ""

    Finally copy your `TypeXZEROTemp.dat` to "C:" (the very top-level where the Users folder is)

## Monitor Orientation and Resolution

!!! info "With JConfig installed, and by using the settings above the game can be played in landscape"
    The window of the game will fit to the height of your screen, even in landscape orientation. Alternatively, you can play in portrait and scale the `WindowSize` values up accordingly. 

## Monitor Refresh Rate
!!! tip ""

    The game needs to be ran at 60 FPS or things will break.
    
    ??? tip "If you have a display that supports higher than 60 Hz"                           
        - Set your display to 60 Hz. You may need to make a [custom resolution](https://customresolutionutility.net/).                                                                              
        - If this is unsupported by your monitor, then alternatively you can use [RTSS](https://www.guru3d.com/download/rtss-rivatuner-statistics-server-download


## Setup Locale Remulator (Optional)
!!! info ""
    Groove Coaster 4 expects a Japanese Locale and as such will show grabled characters if your machine's locale doesn't match. "Locale Remulator" can be used to emulate the correct locale.
    
    - Download the latest release of [Locale Remulator](http://github.com/InWILL/Locale_Remulator/releases)
    - Unzip the contents, and run `LRInstaller.exe`, follow the provided prompts to Install and "Restart Windows Explorer"
    - Close `LRInstaller` and launch `LREditor.exe`
    - In the first tab, select `Run in Japanese`
    - Then click `Shortcut` and choose to your `game.exe` or `game471.exe`
    - Click `Save` and a new shortcut will be created in your data's directory. Use this to launch the game.
    

## Disabling Network Adapters
!!! warning "You must disable all secondary network adapters before each play"
    Groove Coaster 4 expects only a single network adapter to be available. If this is not the case the game won't start.
    
    - Open Control Panel and paste `Control Panel\Network and Internet\Network Connections` into the top navigation bar, then hit Enter.
    - You will see a list of your Network Adapters. You must disable all except the one you are using for internet (including Bluetooth).
    - If there are any VPN Adapters you will also need to disable those.

## First launch
!!! tip ""

    If you've followed all instructions correctly, you're ready to launch the game. Ensure the controller you configured in JConfig is connected in.

    Start the game by running `game.exe`/`game471.exe` or the newly made shortcut if you followed the Locale Remulator part.

!!! success "Setup Complete!"

    You're all done! The game should load up properly now.
  
## Connecting to a network
!!! warning "Groove Coaster 4 will only connect to a network through ethernet"
    You must have a wired connection to connect to a network. Other adapters will not work.

??? tip "Local Network (Complex)"

    If you wish to run the game locally, but with the ability to create and save a profile, you can run a server on the same computer you are playing the game on. This server will need to be running before you launch the game, however it can be shut down when you are no longer playing. 
    
    - [GC Local Server](https://github.com/asesidaa/GC-local-server-rewrite) - Download the latest release and follow the instructions in the README
    - You will need to obtain a clean copy of the `Events` files if you wish to run events
    - You will also need to redirect traffic of `NesysService.exe` from Taito to `GC Local Server` (follow the instructions on the GitHub)

??? tip "Remote (Online Network)"

    - Follow the instructions provided by your network
