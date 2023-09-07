

Example
-------

.. |robo-utils
.. |**********

|

For example:


| Use rad/deg conversion functions and the classic 
| arctan2 method to bound angles to +/- 180 degrees
|

.. code-block:: python

   import numpy as np
   from math import sin, cos
   from roboutils import rad2deg, deg2rad

.. code-block:: python

   def boundTo180(angle): 
    
     # input: angle in degrees
     # output: bounded angle in (+/-) 180 degrees (pi radians)

     # typical condensed python-style
     return(rad2deg(np.arctan2( sin(deg2rad(angle)) ,cos(deg2rad(angle)))))


.. code-block:: python

   # as expected

   boundTo180(179)
   Out[7]: 179.0

   boundTo180(180)
   Out[8]: 180.0

   # by keeping within 180 deg bounds (pi radians)
   # function sees crossing the 180 deg boundary 
   # in normal trig counter-clockwise direction for 
   # positive angle rotations as approaching from the
   # other direction as -179 deg (clockwise)

   boundTo180(181)
   Out[9]: -179.0

   # same with 180+90 ( = 270)

   boundTo180(180+90)
   Out[10]: -90.000000000...


.. code-block:: python

   # the usual
 
   rad2deg(np.pi)
   Out[1]: 180.0

   deg2rad(180)
   Out[2]: 3.141592653589793

   # test w/ inverse ops
   
   rad2deg(deg2rad(180))
   Out[7]: 180.0

   rad2deg(deg2rad(360))
   Out[8]: 360.0

   deg2rad(rad2deg(deg2rad(0)))
   Out[10]: 0.0









