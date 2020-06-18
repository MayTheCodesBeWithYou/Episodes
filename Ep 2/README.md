# Episode 2: Using Sublime Text to Run C++ Codes

- How to Run C++ Program in Sublime Text in your system.
	
### Part 1 Downloading the Required Files: 

- Download your suited compiler (MinGW in our case) and **Sublime Text** from their official sites

### Part 2 Configuring your Compiler:

- Step 1: Copy the path of bin folder of GCC compiler. In my case it looks like **C:\MingGW\bin** It may be different in your case
- Step 2: Now Open your control Panel and go to **System and Security -> System** and select **Advanced system settings**
- Step 3: From the opened Dailog box click on **Environment variables** and choose **Path** from the **System Variables**
- Step 4: Edit that  variable and add a semi colon(;) following the path of your compiler.
- Step 5: Click **OK** to save all settings

### Part 3 Configuring Sublime text:
	
- Step 1: Open Sublime Text and go to **Tools -> Build System -> New Build System** and paste the following lines
```
{
	"shell_cmd": "g++ \"${file}\" -o \"${file_path}/${file_base_name}\"",
	"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
	"working_dir": "${file_path}",
	"selector": "source.c, source.c++",
			 
	"variants":
	[
		{
			"name": "Run",
			"shell_cmd": "g++ \"${file}\" -o \"${file_path}/${file_base_name}\" && \"${file_path}/${file_base_name}\""
		}
	]
}
```
- Step 2: Press **Ctrl + s** to save the build system and name it as **MyBS or MyC++**
- Step 3: Go to **Tools -> Command Pallette** and search for **Install Package**
- Step 4: In Install Package download **Terminal** to quick open your command promt by clicking **Ctrl + Shift + t**


