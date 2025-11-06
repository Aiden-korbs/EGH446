#Cameras #Vision #Models

The **pinhole camera model** is the most common classical model used in robotics and computer vision.

* It assumes that all camera rays pass through a single point, the **optical centre** (`Oc`).
* It also assumes a linear relationship between the image point's position and the direction of the associated camera ray.
* In its simplest form, light rays from an object pass through a small hole (the pinhole) to form an **inverted image** on the image plane.

## Camera Obscura
* The earliest cameras were room-sized pinhole cameras called **camera obscuras** (Latin for "dark room").
* A user would walk into the room and see an upside-down projection of the outside world on the far wall.
* In the 5th century BCE, the philosopher Mo Jing in ancient China mentioned the effect of an inverted image forming through a pinhole.

## Thin Lens Model
* A pinhole camera is an idealization of a thin lens as the aperture shrinks to zero.
* In a real camera, a lens is used. A non-inverted "virtual" image is formed on the image plane, which is at a distance `f` (the focal length) in front of the camera's origin.
* By convention, the optical axis of the camera is the z-axis.