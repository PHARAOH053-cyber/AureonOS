============================================================
                    AUREONOS
                 USER MANUAL
                     v0.1.0
============================================================

AureonOS is an experimental operating system executed
inside Windows through Python.

AureonOS uses a modular architecture that includes:

    - Bootloader
    - Kernel
    - Shell
    - Virtual file system
    - Virtual storage system
    - Applications
    - User interface
    - Themes
    - Event system
    - Timer

AureonOS does not replace Windows. It runs as an
independent layer inside the host operating system.


============================================================
1. REQUIREMENTS
============================================================

To run AureonOS you need:

    - Windows
    - Python 3
    - A complete copy of AureonOS
    - Access to CMD or Windows Terminal

Using a recent version of Python is recommended.


============================================================
2. SYSTEM STRUCTURE
============================================================

The main AureonOS structure is:

AureonOS/
│
├── aureonos.py
├── STARTUP.cmd
│
├── apps/
│   ├── files.py
│   ├── settings.py
│   └── system_info.py
│
├── boot/
│   └── boot.py
│
├── core/
│   ├── config.py
│   ├── kernel.py
│   ├── shell.py
│   └── timer.py
│
├── system/
│   ├── filesystem/
│   ├── processes/
│   ├── services/
│   └── virtualstorage/
│
└── ui/
    ├── desktop.py
    ├── menus.py
    ├── widgets.py
    ├── input/
    ├── themes/
    └── wallpapers/


Each section has a different function within the system.


============================================================
3. STARTING AUREONOS
============================================================

To start AureonOS:

    1. Open CMD or Windows Terminal.
    2. Navigate to the main AureonOS folder.
    3. Run:

        STARTUP

You can also run directly:

        STARTUP.cmd


The boot process is:

    CMD
      |
      v
    STARTUP
      |
      v
    aureonos.py
      |
      v
    boot.py
      |
      v
    kernel.py
      |
      v
    config.py
      |
      v
    desktop.py
      |
      v
    Liquid Glass
      |
      v
    AureonOS Shell


During startup, messages will appear indicating which
components have been loaded successfully.


============================================================
4. AUREONOS SHELL
============================================================

After startup, a prompt similar to this will appear:

    AureonOS:/ >

The text after "AureonOS:" indicates the current location
inside the virtual file system.


Example:

    AureonOS:/ >


After running:

    cd apps


The prompt will change to:

    AureonOS:/apps >


IMPORTANT:

The paths displayed by AureonOS belong to the virtual file
system.

They are not directly Windows file system paths.


============================================================
5. AVAILABLE COMMANDS
============================================================

The currently available commands are:

    help
    clear
    ls
    cd
    pwd
    desktop
    files
    system
    settings
    analysis
    timer
    refresh
    reloadOS
    reboot
    shutdown


Commands are case-insensitive.

For example:

    timer 10:00

    TIMER 10:00

    TiMeR 10:00

are all interpreted as the same command.


============================================================
6. HELP
============================================================

Displays the list of available commands.

Usage:

    help


Example:

    AureonOS:/ > help


============================================================
7. CLEAR
============================================================

Clears the terminal screen.

Usage:

    clear


============================================================
8. LS
============================================================

Displays the contents of the current virtual directory.

Usage:

    ls


Example:

    AureonOS:/ > ls


It may display entries such as:

    apps/
    system/
    users/
    config/


Services are displayed as files:

    desktop.service
    shell.service
    theme.service


============================================================
9. CD
============================================================

Changes the current directory inside the virtual file system.

Usage:

    cd <directory>


Example:

    cd apps


To go back to the previous directory:

    cd ..


To return to the root directory:

    cd /


Example:

    AureonOS:/apps > cd ..
    AureonOS:/ >


Virtual paths can also be used:

    cd /system


============================================================
10. PWD
============================================================

Displays the current virtual location.

Usage:

    pwd


Example:

    AureonOS:/system > pwd

    /system


============================================================
11. DESKTOP
============================================================

Displays the AureonOS desktop again.

Usage:

    desktop


The desktop currently uses the:

    Liquid Glass

theme.

The desktop is a visual representation of the system and
is still under development.


============================================================
12. FILES
============================================================

Opens the file application.

Usage:

    files


Currently, this application displays information about the
file system of the environment where AureonOS is running.

