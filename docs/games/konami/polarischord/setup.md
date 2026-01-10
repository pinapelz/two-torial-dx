<img class="header-logo" src="/img/konami/polarischord/logo.webp">

# Game Setup

--8<-- "docs/snippets/common/data_warning.md"

## Preparing data

--8<-- "docs/snippets/common/data_readonly.md"

    The **complete game data** should be approximately **22.5 GB**.  
    If your data is significantly smaller, you likely have an update archive instead of the full game data.

    Here's what the expected data structure should look like: 

    ```
    📂game
    📂modules
    📂prop
    📄file.inf
    📄keyring.dat
    ```

--8<-- "docs/snippets/konami/common/data_bad.md"

!!! info "If your data is already up-to-date, you can skip ahead to the [Installing spice2x](#installing-spice2x) section"

## Updating data

!!! info "For a comprehensive list of all game updates in chronological order, visit [BemaniWiki](https://bemaniwiki.com/?%A5%DD%A5%E9%A5%EA%A5%B9%A5%B3%A1%BC%A5%C9)"

!!! danger "Make sure you're using the right update for your current game version"

    Polaris Chord updates have `XIF` and one or two datecodes in their archive names.

    **Single datecode:** Contains one update (e.g., `XIF_NewDateCode.7z`)  
    **Two datecodes:** Updates from the older to newer version (e.g., `XIF-OldDateCode-NewDateCode.rar`)

    In the two-datecode example:
 
    - `OldDateCode` is the older date, the game version required to apply this update
    - `NewDateCode` is the newer date, and is the version you'll arrive at after applying the update

--8<-- "docs/snippets/konami/common/data_update.md"

## Installing spice2x

--8<-- "docs/snippets/konami/common/spice2x64_install.md"
    
    Your game directory should now look like:
  
    ``` hl_lines="6-7"
    📂game
    📂modules
    📂prop
    📄file.inf
    📄keyring.dat
    🌶️spice64.exe
    🌶️spicecfg.exe
    ```

--8<-- "docs/snippets/konami/common/spice2x64_stubs.md"

## Configuring spice2x

--8<-- "docs/snippets/konami/common/spicecfg_preamble.md"

??? warning "spicecfg does not detect my game!"
    This is a common problem due to bad data. You are likely missing the required `prop` files. You will need to obtain clean data or obtain these files yourself.

??? info "I don't own a Polaris Chord controller, but have a touchscreen device"
    You can play using [poalris-touch](http://girlsband.party/polaris-touch.html) and connecting to SpiceAPI. For more info on how to configure this, see the API section below.

=== "Buttons"

--8<-- "docs/snippets/konami/common/spicecfg_buttons.md"

=== "Overlay"

--8<-- "docs/snippets/konami/common/spicecfg_overlay.md"

=== "Lights"

--8<-- "docs/snippets/konami/common/spicecfg_lights.md"

=== "Cards"

--8<-- "docs/snippets/konami/common/spicecfg_cards.md"

=== "Patches"

    ??? warning "spice2x does not support patching Unity games, you should instead use a web-based patcher or use [other Unity modding methods](/extras/unity.md)"

=== "API"

--8<-- "docs/snippets/konami/common/spicecfg_nochange.md"

    ??? info "If you are using `polaris-touch`"
        - In `API TCP Port` enter `1337` (or some other port if its unavailable)
        - Make sure to leave the password section blank
        - Find your PC's IP address (will typically start with `192.168`)
        - On your touchscreen device open [polaris-touch](http://girlsband.party/polaris-touch.html)
        - Enter your IP and the port you set above as `IP:Port`, for example `192.168.1.1:1337`
        
        You will know you've done this correctly if the top of polaris-touch shows `CONNECTED`
        
        *The port will increase by 1 on polaris-touch UI, this is normal and expected*


=== "Options"

--8<-- "docs/snippets/konami/common/spicecfg_options.md"

--8<-- "docs/snippets/konami/common/spicecfg_options_nvprofile.md"

=== "Advanced"

--8<-- "docs/snippets/konami/common/spicecfg_nochange.md"

=== "Development"

--8<-- "docs/snippets/konami/common/spicecfg_nochange.md"

## Configuring audio

!!! info "Check out our general [Audio](/extras/audio.md) guide to understand audio modes better, at least the TL;DR"

!!! tip ""

    - Open `spicecfg.exe`
    - At the very top, click on `Shortcuts` then `Audio Playback Devices`
    - In the popup window, right click on your default audio device, and click on `Properties`
    - Go to the `Advanced` tab

    Then, depending follow instructions for your desired audio mode:

??? tip "Setup for WASAPI Exclusive (default)"

    - Check both boxes under `Exclusive Mode`
    - Open the `Default Format` dropdown
    - Pick the `16 bit, 44100 Hz (CD Quality)` option, click `Apply` then `OK`

??? tip "Setup for WASAPI Shared"

    - Open the `Default Format` dropdown
    - Pick the `16 bit, 48000 Hz (DVD Quality)` option, click `Apply` then `OK`
    - Return to `spicecfg`, go to the `Patches` tab
    - Following the [Unity modding guide](/extras/unity.md) and patch `Shared Mode WASAPI`

??? tip "Setup for ASIO (requires specialized hardware)"

    - Check both boxes under `Exclusive Mode`
    - Open the `Default Format` dropdown
    - Pick the `16 bit, 44100 Hz (CD Quality)` option, click `Apply` then `OK`

## Connecting to a network

--8<-- "docs/snippets/konami/common/setup_network.md"

??? tip "Option 3: Local e-amuse Emulator (MonkeyBusiness)"

    For instructions on setting up MonkeyBusiness, please refer to our [MonkeyBusiness setup guide](/extras/monkeybusiness.md).

    After MonkeyBusiness is setup with the proper plugin for your game:

    - Open `spicecfg.exe` and head to the `Options` tab
    - Under the `Network` category, set your `EA Service URL (-url)` to point to your asphyxia server, typically `http://localhost:8000/core`


## Installing VCRedist & DirectX

--8<-- "docs/snippets/common/setup_vcredist_directx.md"

## Before playing

--8<-- "docs/snippets/common/before_playing.md"
  
## First launch

!!! tip ""

    If you've followed all instructions correctly, you're finally ready to launch the game!

    Run `spice64.exe`, press `Yes` when it asks for elevated privileges.

    The game will go through a series of checks, let it run, if you've done everything properly they'll pass.
  
    You may then get a `CLOCK ERROR`, if this the case. Press your `TEST` key to enter the Service Menu. Simply use the touchscreen buttons to navigate the menu and set and save a time.
    
!!! success "You're all done! The game should load up properly now"

## Help

!!! warning "Something's wrong?"

    Make sure you've followed all steps correctly and also read other relevant guides. See the [troubleshooting](troubleshooting.md) section
