#Cameras #Vision #Data

Cameras capture color using different models. The most common is **RGB** (Red, Green, Blue).

* The RGB model is based on a Cartesian coordinate system, creating a "color cube."
* Black is at the origin (0, 0, 0) and White is at the opposite corner (1, 1, 1).
* The line connecting black and white represents the **Gray scale**.

## Data Size
The amount of data a camera produces is a major consideration.

* **Example**: An 8-bit per channel color image
* Each pixel has 8 bits for Red, 8 for Green, and 8 for Blue (24 bits total).
* Number of colors = $2^8 \times 2^8 \times 2^8 = 256^3 = 16,777,216$ colors.

* **Bandwidth Calculation**:
* For a `1024 x 768` image at 8-bits per channel:
    `Size = 1024 (W) × 768 (H) × 3 (channels) × 8 (bits)` = `~2.36 MB per image`
* If streaming at 20 frames per second (fps):
    `Data Rate = 2.36 MB/image × 20 images/sec` = **`47.2 MB/sec`**