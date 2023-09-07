

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

   # test w/ inverse op
   
   deg2rad(rad2deg(180))
   Out[3]: 180.0

   deg2rad(rad2deg(360))
   Out[4]: 360.0

   deg2rad(rad2deg(0))
   Out[5]: 0.0






