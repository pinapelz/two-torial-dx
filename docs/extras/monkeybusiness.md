# MonkeyBusiness

## What is MonkeyBusiness?

!!! tip ""

    MonkeyBusiness is a tool that handles online services for BEMANI games by simulating an e-amusement network, enabling features like score saving, profile management, game events and other online functionality.
    
    A list of supported games can be found on the [GitHub page](https://github.com/drmext/MonkeyBusiness).

    It consists of two main components:

    - MonkeyBusiness: The server software itself, supports a wide variety of e-amusement games
    - BouncyTrippy: A WebUI for viewing scores and other operations (limited game support)

## Downloading MonkeyBusiness

!!! tip ""

    - Head to the [MonkeyBusiness GitHub](https://github.com/drmext/MonkeyBusiness) page
    - Click the `Code` button and then choose `Download ZIP`
    - Extract the archive

    You should end up with a structure similar to:

    ```
    📂 MonkeyBusiness-main
    ┣━ 📂 modules
    ┣━ 📂 utils
    ┣━ 📄 .gitignore
    ┣━ 📄 config.py
    ┣━ 📄 core_common.py
    ┣━ ▶️ make_venv_portable.bat
    ┣━ 📄 pyeamu.py
    ┣━ 📄 requirements.txt
    ┣━ ▶️ start.bat
    ┣━ ▶️ start.sh 
    ```

## Installing BouncyTrippy (WebUI)
!!! tip ""
    > The WebUI setup portion of MonkeyBusiness is optional, you may skip it if you don't plan on using the WebUI.
  
    - Head to the [BouncyTrippy GitHub](https://github.com/drmext/BounceTrippy/releases) and download the latest release (regardless of name)
    
    !!! warning "Be sure that you are downloading the built WebUI and **NOT** the Source Code."
    
    - Extract the `webui` folder to the same place where MonkeyBusiness is
    
    Your MonkeyBusiness folder should now look something like this:
  
    ```
    📂 MonkeyBusiness-main
    ┣━ 📂 modules
    ┣━ 📂 utils
    ┣━ 📂 webui
    ┣━ 📄 .gitignore
    ┣━ 📄 config.py
    ┣━ 📄 core_common.py
    ┣━ ▶️ make_venv_portable.bat
    ┣━ 📄 pyeamu.py
    ┣━ 📄 requirements.txt
    ┣━ ▶️ start.bat
    ┣━ ▶️ start.sh 
    ```

## Starting and Configuring MonkeyBusiness

!!! tip ""

    Run the respective start up script for your platform. On Windows this is `start.bat` on Linux `start.sh`. You will need to have Python installed to use MonkeyBusiness (don't worry the start-up script will tell you if its missing)

### Configuring Service URL

!!! tip ""

    To configure the service URL for your BEMANI game:

    - Open `spicecfg.exe`
    - Navigate to the `Options` tab
    - Locate the `EA Service URL` field
    - Enter the Service URL shown in MonkeyBusiness' console output (typically `http://127.0.0.1:8000/core`)

### Importing Metadata 

!!! tip ""
    
    Certain games may require you to import a "mdb" file for the server to work. A list of the games that require this can be found on the [GitHub page](https://github.com/drmext/MonkeyBusiness).
    
    You can obtain the necessary file from your data. The location may differ depending on the game, or you may be provided one through other means. The file should end in `.xml`.
    
    Once you have found the relevant file, head back to where you extracted MonkeyBusiness and open the `modules` folder. Find the correct game, and place the "mdb" file in this folder.
    
    As an example, you can get the SDVX "music_db.xml" file from your data's `contents/data/others` directory. Then you would copy this folder into `modules/sdvx` within your MonkeyBusiness folder.


## Final words

!!! success "Setup Complete!"

    Remember to always make sure MonkeyBusiness is running **before** starting your game!

    If you were following a guide, you can now return to it and proceed with the next steps.

## Help

--8<-- "docs/snippets/common/help.md"
