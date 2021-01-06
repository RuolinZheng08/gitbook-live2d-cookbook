---
description: >-
  Live2D Cubism has an official Photoshop script for cleaning up the drawing for
  modeling. However, we have to do some manual work if we are using drawing apps
  other than Photoshop.
---

# Import PSD Files

The most important feature Photoshop provides is **Autocrop**. This ensures that all model component layers are compact and have no empty pixels. Many free drawing apps like Medibang, ibis Paint, or, GIMP, don't have this feature. However, we may achieve the same effect using the command line tool **imagemagick**.

```text
# if you haven't installed homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# use homebrew to install imagemagick
brew install imagemagick
```

We can use **imagemagick** from the command line to extract each layer of our PSD file as a TIFF image, trim the empty pixels from each TIFF image, and stack the TIFF images as a layered PSD file. The ordering of the layers might have changed during the process.

```text
convert live2d.psd tiff/img_%d.tiff
convert tiff/*.tiff -trim trimmed/img_%d.tiff
convert trimmed/*.tiff live2d_trimmed.psd
```

