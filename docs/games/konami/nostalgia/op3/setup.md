<img class="header-logo" src="/img/konami/nostalgia/op3/logo.webp">
# Game Setup

--8<-- "docs/snippets/common/data_warning.md"

## Preparing data

--8<-- "docs/snippets/common/data_readonly.md"

    The **complete game data** should be approximately **9.4 GB**.  
    If your data is significantly smaller, you likely have an update archive instead of the full game data.

    Here's what the expected data structure should look like: 

    ```
    📂data
    📂data_op2
    📂data_op3
    📂dev
    📂ext
    📂modules
    📂prop
    ```

--8<-- "docs/snippets/konami/common/data_bad.md"

!!! info "If your data is already up-to-date, you can skip ahead to the [Installing spice2x](#installing-spice2x) section"

## Updating data

!!! info "For a comprehensive list of all game updates in chronological order, visit [BemaniWiki](https://bemaniwiki.com/?%A5%CE%A5%B9%A5%BF%A5%EB%A5%B8%A5%A2+Op.3)"

!!! danger "Make sure you're using the right update for your current game version"

    NOSTALGIA updates have `PAN` and one or two datecodes in their archive names.

    **Single datecode:** Contains one update (e.g., `PAN_NewDateCode.7z`)  
    **Two datecodes:** Updates from the older to newer version (e.g., `PAN-OldDateCode-NewDateCode.rar`)

    In the two-datecode example:
 
    - `OldDateCode` is the older date, the game version required to apply this update
    - `NewDateCode` is the newer date, and is the version you'll arrive at after applying the update

--8<-- "docs/snippets/konami/common/data_update.md"

## Installing spice2x

--8<-- "docs/snippets/konami/common/spice2x64_install.md"

    ``` hl_lines="6-7"
    📂data
    📂dev
    📂ext
    📂modules
    📂prop
    🌶️spice64.exe
    🌶️spicecfg.exe
    ```

--8<-- "docs/snippets/konami/common/spice2x64_stubs.md"

## Configuring spice2x

--8<-- "docs/snippets/konami/common/spicecfg_preamble.md"

=== "Buttons"

--8<-- "docs/snippets/konami/common/spicecfg_buttons.md"

> If your controller or MIDI keyboard supports velocity-sensitive input, be sure to configure them as analog.
> Instructions for different input types are provided in spice2x

=== "Overlay"

--8<-- "docs/snippets/konami/common/spicecfg_overlay.md"

=== "Lights"

--8<-- "docs/snippets/konami/common/spicecfg_lights.md"

=== "Cards"

--8<-- "docs/snippets/konami/common/spicecfg_cards.md"

=== "Patches"

--8<-- "docs/snippets/konami/common/spicecfg_patches.md"

=== "API"

--8<-- "docs/snippets/konami/common/spicecfg_nochange.md"

=== "Options"

--8<-- "docs/snippets/konami/common/spicecfg_options.md"

--8<-- "docs/snippets/konami/common/spicecfg_options_nvprofile.md"

=== "Advanced"

--8<-- "docs/snippets/konami/common/spicecfg_nochange.md"

=== "Development"

--8<-- "docs/snippets/konami/common/spicecfg_nochange.md"

## Configuring audio

--8<-- "docs/snippets/konami/common/setup_audio.md"

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
  
    You will first be forced into a the `TEST MENU`. You can use the on-screen touch buttons to navigate.

    <img src="/img/konami/nostalgia/common/2.webp">

    A series of arrows will show pointing to some of the menu options asking you to confirm the details.
    
    First clear the alerts of `SOUND OPTIONS`, `GAME OPTIONS`, `COIN OPTIONS`, `ECOMODE OPTIONS`, and `NETWORK OPTIONS`, by entering their submenu and then immideately exiting. You may do this in any order.
    
    Afterwards, enter the `CLOCK` submenu, and set a time using the touch screen. Then `SAVE AND EXIT`
  
    <img src="/img/konami/nostalgia/common/3.webp">
    
    Finally, enter the `VIRTUAL COIN` submenu, and select `OPERATION SETTINGS`
  
    <img src="/img/konami/nostalgia/common/4.webp">
    
    On this screen, select `TAX RATE SETTING`, and then immideately choose `SAVE AND EXIT`.
    
    Do the same thing to clear the notifications from `PATTERN 1`, `PATTERN 2`, and `PATTERN 3`. Enter the submenu, and immideately `SAVE AND EXIT`.
    
    <img src="/img/konami/nostalgia/common/5.webp">
    
    Once all the notifications have been cleared, return to the main test menu.
    
    Now the `GAME MODE` option should no longer be grayed out. Select it, and the game should start.


!!! success "You're all done! The game should load up properly now"

## Help

--8<-- "docs/snippets/common/help.md"
