
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
 	               TRAP (Test Risk Assessment Program)
               Issued: January 2000,  Last Updated:  October 10, 2022
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
	   Copyright (C) 2000-2022 Texas A&M Transportation Institute
			      All Rights Reserved
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 

            This document provides late-breaking or other information
                     that supplements the TRAP documentation.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
Contents 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
1. Installing TRAP
2. Upgrading TRAP
3. User's Manual
4. NHTSA, FHWA, and CEN auxillary programs:
5. Uninstalling TRAP
6. Trademarks

7.  Version 2.1 changes
8.  Version 2.1.1 changes
9.  Version 2.2 changes
10. Version 2.3 changes
11. Version 2.3.2 changes
12. Version 2.3.3 changes
13. Version 2.3.4 changes
14. Version 2.3.5 changes
15. Version 2.3.6 changes
16. Version 2.3.7 changes
17. Version 2.3.8 changes
18. Version 2.3.9 changes
19. Version 2.3.10 changes
20. Version 2.3.11 changes
21. Version 2.4.1 changes
22. Version 2.4.2 changes
23. Version 2.5.1 changes
24. Version 2.5.2 changes

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
1. Installing TRAP
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
Run Setup.exe from the install disk.  The install program will prompt you
to choose a location for the program. It will also create an icon in the
Start menu.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
2. Upgrading TRAP
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
Please UNINSTALL the previous version of TRAP before installing a new version.
See section 5.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
3. User's Manual
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
The user's manual for TRAP and the Programmer's Guide are included in 
Microsoft Word 97 format (Manual.doc, ProgrammersGuide.doc respectively). 
They are installed in the main TRAP directory (C:\Program Files\Trap by default).



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
4. NHTSA, FHWA, and CEN auxillary programs:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
Note:  An auxilary program, the NHTSA program, must be installed in a 
directory named \ENTREE.  By default, this directory will be created on
the drive that also has the Windows installation. For example, if Windows
is installed on C:, the NHTSA program will be installed in C:\ENTREE.  
Two other auxilary programs are installed, however they are placed in
subdirectories of the TRAP install directory.

A line is also added to your autoexec.bat file:
	
	SET SMVARS=C:\ENTREE\SMVARSC.BIN

If you do not use the NHTSA program, you may remove this line from 
autoexec.bat.  If you are running NT, you may also set this environment
variable in the System Settings under Control Panels.

If you use the NHTSA program, DO NOT move it or delete the files--they
must be in the ENTREE directory.  If you are low on drive space on your
Windows drive, you may move it to another disk, but it MUST remain in the
\ENTREE directory.

It is not recommended that you move the NHTSA program.
In order for TRAP to find the NHTSA program if you move it, you must alter
registry entries. Back up your registry before modifying it.

Create a new text file on your desktop. Using notepad, copy the 
following lines to that file:


	REGEDIT4

	[HKEY_LOCAL_MACHINE\SOFTWARE\TTI\TRAP]
	"EXTERN_APP_PATH_NHTSA"="C:\\ENTREE"

Instead of 'C:\' place the new drive letter for the NHTSA program.
Example: If you move it to D:\ENTREE, the 3rd line of the file would be:

	"EXTERN_APP_PATH_NHTSA"="D:\\ENTREE"

Save this text file as entree.reg, and close the file.  Double-click on
the file's icon on the desktop.  A dialog should say that the information
has been successfully entered into the registry.  You must also modify the
line in the autoexec.bat file to reflect the new drive path.  For example,
change it to read the following if you moved the files to the D drive:

	SET SMVARS=D:\ENTREE\SMVARSC.BIN

Restart Windows in order for your changes to have effect.



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
5. Uninstalling TRAP
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
Launch the "Add/Remove Programs" icon from the Control Panel and select 
TRAP from the list of applications that can be removed.



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
6. Trademarks
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
Windows is a a registered trademark of Microsoft.



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
7. Version 2.1 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Tables now copy to clipboard in tab delimited format for easier use in
  external packages (Excel)

- New option to allow input data to be filtered using CFC 180Hz filter
  before data is used in calculations.  Selectable on both acceleration data
  and angular velocity data.

- New plot curves for CFC 180 filtered data

- New ability to edit axis labels on plots

