Very simple task.

# General Idea

Here below is a picture. Revolutionnary.

![[Pasted image 20261121194041.png|354]]

- Green spot is the position (vector "pos") of Le Player.
- Black line, ending in Black spot, represents the direction vector (vector "dir"), so the position of the black dot is pos+dir.
- Blue line represents the full camera plane.
- Vector from Black dot to the right Blue dot represents the vector "plane".\
/!\ These are all vector additions /!\
   - -> position of the right Blue point is pos+dir+plane.
   - -> position of the left blue dot is pos+dir-plane.
 
- Red lines represents some of the rays.
- The direction of these rays is easily calculated out of the camera: it's the sum of the direction vector of the camera, and a part of the plane vector of the camera:
  - For example: the third Red ray goes through the right part of the camera plane at the point about 1/3th of its length. So the direction of this ray is `dir + plane \* (1/3).`
- The two outer lines, are the left and right border of the screen, and the angle between those two lines is called the Field Of Vision or FOV.

## Rotation

Wanna make your vector bend ? Well that's not exacty what we're doing but I tried being funny, and I don't wanna delete the first phrase. Soo we're stuck with it. Nice.

Rotation ! yeahh vector goes *rock sliding noise*
The best idea it to simply get the angle of the vector you wanna rotate and the angle by which you want to rotate it and do some [math magic](https://matthew-brett.github.io/teaching/rotation_2d.html).\
Yeepee !
That should look like sum like that:
![[Pasted image 20261121221915.png]]
B being the new angle, which will be our rotation speed.

Or in pseudo code:
```
double oldDirX = dirX;
dirX = cos(rotSpeed) * dirX - sin(rotSpeed) * dirY;
dirY = sin(rotSpeed) * oldDirX + cos(rotSpeed) * dirY;
```
Or with `cos( -rotSpeed)` to rotate in Le other way.

**/!\ Important Note ! /!\\**
rotSpeed here is in radians/frame, which may cause problems when said frames are irregular.
The player movement speed should probably be in squares/seconds or some way to keep it peasy.
# Implementation


Just do what i said duhh


## To know :

the first part of this page is just a shortened copy and pasted version of [this](https://lodev.org/cgtutor/raycasting.html#Untextured_Raycaster_) web page.