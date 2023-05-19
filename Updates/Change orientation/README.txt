Change the orientation
We are trying two different approaches:

1]

To change the orientation of the samples we rotate the mesh used to draw the image.
Using a 2D rotation matrix:
RotMatrix = np.array([[np.cos(RotRad),  np.sin(RotRad)],
                      [-np.sin(RotRad), np.cos(RotRad)]])
We randomly chose the rotation angle.
After this we inject the simulated SMOs using the PSF itself.

2]

Another attempt we made is to add a certain offset in each occurence of the delta_RA and delta_DEC offset.




