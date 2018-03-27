# owl
image annotation app

### Notes

1. Before starting, copy params.py.example to params.py under annotate,
   and modify that file to suit your needs.
2. Usually "images" is a link to the directory which holds your images.
   When images are large, one usually keep two directories with the same
   filenames but different resolutions.  Point symbolic link "images" to
   the small version when you do import & annotation.  After annotation
   is done, symbolic link "images" to the full version and do
   `./manage.py export db`.
3. To avoid copying a large db from local annotation side to server side. After annotation, just copy "db.sqlite3" to owl directory on your destination. 
   Make sure you have the same "images" (image file names must be the same, but you can keep different resolution) there. Then do `./manage.py export db`
   
   

### Start annotation
  1. `./rebuild.sh`
  2. `./run.sh`   
  3. Go to http://localhost:8005/annotate/ to do annotation.   
  4. After annotation, do:   
     `./manage.py export db`


#### Dumping bounding box
1. ./dump.py >dumped_out_annotation.txt
2. Column1 : image, Column 4: x, Column 6: y, Column 8: height, Column 10: width