This feature will continue to evolve toward using the
AureonOS virtual file system.


============================================================
13. SYSTEM
============================================================

Displays basic information about the host system.

Usage:

    system


The application can display:

    - Computer name
    - Operating system
    - System version
    - Python version


IMPORTANT:

This information belongs to the host computer.

AureonOS does not yet have an independent kernel capable of
directly controlling hardware.


============================================================
14. SETTINGS
============================================================

Displays the basic AureonOS configuration.

Usage:

    settings


Currently displays information such as:

    - Theme
    - Version


Configuration options will increase in future versions.


============================================================
15. VIRTUAL FILE SYSTEM
============================================================

AureonOS has an independent virtual file system.

The root directory is:

    /


The initial structure contains:

    /
    ├── apps/
    ├── system/
    │   ├── filesystem/
    │   ├── processes/
    │   └── services/
    ├── users/
    │   └── lio/
    └── config/


This system does not directly modify the Windows file system.


============================================================
16. VIRTUAL STORAGE
============================================================

AureonOS includes an experimental virtual storage system.

Its structure is:

    system/
    └── virtualstorage/
        ├── virtualdevices/
        │   ├── port1/
        │   └── port2/
        │
        └── virtualstorageunit/


There are currently two ports:

    port1
    port2


Each port can contain folders and real files inside the
AureonOS structure.


============================================================
17. ANALYZING A PORT
============================================================

To analyze the contents of a virtual device, use:

    analysis port1

or:

    analysis port2


Example:

    AureonOS:/ > analysis port1


AureonOS will display:

    - Port status
    - Contents
    - Folders
    - Files
    - Tree structure


Example:

    AUREON STORAGE ANALYSIS

    Port   : port1
    Status : CONNECTED

    ├── data/
    │   ├── file1.txt
    │   └── file2.txt
    │
    └── config/


If the port is empty:

    Status : EMPTY


If the port does not exist:

    Status : NOT FOUND


If an unknown port is entered:

    Unknown virtual storage port.


Available ports:

    port1
    port2


============================================================
18. TIMER
============================================================

AureonOS includes a built-in timer.

Command:

    timer


The format depends on the desired duration.


MINUTES AND SECONDS:

    TIMER 10:00

Means:

    10 minutes


Also:

    TIMER 1:00

Means:

    1 minute


HOURS, MINUTES AND SECONDS:

    TIMER 1:00:00

Means:

    1 hour


During the timer, something similar to this will appear:

    TIMER [09:59]

    TIMER [09:58]

    TIMER [09:57]


When the timer reaches zero:

    TIMER [00:00]


Then:

    TIMER FINISHED


To cancel the timer:

    Press CTRL + C


AureonOS will display:

    Timer cancelled.


============================================================
19. REFRESH
============================================================

Reloads AureonOS without requiring you to manually close
the terminal.

Usage:

    refresh


The system will execute the main program again.

This is especially useful during development.


============================================================
20. RELOADOS
============================================================

This is another way to reload AureonOS.

Usage:

    reloadOS


This also works:

    reloados


Both commands perform the same function.


============================================================
21. REBOOT
============================================================

Restarts the AureonOS environment and displays the desktop
again.

Usage:

    reboot


Unlike "refresh", this command is intended to simulate a
system reboot.

It does not currently restart Windows or the physical
computer.


============================================================
22. SHUTDOWN
============================================================

Closes AureonOS.

Usage:

    shutdown


The system will display:

    Shutting down AureonOS...


The program will then terminate.


IMPORTANT:

This command only shuts down AureonOS.

It does NOT shut down Windows.


============================================================
23. CTRL + C
============================================================

CTRL + C can be used to interrupt certain operations.

For example, during a timer:

    CTRL + C

will cancel the timer.


In other parts of the system, its behavior may depend on
the operation currently running.


============================================================
24. CURRENT THEME
============================================================

The current AureonOS theme is:

    Liquid Glass


The theme is located at:

    ui/themes/liquid_glass.py


The goal of the theme is to provide a minimalist visual
interface using terminal characters.


============================================================
25. ARCHITECTURE
============================================================

AureonOS is divided into several layers.


BOOT:

    boot/

Handles the initial boot process.


CORE:

    core/

