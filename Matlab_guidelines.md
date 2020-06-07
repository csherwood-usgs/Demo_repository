### My guidelines for Matlab scripting

#### Command window
 * `format compact` - reduce white space on output
 * `pwd` - print working directory
 * `dir` or `ls` - list everything in the working directory
 * `what` - list only Matlab-specific files in the current directory
 * `who`, `whos` - list current variable in the workspace. `whos` also reports size
 * `cls` - clear output in command window
 * `clear` - clear all variables in workspace
 * `close all` - close all figure windows
 * `save` - save all variables in workspace to a file called `matlab.mat` (do `help save` to see other options).
 * *uparrow* - recall last command. More *uparrows* recall further. Typing `b *uparrow*` will recall previous commands starting with `b`.
 

#### M files (not `Live Scripts`)
 * Don't use Matlab's `Live Scripts`...they are stored in a proprietary binary format and can only be read in Matlab.
 * Start each script with at least one line with the name and purpose. For example:
 
  ```
  % matlab_guidelines - Pontificate about personal coding quirks
  % more info about the code
  
  x=5 % first exectuable line
  ```
  
  This will allow the command `help matlab_guidlines` to return that info, and any other comments from the top line to the first blank or executable line.
  * Break m-files into sections using the `%% comment on new section` syntax. Space after `%% ` is required. You may need to turn on `sectons 

#### Good coding practices
 * Never lie in comments: no comment is better than a misleading comment.
 * Comments should explain the rationale behind code, not repeat the mechanics.
 * Always indent properly (ctrl-a to highlight all of code, ctrl-i to indent in Matlab editor).
 * Not a fan of camelCase. Use short variable names and document them.
 * Develop some standard variable name conventions. Some of mine:  
 `dn` - a datenum variable or array (I don't like the new datetime object)  
 `ds`, `de` - start date, end date  
 `fn`, `pn` - filename, pathname  
 `i`,`j`,`k`,`m`,`n` - indices (old school). They may not really be integers in Matlab, but are used that way. `l` is useless because it looks like `1`.  
 `h` - water depth, `Hs` - water depth, `T` - wave period  
 
#### Gotchas and debugging
Most common mistakes:
 * typos in filenames
 * evil whitespace in files (you need an editor that will display tabs, carriage returns, linefeeds, and tabs). I use __Atom__ for serious coding, and __TextPad__ because of the `block editing` capability. Lots of people like __Notepad++__, which is free.
 * overwriting a function name with a variable name e.g. `dir = 360.` will clobber the built-in directory command `dir`.
 * missing variables when a script is re-run. Sometimes while building a script, you might refer to a variable that exists in the workspace, but has not been defined in the script. The script runs fine in the current session, but throws an error in the next session or after the workspace has been cleared. The best way to prevent this is to, before you are done developing the script, use `clear`

## Directory (folder) organization

I have a top-level directory called matlab: e.g. C:\matlab
Below this, I have directories with code from others and *general* routines that I use. Here is a suggested structure for the PEP/SSF research group  
C:\matlab 
    \cbrewer  
    \cmocean  
    \cmglib  
    \RPSstuff 
    \CIRN

    

I keep project related work in project folders. I start these folder names with the year, so they will sort chronologically.
