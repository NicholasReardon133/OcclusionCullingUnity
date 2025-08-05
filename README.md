Custom Occlusion Culling in Unity
📖 Overview
This project is an implementation of a custom occlusion culling system within the Unity game engine. The goal is to provide a more flexible and granular approach to camera-based culling than Unity's built-in solution. By leveraging raycasting and custom-modeled occluder meshes, this system determines object visibility, optimizing rendering performance by disabling the renderers of objects that are hidden from the camera's view.

This is particularly useful in scenes with complex, dense geometry where manually defining occlusion areas can be tedious or inefficient. Due to Github file size restriction, I could not push with the models or assets, but the rest of the code base is present in the folder.

🛠️ Tools & Technologies
Game Engine: Unity

3D Modeling: Blender

IDE: Visual Studio Code

💡 Key Concepts & Topics
This project explores several key areas of game development and optimization:

1. Occlusion Culling
The core of the project. Instead of relying solely on Unity's built-in occlusion, this system uses a custom script to dynamically determine which objects are "occluded" (hidden) by other objects. This prevents the GPU from rendering unseen objects, which can significantly improve frame rates in complex scenes.

2. 3D Modeling for Optimization
Simple, low-poly meshes (occluders) were created in Blender. These meshes are not visible in the game but are used by the culling system as simplified representations of complex objects. Using these occluders for visibility calculations is much more performant than using the high-poly visual meshes.

3. Raycasting
The visibility check is performed by casting rays from the camera towards the bounding boxes of objects in the scene. If a ray is intercepted by an occluder mesh before it reaches the target object, that object is considered hidden and its renderer is disabled for that frame. The script manages the frequency and targets of these raycasts to balance accuracy with performance.