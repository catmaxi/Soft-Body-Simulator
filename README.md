# Soft-Body-Simulator

## Links
video: https://www.youtube.com/watch?v=1tz_Blu0F6k

video examples:  https://www.youtube.com/playlist?list=PL39Cz8KUgoRkP_1PGYTlOY0G1NgRBYebp


## Run

### Step 1: install the requirements

This simulator uses the Taichi Programming Language so you will need to install that.
Simply run:
```
pip install -r requirements.txt
```
OR
```
pip install taichi
```



### Step 2: running the file
python3 [path to the file to run]




## Files
as you can see in the paper and in the video, there are 2 types of models for soft bodies in this project.

* Simple truss structure based spring mass particle system. (files in the dir grid)
* Pressure model based spring mass particle system. (files in the dir pressure)




## parameters
there are many parameters that you can set so that it does different things:

```python
spring_debug
```
if turned on, will show the spring-mass system else it will show the rendered soft body.

```python
self_collision = False
```
this activates particle-particle collisions


```python
write_image = False
```
If turned on, then will start writing each frame into files.

```python
image_dir = "img/grid/"
```
path to write to 


```python
project_name = "grid"
```
name of the project


```python
width
height
```
width and height of the GUI and of the screen and of the image size.


```python
GROUND = 0.3
```
this sets the y-positon of the ground

```python
ground_damp = 0.4
```
This sets the energy loss ratio of collisions between particles and the ground.

```python
DIM = 2
```
Dimension - keep it to 2 for now


```python
gravity = 5
```
Setting the gravity, viscousDamping to influence the particle motion

```python
viscousDamping = 3
```
viscous damping

```python
useGravity = True
```
Set to true if we wish to have gravity

```python
num_substeps = 40
```
Number of substeps

```python
step_size = 0.005
```
step size


```python
h = step_size / num_substeps
```
Substep size

### grid system

```python
g_rows = 4
```
number of rows in the computed grid.

```python
g_cols = 4
```
number of cols in the computed grid.


```python
start_x = 0.5
start_y = 0.4
```
starting position of the grid created


```python
spring_len_x = 0.02
spring_len_y = 0.02
```
distance between each particle in the grid.

### Particle data
```python
particle_radius = 5
particle_mass = 2
num_particles = g_rows * g_cols
particle_color = 0x9999FF
```

### Pressure Constants
```python
use_pressure_model = True  # set to true to use pressure model
draw_center = True  # Set to true to see center for the triangulation
use_triangulation = True  # Set to true for exact area using triangulation,
draw_bounding_box_flag = False
draw_triangulation_flag = True
or False for simple bounding area
R = 8.314  # Keep constant
N = 1000  # Keep Constant
T = 30  # Keep Constant
scaling_factor = 5e-8  # Vary accordingly
```



## To run an example

to run a grid ased example simply run:
```
python3 grid.py
```

to run a pressure model example simply run:
```
python3 balloon.py
```



The parameters may not all have been perfectly set up already. If you want to test out different scenario and change some of he parameters, make sure to update the other parameters accordingly.


As the spring constant k goest up, we would like to also increase the substep size (either decrease the step size or increase the number of substeps)



## Useful libary code
the file "gf2.py" is a libary for generating "grids" of particle systems or truss structures

the file "bf2.py" is a libary for generating " of particle systems or truss structures



## System Requirements
This simulator has been tested and used on a Windows 10 machine using python 3.8.9.
Please note currently, Taichi does not support python 3.9 so DO NOT EVEN TRY.
For more information about taichi, please visit: https://taichi.graphics/.
the taichi documentation can be found here: https://taichi.readthedocs.io/
and then taichi github page where you can even find a few interesting examples of projects built in taichi: https://github.com/taichi-dev/taichi

Note:

you do need to check out the system requirements for taichi on the taichi github page.



