1. Add the path and executable as a post-processing script in orca slicer
  - c:\slow.print.test.exe;
2. Slice your model
3. Analyze your print to determine layer times to determine when long layers print times become fast
4. Slide to that layer and add custom gcode "; pm220.start 80" where 80 is the speed the printer is to operate.
5. Slide to the layer you want to revert back to 100 speed and add "; pm220.stop 100"
6. Reslice your model
  - This will recalculate the feed rate between the layers you have choosen. If no stop command is found, it defaults to 8 layers
7. Export and review your gcode before printing.

You can disable post-processing by either removing the post-processing script or add -noprocess to the end of the command
**c:\slow.print.test.exe -noprocess;
