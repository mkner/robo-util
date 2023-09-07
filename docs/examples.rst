

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

   rad2deg(np.pi)
   Out[1]: 180.0

   deg2rad(180)
   Out[14]: 3.141592653589793

   # test w/ inverse ops
   
   rad2deg(deg2rad(180))
   Out[7]: 180.0

   rad2deg(deg2rad(360))
   Out[8]: 360.0

   deg2rad(rad2deg(deg2rad(0)))
   Out[10]: 0.0









