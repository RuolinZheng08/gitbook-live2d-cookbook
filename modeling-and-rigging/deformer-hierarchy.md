---
description: The recommended deformer hierarchy structure of a full-body model.
---

# Deformer Hierarchy

The following deformers are warp deformers by default unless labeled explicitly as rotation deformers.

```text
- Leg L Rotation
- Leg R Rotation
- Body Z
  - Body Y
    - Breath
      - Face Rotation
      - Body X
      - Arm L Rotation
      - Arm R Rotation
```

Inside **Face Rotation**, each part should be wrapped inside its own warp deformer with parameters **Angle X, Y** set. For example:

```text
- Face Rotation
  - Hair Front XY
  - Hair Side XY
  - Hair Back XY
  - Eye L XY
  - Eye R XY
  - ...
```

Parts on which physics \(swinging motion\) may be applied, like hair and accessories, should nest the warp deformer for physics \(which sets parameters like **Hair Front**\) inside the one that controls parameters **Angle X,** **Y.**

Hence the above expands to:

```text
- Face Rotation
  - Hair Front XY
    - Hair Front Swing
  - Hair Side XY
    - Hair Side Swing
  - Hair Back XY
    - Hair Back Swing
  - Eye L XY
  - Eye R XY
  - ...
```

## Miscellaneous Notes about Deformers

* Deformers won't be effective without an Artmesh.
* To adjust the deformer without affecting the old down the command key on Mac and 
* Use a square \(2x2, 3x3\) Beizer division warp deformer for square body parts like eyes or face; Use a 3x2 one for wide ones like front bangs; Use a 2x3 one for long ones like long side bangs or long back hair.
* 
