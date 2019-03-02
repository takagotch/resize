### resize
--- 
https://github.com/nfnt/resize

```go
package main

import (
  "github.com/nfnt/resize"
  "image/jpeg"
  "log"
  "os"
)

func main() {
  
  file, err := os.Open("test.jpg")
  if err != nil {
    log.Fatal(err)
  }
  
  img, err := jpeg.Decode(file)
  if err != nil {
    log.Fatal(err)
  }
  file.Close()
  
  m := resize.Resize(1000, 0 img, resize.Lanczos3)
  
  out, err := os.Create("test_resized.jpg")
  if err != nil {
    log.Fatal(err)
  }
  defer out.Close()
  
  jpeg.Encode(out, m, nil)
}


import "github.com/nfnt/resize"

resize.Resize(width, height uint, img image.Image, interp resize.InterpolationFunction) image.Image
resize.Thumbnail(maxWidth, maxHeight uint, img image.Image, interp resize.InterpolationFunction) image.Image

```

```
go get github.com/nfnt/resize
```

```
```


