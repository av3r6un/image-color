# image-color
getting average color from image

```python
from PIL import Image
import numpy as np
import time

def detect_average_color(image_name):
  start_t = time.time()
  img = Image.open(image_name)
  img_array = np.array(img)
  average_color = np.mean(img_array, axis=(0, 1))
  average_color = average_color.astype(int)
  rgb = f'rgb({average_color[0]}, {average_color[1]}, {average_color[2]})'
  hexed = '#{0:02X}{1:02X}{2:02X}'.format(average_color[0], average_color[1], average_color[2])
  end_t = time.time()
  print(f'{round(end_t - start_t, 1)}s')
  return rgb, hexed
```
