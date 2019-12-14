In this lecture, you will learn how to install the Java Development Kit.

 * You must have administrator privilege to install the Java Development Kit.
   Without administrator privileges, you cannot install Java Development Kit.
   If you don't have administrator privileges, please contact the administrator
   of your system.
 * On Windows, start the installer by double-clicking the file you downloaded.
   You will be prompted with a dialog asking for permission. Click 'Yes' to continue.
 * For a Linux or Solaris system, use console commands to change to the
   directory you downloaded the file to, and then run the installer.
 * Once you run the installer, you can easily follow the instructions provided
   by the Installation Wizard.

When the Java Development Kit installs, it creates several folders on your disk.
The location of these folders vary depending on your system.

On Windows, you can find it under 'Program Files\Java' on your Windows drive,
which is usally C drive.

Again, the name of the Java Development Kit root folder also varies, depending
on the version of Java you have installed. In my system, it is named 'jdk-11.0.2'
because that's the version that I installed.

Take a look at the subfolders inside the root folder. As you work with
Java, you’ll frequently refer to these folders.

 * bin
   The compiler, the virtual machine, and other Java development tools reside
   in this folder.
 * conf
   In this folder, you will find the configuration files of the Java Virtual Machine.
   You can edit these configurations. I would suggest to you make sure you know
   what you are doing.
 * include
   This folder contains C header files needed to integrate your Java programs
   with programs written in C and C++. This interface is known as Java Native Interface (JNI).
 * lib
   The private implementation details of the runtime system. It includes the
   Java API class library. These files are not intended for external use
   and must not be modified.
 * jmods
   The compiled module definitions.
 * legal
   The copyright and license files for each module.

After you install the Java Development Kit, you need to configure your operating system to find the Java Development Kit tools. To do this, you must set the
*PATH environment variable*.

The `PATH` variable is a list of folders that the operating system uses to
locate executable programs.

In other words, The `PATH` environment variable is a series of directories
separated by semicolons (;)  (on Windows) and colons (:) (on Linux and MacOS).
Your system looks for programs in the PATH directories in order, from left to right.

To set the PATH variable on Windows 10, follow these steps:
 * Copy the location of the `bin` folder in the root of your Java Development Kit.
 * In Search, search for `This PC`.
 * Right click on `This PC` to open a context menu.
 * Click on the `Properties` menu item.
 * Click the `Advanced system settings` link. This will open the `System Properties` 
   dialog.
 * Click `Environment Variables...` to open `Environment Variables` dialog.
 * In the `System variables` section, find the `PATH` environment variable and select it.
 * Click Edit. This will open `Edit environment variable` dialog.
 * Click `New` and paste the path of the Java Development Kit `bin` folder.
 * Click OK.
 * Close all remaining windows by clicking OK.

The new path takes effect after your open a new console window.

Now, let's verify if the Java Development Kit was correctly installed.
Open your console window.

On Windows, click on `Windows + R` and type `cmd`. Press enter to open the command prompt.

On Linux, click `CTRL + ALT + T` to open the terminal window.

On MacOS, press `Command + spacebar` to launch Spotlight and type `Terminal` then double-click the search result.

Once you open the terminal, console, or the command prompt (all of which mean the same), type `java --version` to see the version of the Java Virtual Machine installed
on your system.

If you don't see the version on the console, you have not installed  properly. Revist your steps to make sure you followed the steps correctly.

If you see the version of the Java Virtual Machine, that's it! You have successfully
installed Java Development Kit on your system.