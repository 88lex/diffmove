# diffmove
**THIS IS A TEST SCRIPT. PLAY WITH IT CAREFULLY.**  

**Usage diffmove:** ```./diffmove source: destination:```    
**Usage diffsets:** ```./diffsets dset.video```        
**Usage difflist:** ```./difflist source: destination:```    

**DIFFMOVE**    
diffmove uses rclone to generate a list of files that are on source but not on the destination remote, and
then **moves** those files from source to the destination remote. 

Files present on both source and destination remain on source.    
Files present only on destination are not touched.

Example: `./diffmove source: destination:`

```Before diffmove
Source:       Destination:
file1
file2
file3         file3
file4         file4
              file5
```

```
After diffmove
Source:       Destination:
              file1
              file2
file3         file3
file4         file4
              file5
```

**DIFFSETS**    
diffsets uses a set file containing any number of source-destination pairs along with diffmove to move files as described above for each pair.

```
#source                     destination
bak:home_movies             gdrive:Media/home_movies
bak:travel_video            gdrive:Media/travel_video
```

**DIFFLIST**    
difflist is a standalone script using `rclone check` to find differences between source and destination rclone remotes.    
difflist generates a flat text file called difflist.txt which contains files that exist on source but not on destination (a one way compare).