- Corrected method for showing 10 and 50 msec averaged data on plots and in 
  tables.  No longer shows averaged data points prior to the middle of the 
  averaging interval.  (e.g., The first 50 msec averaged data point will be
  at least 25 msec past the start of the data since it needs 25 msec of data 
  before and after the point to have a valid average.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
8. Version 2.1.1 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Added "Velocity" column to "X Acceleration at CG" table.

- Minor changes to icons.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
9. Version 2.2 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Added option to store raw data in .TRP file

- Allow for missing X or Y data

- Show long pathnames in file entry with tool tips.

- Add Test Number to autogenerated graph annotations.

- Add Velocity to "Y Acceleration at CG" table

- Save/restore app window location when program started.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
10. Version 2.3.1 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 

- Corrected an error in the THIV calculation. The calculation of head Y 
  velocity was using the X position array (adGroundDeltaPosX) instead of the 
  X velocity array (adGroundDeltaVelX) as part of the calculation. The 
  corrected equation is now: 
  HeadVelY[i] =  GroundDeltaVelX[i] * sin(dYawAngle) - GroundDeltaVelY[i] * cos(dYawAngle) - HeadPosX[i] * dYawRate
							 
- The program no longer crashes when attempting to generate graphs when an 
  HP printer was set as the default printer. This was accomplished up using 
  an updated version of the graphing library.

- Improved speed of copying tabular data to the clipboard

- Graphs will save settings after they are closed.

- Graph settings are now saved in .TRP files.

- Tables can now be exported to .csv format from the File Menu.

- In the data input windows, altered the display of filenames so that the 
  filename itself can be read (right-aligned instead of left-aligned text 
  within the box).

- Toned down the Missing Data popup

- Added support for changing data input unit labels. (E.G. test inertial 
  mass, gross inertial mass) can now have their unit label changed. Unit 
  converion is not performed: the unit dropdown changes the unit label that 
  will be displayed in the test summary report.

- Updated the development environment and installer to Visual Studio 2005.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
11. Version 2.3.2 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Graphs now correctly display X and Y zero lines.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
12. Version 2.3.3 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- X and Y Accelation at CG tables now correctly calculates and displays 
  velocity in the velocity units the user has chosen for impact speed.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
13. Version 2.3.4 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
-ASI computation Changed to use Butterworth filetred data (previous code to 
 use sliding window averaging was removed) per reference spec: EN 1317-1-2010 (E)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
14. Version 2.3.5 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
-a new field to specify start time as a signed number (msec) for the first 
data point is added to allow data files with pre zero data to use with 
Butterworth filter per reference spec: EN 1317-1-2010 (E). 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
15. Version 2.3.6 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Fix timing display for results that did not take start time into account. 
  This includes Occupant Risk Factors, and Max Roll, Pitch, and Yaw Angles 
  on the Test Summary Report; OIV time on graphs; Roll, Pitch, and Yaw Angles 
  tables and graphs; and Roll, Pitch and Yaw Rates tables and graphs. 
  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
16. Version 2.3.7 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Changed all computations to look only at data at time zero and later. 
- Change plots, tables to only display data for time zero and later.
- ASI computation now passes all acceleration data through a filter rather than 
  just at time zero and later, and ASI computation is only performed at time 
  zero and later.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
17. Version 2.3.8 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Fixed a crash that occurs when the CFC 180hz filters are selected
- Changed the ASI buttersworth filter algorithm to match SAE J211-1

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
18. Version 2.3.9 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Fixed a crash that occurs when acceleration is selected for input but Roll, 
  Pitch and Yaw are not.
  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
19. Version 2.3.10 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Fixed error message that displays when start time is specified and 
  acceleration is selected for input but Roll, Pitch and Yaw are not.
  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
20. Version 2.3.11 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
-Fix for printing test report on Vista and later systems on some printers

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
21. Version 2.4.1 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Added support for using a single, composite file for all the data inputs
- New Input Dialog when using composite files
- Changed the Graph legends to prevent overflow text
- Added multiple speed/velocity values to always show km/h and mph

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
22. Version 2.4.2 Changes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Updated the Y Angle and Y Rate graphs to convert Radians input to Degrees
- Minor UI changes

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
23. Version 2.5.1 Changes  July 20, 2022
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Added "TERMS and CONDITIONS" page with statements.
- Added ability to invert Input Data when using Individual input file types as well as Composite.
- Added ability to input positive and/or negative values of "Start time in mili-seconds".
- Fixed Various Bugs (Preservation of Data Input Values when changing file types, etc).
- Rearranged Angular Input Data areas for more intuitive use (Roll, Pitch, Yaw).
- Added ability to use independent Input Data Rates for each data type.
- Minor Improvements to integrated Graphics Package.
- NOTE: On Settings Tab, ignore units of "Hz" for "Filter input data to CFC 180".

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
24. Version 2.5.2 Changes    October 10, 2022
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
- Deleted units of "Hz" for "Filter input data to CFC 180"

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 















