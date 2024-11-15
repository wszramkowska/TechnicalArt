# Physics Door

Technical Art

Sid Szramkowska

2106125

## Research

### What sources or references have you identified as relevant to this task?

I will be looking at Unreal documentation to get a grasp on how physics works within the engine, and the different ways I am able to manipulate it. My task for this week will be to make a physics door so I will be focusing on collision and joints or hinges. Over the course of my project Unreal documentation has always been very reliable for my research and has usually been a great place to start for me.

My other source will be a video tutorial as it helps me narrow down my specific task and I think will give me a great base to then further experiment. 



#### Sources



##### Unreal Documentation

I found various Unreal documentation to do with physics, starting with the general Physics documentation (Physics in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community, s.d.). In Unreal Engine, physics bodies are components used to simulate realistic physical interactions and behavior for objects within a game or interactive experience. Unreal Engine’s physics system, powered by NVIDIA's PhysX or Chaos (in later versions), allows for objects to react to forces like gravity, collisions, and other forces.
I also specifically looked at documentation for collision (Collision Overview | Unreal Engine 4.27 Documentation | Epic Developer Community, s.d.) and constraints (Constraints User Guide | Unreal Engine 4.27 Documentation | Epic Developer Community, s.d.) as I knew I would need these to create my physics door.

1. Physics Bodies and Rigid Bodies
- A physics body is often a part of a rigid body in Unreal Engine, which refers to an object that can move, rotate, and be affected by physical forces without deforming (like a box or a ball).
- These bodies are typically represented by collision shapes (such as spheres, boxes, or custom meshes) that are added to an actor or a skeletal mesh to determine how it should react to physical forces.
2. Physics Assets
- Physics bodies are often used in conjunction with Physics Assets for skeletal meshes, which is a set of rigid bodies and constraints associated with a character or animated object.
- A Physics Asset contains Physics Bodies for each bone or part of the mesh, allowing for interactions like ragdoll effects, joint constraints, and more realistic movement of limbs.
3. Collision and Simulation
- Physics bodies include collision properties, which define how they interact with other objects in the environment.
- You can set properties like mass, linear and angular damping, friction, restitution (bounciness), and simulate responses to forces such as gravity, wind, or player-applied forces.
4. Constraints and Joints
- In Unreal, you can use constraints to control how physics bodies are allowed to move. This can be useful for creating joints or hinges, such as connecting a door to its frame.
- Constraints allow you to specify limits, like rotation angles and motion in specific directions, helping create realistic or stylized interactions between connected physics bodies.
5. Dynamic vs. Static
- Physics bodies can be set to be dynamic (affected by physics forces) or static (immovable and unaffected by physics forces). For example, a rock that falls when hit is dynamic, while the ground is usually static.
6. Common Uses in Unreal Engine
- Characters: Using physics bodies in skeletal meshes to simulate body parts’ motion or add ragdoll effects.
- Vehicles: Creating accurate physics simulations for moving parts and realistic vehicle movement.
- Environmental Interactions: Allowing objects to respond to explosions, collisions, and other in-game forces.
- Physics-based Puzzles: Building objects that move, rotate, or react in ways that players can use to solve puzzles.


Unreal Engine's Physics Bodies give developers tools to make objects feel believable in a game world by handling the heavy lifting for real-world interactions.

The Unreal Documentation has a large amount of information however it is fairly easy to navigate as there are lots of pages dedicated to the various uses, tools and tutorials. They all have an easy to understand title that allowed me to quickly get to the information I needed, since I knew I would need collision and constraints. If I wanted to learn physics from scratch and didn't have a specific goal in mind, I think the documentation would be much too long to read.



##### Youtube Video How to Make a Physics Door in Unreal Engine 5 by Gorka Games

<iframe width="560" height="315" src="https://www.youtube.com/embed/30G-WJ5aMpA?si=W3SUcSvs8BgPEC4o" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

I looked for a short youtube video to explain how to do my task in simple terms, which would allow me to expand on it myself. I found a youtube video by Gorka Games which shows how to make a physics door.
The video explains how to add collision to a static mesh and then uses a physics constraint component in order to operate the door swing.

Although the video did its job, and I was able to successfully make a physics door, I think it is only good for simple projects. If I wanted animation to open the door, I would definitely have to find a different video. It also did not use any blueprints, which I think might have been helpful.



## Implementation

### What was the process of completing the task? What influenced your decision making?

- Added a static mesh, using a door model from the Unreal starter content. This consisted of a door and a door frame.
- Added a box simplified collision to the door so I could enable simulation physics.
- Added Physics Constraint component and changed the angular limits to only allow the swing motion for the door to open. Limited the angle to 90 degrees.
- Moved the pivot to the corner of the door.
- Changed the angular motor to twist and swing so the door would swing back to the frame.
- For a more realistic door opening motion I increased the angular damping.


<br>


### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- Due to the simplicity of the task I didn't really have an difficulties.

## Outcome

[Physics Door Task](https://www.youtube.com/watch?v=ICXiZrI8GDA&ab_channel=WSzramkowska)


<iframe width="560" height="315" src="https://www.youtube.com/embed/ICXiZrI8GDA?si=3lkZS_RTy7MUs0to" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

*Figure 1. Physics Door*

## Critical Reflection

### What did or did not work well and why?

Overall I think the door works well and looks quite realistic. I was pleasantly surprised at how simple this was to make, which has given me a bit of confidence with physics inside the Unreal Engine. I am excited to explore more ways of using these physics and I think it will be very helpful for my project this term.
I think looking at a more complex system could have helped me learn and challenged me a bit more, however when developing video games I still think it is good to have these simple methods and to not overcomplicate things unnecessarily. 

### What would you do differently next time?

- I would like to try this with different types of doors, such as swinging gates, or hatches that might swing vertically rather than horizontally which would need a different pivot.

## Bibliography

Physics in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/physics-in-unreal-engine (Accessed  15/11/2024).

Constraints User Guide | Unreal Engine 4.27 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/constraints-user-guide-in-unreal-engine (Accessed  15/11/2024).

Collision Overview | Unreal Engine 4.27 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/collision-in-unreal-engine---overview (Accessed  15/11/2024).

How to Make a Physics Door in Unreal Engine 5 (s.d.) At: https://www.youtube.com/watch?v=30G-WJ5aMpA (Accessed  15/11/2024).


## Declared Assets

Used to assist in writing Physics Door Development Journal:
ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/11/2024).