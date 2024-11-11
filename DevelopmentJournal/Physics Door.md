# Physics Door

Technical Art

Sid Szramkowska

2106125

## Research

### What sources or references have you identified as relevant to this task?





#### Sources




In Unreal Engine, physics bodies are components used to simulate realistic physical interactions and behavior for objects within a game or interactive experience. Unreal Engine’s physics system, powered by NVIDIA's PhysX or Chaos (in later versions), allows for objects to react to forces like gravity, collisions, and other forces. Here’s a breakdown of what physics bodies are and how they're used:

1. Physics Bodies and Rigid Bodies
A physics body is often a part of a rigid body in Unreal Engine, which refers to an object that can move, rotate, and be affected by physical forces without deforming (like a box or a ball).
These bodies are typically represented by collision shapes (such as spheres, boxes, or custom meshes) that are added to an actor or a skeletal mesh to determine how it should react to physical forces.
2. Physics Assets
Physics bodies are often used in conjunction with Physics Assets for skeletal meshes, which is a set of rigid bodies and constraints associated with a character or animated object.
A Physics Asset contains Physics Bodies for each bone or part of the mesh, allowing for interactions like ragdoll effects, joint constraints, and more realistic movement of limbs.
3. Collision and Simulation
Physics bodies include collision properties, which define how they interact with other objects in the environment.
You can set properties like mass, linear and angular damping, friction, restitution (bounciness), and simulate responses to forces such as gravity, wind, or player-applied forces.
4. Constraints and Joints
In Unreal, you can use constraints to control how physics bodies are allowed to move. This can be useful for creating joints or hinges, such as connecting a door to its frame or making a chain with linked segments.
Constraints allow you to specify limits, like rotation angles and motion in specific directions, helping create realistic or stylized interactions between connected physics bodies.
5. Dynamic vs. Static
Physics bodies can be set to be dynamic (affected by physics forces) or static (immovable and unaffected by physics forces). For example, a rock that falls when hit is dynamic, while the ground is usually static.
6. Common Uses in Unreal Engine
Characters: Using physics bodies in skeletal meshes to simulate body parts’ motion or add ragdoll effects.
Vehicles: Creating accurate physics simulations for moving parts and realistic vehicle movement.
Environmental Interactions: Allowing objects to respond to explosions, collisions, and other in-game forces.
Physics-based Puzzles: Building objects that move, rotate, or react in ways that players can use to solve puzzles.
Practical Example
If you wanted to simulate a table breaking upon impact, you might add physics bodies to each table leg and the tabletop, defining how each part should move when a force (like a player or projectile) collides with it.

Unreal Engine's Physics Bodies give developers tools to make objects feel grounded and believable in a game world by handling the heavy lifting for real-world interactions.








##### Unreal Documentation

Unreal documentation for materials is incredibly vast and seems to have various detailed pages to do with specific materials or their functions. Since I am new to materials in Unreal, so I stuck with the 'Getting Started' section of the Materials documentation (Unreal Engine Materials | Unreal Engine 5.5 Documentation | Epic Developer Community, s.d.). Within 'Getting Started' I used the essential material concepts documentation (Essential Unreal Engine Material Concepts | Unreal Engine 5.5 Documentation | Epic Developer Community, s.d.) to learn some of the basics.

###### Materials
Control the visual appearance of objects by defining surface characteristics like color, reflectivity, roughness, and transparency, which dictate light interaction.

###### Shading Pipeline
Unreal Engine uses shaders (written in HLSL) to determine how each pixel and vertex should render on screen. Users create Materials visually in the Material Editor instead of coding in HLSL.

###### Material Editor
Materials are built using nodes (Material Expressions) that create a shader graph, where inputs connect to the Main Material Node. Properties like Material Domain, Blend Mode, and Shading Model determine the Material's foundational settings.

###### Material Expressions
These nodes perform specific tasks, and by connecting them, users effectively write shader code without needing direct HLSL input. Expressions allow customization of data flow and control of aspects like color, opacity, and roughness.

###### Material Instances and Functions
Material Instances allow quick variations of a base Material, ideal for assets that need similar textures with different colors or characteristics.
Material Functions package commonly used node networks, enabling reusable elements across different Materials.

###### Data Types and Flow
Unreal Engine utilizes RGBA (float4) color values, with data types like float, float2, float3, and float4 to control Material expressions. Knowing data types is essential for creating complex Materials.

