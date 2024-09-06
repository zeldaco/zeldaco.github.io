---
layout: project
type: project
image: img/222.PNG
title: "Sakura Particle Animations"
date: 2024
published: true
labels:
  - Maya
  - Animation
  - Python
  - 3D Modeling
summary: "Developed 3D models and python scripts to create particle animations within Maya software."
---

<div class="text-center p-4">
  <img width="300px" src="../img/222.PNG" class="img-thumbnail" >
  <img width="300px" src="../img/333.PNG" class="img-thumbnail" >
  <img width="300px" src="../img/1111.PNG" class="img-thumbnail" >
</div>


# About the Project


I used Maya to develop particle systems to create a story of a cat rowing down a river. I developed three particle systems to animate sakura petals falling, the wake of the boat, and a water splash. **I learned how to manage scenes and keyframes, develop unique materials, work with shaders and lighting to render the project.**


I started by modeling all of the different assets, making sure to organize the project so that it would be easy to animate and move specific parts of the models, such as the cats head. Then I worked on the three particle scripts while implementing them into the scene in the right position and frame. 


Here is some code that illustrates how the petal particle system functions: 

```cpp

    def updateParticle(self, force):
        if self.updateLife():  # Updates the life and checks if still alive
            self.updateVel(force)  # Update velocity based on forces
            self.updatePos()  # Update position based on new velocity

        # Handle collisions before further updates
        if self.pos[1] <= GROUND_LEVEL:
            self.handleGroundCollision()  # Adjust position and stop movement if needed

        # Only update rotation if still rotating (not collided)
        if self.rotating:
            self.updateRotation()
        
        self.updateScale()
        self.updateColor()
        self.updateNode()  # Apply position, rotation, and other transformations to the Maya node
                
    def updateRotation(self):
        # Update the rotation if the particle is still spinning
        self.rotation = tuple((current + change for current, change in zip(self.rotation, self.spin)))
        self.applyRotation()
        if self.rotating:
            currentRotation = cmds.getAttr(self.node + ".rotateZ")  # Rotate around Z-axis for spinning
            newRotation = currentRotation + self.rotationSpeed
            cmds.setAttr(self.node + ".rotateZ", newRotation)
            
    def applyRotation(self):
        # Apply the current rotation to the Maya node
        cmds.rotate(self.rotation[0], self.rotation[1], self.rotation[2], self.node)

    def handleGroundCollision(self):
        self.vel = (0, 0, 0)  # Stop downward movement
        self.pos = (self.pos[0], GROUND_LEVEL, self.pos[2])  # Correct position to be exactly on ground level
        self.rotating = False  # Optional: Stop rotation
        self.testForCollision = False  # Prevent further collision checks if needed
        setNodeVisibility(self.node, True)  # Ensure visibility is on if the particle is meant to be visible
        self.updateNode()  # Apply the new position and other transformations immediately

# Make Sakura Test -----------------------------------------------------------------------------------------------------------------

def makeSakura():
    emitter = Emitter(startFrame=1, duration=300, numParticlesPerFrame=3, minLife=40,
                      maxLife=110,
                      size=1,
                      shapeType="custom",
                      minPos=(-500, 500, -500), maxPos=(500, 500, 500),
                      minVel=(-0.02, -0.5, -0.2), maxVel=(0.2, -1, 0.2))
    
    print("Creating particle system...")
    pSystem = ParticleSystem(name="sakuraSystem")
    print("Adding emitter...")
    pSystem.addEmitter(emitter)
    print("Adding forces...")
    pSystem.addForceField(GravityForce(strength=0.08))
    pSystem.addForceField(WindForce(dir=(0.005, 0, 0.05)))
    pSystem.addForceField(WriggleForce(strength=0.05))
    return pSystem

cmds.file("CustomShape.ma", i=True, namespace="imported")
endFrame = 300
setTimelineEndFrame(endFrame)
sakuraSystem = makeSakura()
sakuraSystem.run(frames=300)
```
# Takeaways

I learned how to organize particle classes and structures in Maya, manage scenes, and explore new possibilities codeing can bring to animation. While working on the project, I faced many software issues when it came to rendering the frames. In the future, I would love to go back and slow down some of the particle systems and scenes so that there is more time to appreciate the particle system animations.  