Contains fundamental components:

    - Kernel
    - Shell
    - Configuration
    - Timer


APPS:

    apps/

Contains AureonOS applications.


SYSTEM:

    system/

Contains internal system components:

    - Filesystem
    - Processes
    - Services
    - Virtual Storage


UI:

    ui/

Contains the visual interface:

    - Desktop
    - Menus
    - Widgets
    - Input
    - Themes
    - Wallpapers


============================================================
26. KERNEL
============================================================

The current AureonOS kernel is an experimental kernel
implemented as Python code.

Its current functions include:

    1. Loading the configuration.
    2. Initializing the environment.
    3. Starting the shell.


Current architecture:

    boot.py
        |
        v
    kernel.py
        |
        v
    config.py
        |
        v
    shell.py


The kernel does not yet directly control:

    - CPU
    - RAM
    - GPU
    - Storage
    - Drivers
    - Hardware


AureonOS currently operates in user space.


============================================================
27. COMMON PROBLEMS
============================================================

PROBLEM:
    "python is not recognized as a command"

SOLUTION:

    Make sure Python is installed and added to PATH.


------------------------------------------------------------

PROBLEM:
    AureonOS does not start.

SOLUTION:

    Check that STARTUP.cmd and aureonos.py are located in
    the main AureonOS folder.


------------------------------------------------------------

PROBLEM:
    "Unknown command" appears.

SOLUTION:

    Type:

        help

    to view the available commands.


------------------------------------------------------------

PROBLEM:
    "Directory not found"

SOLUTION:

    Check the path using:

        ls

    You can also return to the root:

        cd /


------------------------------------------------------------

PROBLEM:
    A virtual port appears as NOT FOUND.

SOLUTION:

    Check that the following directory exists:

        system/virtualstorage/virtualdevices/port1

    or:

        system/virtualstorage/virtualdevices/port2


============================================================
28. DEVELOPMENT
============================================================

AureonOS is designed to grow through a modular architecture.

Components can be developed independently.

Future development areas may include:

    - Process system
    - Real AureonOS services
    - Device manager
    - Storage mounting
    - User system
    - Permissions
    - Additional applications
    - Window system
    - Real mouse input
    - Advanced event system
    - Memory management
    - Virtual drivers
    - Package system
    - Advanced configuration
    - Wallpapers
    - Additional themes
    - More


============================================================
29. PROJECT PHILOSOPHY
============================================================

AureonOS is not intended to be just a terminal program.

The goal of the project is to progressively build an
experience that behaves like an operating system:

    BOOT
      ↓
    KERNEL
      ↓
    SERVICES
      ↓
    UI
      ↓
    SHELL
      ↓
    APPS
      ↓
    USER


Although it currently runs inside Windows, AureonOS maintains
its own logical structure and virtual systems.


============================================================
30. QUICK REFERENCE
============================================================

COMMAND                  FUNCTION
------------------------------------------------------------
help                     Show help
clear                    Clear screen
ls                       List virtual directory
cd <path>                Change directory
pwd                      Show current path
desktop                  Show desktop
files                    Open files
system                   Show system information
settings                 Show configuration
analysis port1           Analyze port 1
analysis port2           Analyze port 2
timer 10:00              Start timer
refresh                  Reload AureonOS
reloadOS                 Reload AureonOS
reboot                   Restart environment
shutdown                 Close AureonOS


============================================================
31. EXAMPLE SESSION
============================================================

    AureonOS:/ > help

    AureonOS:/ > ls

    AureonOS:/ > cd system

    AureonOS:/system > pwd

    /system

    AureonOS:/system > cd virtualstorage

    AureonOS:/system/virtualstorage > cd ..

    AureonOS:/system > analysis port1

    AureonOS:/system > timer 1:00

    TIMER [00:59]
    TIMER [00:58]
    TIMER [00:57]

    ...

    TIMER [00:00]

    TIMER FINISHED

    AureonOS:/system > desktop

    AureonOS:/system > refresh


============================================================
                    AUREONOS
                  END OF MANUAL
============================================================

Version: 0.1.0

Status:
    EXPERIMENTAL

Host System:
    Windows

Engine:
    Python

Interface:
    Terminal

Theme:
    Liquid Glass

============================================================
              "THE SYSTEM IS ALIVE."
============================================================
