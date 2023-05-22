Change the speed

To arbitrarily change the speed of the SMOs in the animations, I use a parameter called speed_factor.
Speed_factor is an integer.
°Passing 2,3, etc.. as value, we discard an occurrence from both delta RA and delta DEC arrays every speed_factor times.

Example:*

delta_RA=

       |----------------|--------------|-----------------|----------------|
delta_ra[0]=10     delta_ra[1]=11   delta_ra[2]=12    delta_ra[3]=13   delta_ra[4]=14

speed_factor = 2

RESULT =

       |----------------|----------------|
delta_ra[0]=10     delta_ra[1]=12    delta_ra[2]=14

the same for the delta DEC array

*The RA and DEC values only, for example, have no physical meaning.

°Passing -2,-3, etc... as value, we add an occurrence in both delta RA and delta DEC arrays every speed_factor times. We compute the "off" variable in this way:
       abs(delta_RA[i+1] - delta_RA[i])/abs(speed_factor).
Then, we add the "off" variable to build a new coordinate:
       delta_RA[i] + off*t, where t  is t=0,1,2,... to (abs(speed_factor)-1). 

Example:*

delta_RA=

       |----------------|--------------|
delta_ra[0]=10     delta_ra[1]=12   delta_ra[2]=14   

speed_factor = -2

RESULT =

       |----------------|--------------|-----------------|----------------|
delta_ra[0]=10      delta_ra[1]=11   delta_ra[2]=12    delta_ra[3]=13   delta_ra[4]=14

*The RA and DEC values only for example, have no physical meaning.
