# diffmove

**THIS IS A VERY EARLY TEST SCRIPT. PLAY WITH IT CAREFULLY.  `RCLONE MOVE` IS A POWERFUL COMMAND**

**Usage:** `./diffmove source: destination:`

Using rclone, generate a list of files that are on a source and not on a destination.
Diffmove then moves the files missing from the destination onto the destination from the source.
Files present on both source and destination remain on source.
Files present only on destination are not touched.

Example: ./diffmove source: destination:`

```Before diffmove
Source:       Destination:
file1
file2
file3         file3
file4         file4
              file5

After diffmove
Source:       Destination:
              file1
              file2
file3         file3
file4         file4
              file5```
              
If you wish to only create the list but not execute the move, run `./difflist source: destination:` rather than diffmove.

