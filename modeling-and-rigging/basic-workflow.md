---
description: My basic workflow after importing the PSD file
---

# Basic Workflow

1. Select all parts and add **standard** ArtMesh to them. I may adjust the ArtMesh to heavy or light, or, customize it by hand as fit when working on the model.
2. Create a Texture Atlas by clicking Command + T on Mac.
3. Set up clipping masks on parts like eyes \(irises clipped to eye whites\).
4. Manually redraw the ArtMesh of parts like eyelashes, eyebrows, closed mouth, so that the ArtMeshes are made up of nice-looking triangles.
5. Set up the deformer hierarchy before setting any parameters. See the page on Deformer Hierarchy for details.
6. \(Optional\) Create two ArtMesh Collision Detection Areas, one on the head and one on the body \(excluding the head\). See the page on ArtMesh Collision Detection for details. It's necessary to recreate the Texture Atlas after this step.
7. Modeling and rigging: Set parameters for the deformers
8. Stress-test the model by turning on the Editor's random motion feature.
9. Set up physics.
10. Animate the model. Sometimes I create an animation scene based on a voice clip. Apply lip-sync from the audio file. Bake animation from physics.
11. Export **moc3, motions.json, physics.json** files.
12. Configure collision detection areas and corresponding motions in Live2D Cubism Viewer. This adds to the **model.json** file.
13. Use the exported model files in downstream applications with SDKs for Web, native, Unity, Ren'Py, etc.