The Unreal documentation is very detailed and the documentation I looked at was just one of many available. The inclusion of screenshots was helpful to orientate myself within the Engine and actually apply the information given to me. There are also multiple links to other documentation so anything I didn't understand, I was able to easily catch up on.

Although there was a lot of information provided, I found myself getting lost quite quickly. I don't think this documentation is necessarily meant to be read all in one go, but maybe more as a point of reference when you have a specific problem or question. Otherwise it is just too much.

##### Youtube Video How to Make a Simple Water Material in Unreal Engine 5 by Gorka Games

<iframe width="560" height="315" src="https://www.youtube.com/embed/o6f7n4UhYq0?si=wV8LVcLNL8CPqWPW" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

After reading the Unreal documentation I didn't really feel any more confident about materials so I found a simple youtube tutorial for a water material. It was only 4 minutes long which I thought was good since I had already spent so much time reading documentation.
 

- Used single layer water shading model.
- Plugged parameters into refraction, opacity and base colour to create a simple water material.
- Waternormal in texture sample for waves. 
- Panner node to make the waves move.
- Waves moving on both axis for a realistic effect. 
- Texture sample nodes connected by a blend node and plugged into normal. 

The video used starter content which made it eaxsy to follow along. All blueprints were shown and Gorka Games explains what the various nodes do which gave me the confidence to create my own water material. 

For a simple material this video is very good, however it's not an in depth tutorial. This did not really bother me as I was more interested in the basics, and wanted to do further exploration on my own within the Unreal Engine.


## Implementation

### What was the process of completing the task? What influenced your decision making?

- This was another task where I used pair programming, this time with me as the navigator. It was helpful to experience pair programming from another perspective.
- We wanted to create a semi-realistic water material. 

<br>

*Figure 1. Blueprints for Water Material 1*

<iframe src="https://blueprintue.com/render/gipcqyu7/" scrolling="no" allowfullscreen></iframe>

- For our base colour we wanted to do a gradient to make the middle of the water seem deeper. To achieve this we used Lerp to connect our lighter blue, darker blue, and radialgradientexponential node. The gradient node created a circular gradient.
- For our waves, we created them using a texcoord node. We moved them using panner and time nodes.
- We used the Fresnel node to make our material reflect light differently based on the viewing angle. This gave the water a more realistic, dynamic effect, rather than being the same from all angles. 
- For extra noise we used a Perlin noise texture sample. Again, this just gives the water a bit more of a realistic look. 

*Figure 2. Blueprints for Water Material 2*

<iframe src="https://blueprintue.com/render/seb5yad-/" scrolling="no" allowfullscreen></iframe>

- Our first attempt at a water material ended up being slightly more complex, so we had another go to create a simple single layer water material.
- We used the singlelayerwater shading model.
- We plugged our green and pink colours into the single layer water material node.
- For the waves we used a water texture sample from the starter content.
- We added a noise texture sample to make the material a bit more interesting.

Our second water material was definitely much easier and quicker to make however, visually, I prefer our first water material.



### What creative or technical approaches did you use or try, and how did this contribute to the outcome?

- We tried to create a gradient to give the water more depth. Although it's not as obvious visually, it was still a useful skill to learn.



### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- We struggled to make the waves realistic. At first they were quite plain even though we had added noise. To help this we used a NormalFromHeightmap node which then gave our desired effect. This node converts a height map texture into a normal map. 

## Outcome

[Single Layer Water Material Task](https://www.youtube.com/watch?v=egKXXhncoOs&ab_channel=WSzramkowska)


<iframe width="560" height="315" src="https://www.youtube.com/embed/egKXXhncoOs?si=Hgm2wNvu7-tS5Hmp" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


## Critical Reflection

### What did or did not work well and why?

- Creating a material from scratch is quite difficult. Although I think the water materials look good, they may not be realistic in terms of the way the waves move. To help this I could look at water in real life, or videos of water and try replicate those movements.
- However overall I am happy with these materials as a first go. I like the waves moving in different directions, I think it really gives the water life. 

### What would you do differently next time?

- In the future I could try create materials other than water. This would allow for more experimentation with things such as emission or metallic materials. 
- It would also be interesting to add reflections. 

## Bibliography

Unreal Engine Materials | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-materials (Accessed  10/11/2024).


Essential Unreal Engine Material Concepts | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/essential-unreal-engine-material-concepts (Accessed  10/11/2024).

How to Make a Simple Water Material in Unreal Engine 5 (2023) At: https://www.youtube.com/watch?v=o6f7n4UhYq0 (Accessed  10/11/2024).

## Declared Assets


ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/11/2024).