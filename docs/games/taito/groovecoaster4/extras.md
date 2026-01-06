<img class="header-logo" src="/img/taito/groovecoaster4/logo.webp">
# Extras

## Changing the game's language

!!! tip ""
    
    Changing the game's language requires changing values in Windows Registry Editor (regedit)
  
    !!! warning "**You should run the game at least once before doing this**"
  
    - Press `WIN + R` and type in `regedit`, then hit OK
    - Navigate to `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\TAITO\TYPEX`
    - Right click on the right-side panel and select `New` -> `Binary Value`
    - Enter code for the language you want
  
      Code | Language
      ------ | ------
      00 00 00 00   | GROOVE COASTER (Japanese)
      01 00 00 00   | RHYTHM INVADERS (English)
      02 00 00 00  | GROOVE COASTER (English)
    
    - The next time you launch the game you may get a backup error. This can be safely ignored
