# Animation System

Technical Art

Sid Szramkowska

2106125

## Research

### What sources or references have you identified as relevant to this task?

I have never used the animation system in Unreal, and decided to start off my research with official Unreal documentation. This task seemed particularly difficult as I didn't have much experience with animation in general so I wanted to make sure my research gave me good enough knowledge to get started.

Another source I would use would be a video as I find those most helpful for my learning when trying new things in the Unreal Engine as I can see the full process and follow along. Animation is visual movement so I think a video will be good for showcasing that system. 


#### Sources

##### Unreal Documentation

I looked at the animation system overview documentation (Animation System Overview | Unreal Engine 4.27 Documentation | Epic Developer Community, s.d.) which explained a lot of the key features of the animation system and even had a diagram which explains where certain parts of the animation system are created and edited.


Overview of the UE4 Animation System
Purpose: Provides tools for realistic animation through skeletal and morph-based mesh deformation, enhancing player movement and special moves.
Components: Animation Sequences, Animation Blueprints, Blend Spaces, Skeletal Controls, and State Machines.
Key Concepts and Tools

Skeleton:

Manages bone hierarchy.
Allows multiple Skeletal Meshes to share animations via a single Skeleton.

Skeletal Mesh:

Represents the character's visual appearance.
Modified in the Skeletal Mesh Editor.

Animation Sequences:

Single animations for Skeletal Meshes.
Keyframes specify bone position, rotation, and scale.

Animation Notifications (Notifies):

Events triggered at specific points during Animation Sequences.
Common uses: footsteps, particle effects, and custom game events.
Animation Tools in UE4

Animation Blueprint Editor:

Controls animation logic.
Enables blending, bone control, and frame-by-frame pose definition.

Blend Spaces:

Blend between multiple animations based on two inputs.
Reduces need for hard-coded blending nodes in Animation Blueprints.

Animation Montages:

Complex animation effects (e.g., loops, condition-based switching).
Accessible through Blueprint Visual Scripting or code.

Skeletal Controls:

Direct control over Skeleton bones.
Supports dynamic, procedural animation adjustments (e.g., IK chains, foot alignment).

State Machines:

Manages animation states (e.g., Idle, Movement, Jumping).
Transition rules control blending between states.
Simplifies animation design and visualizes state flow.
Debugging and Visualization Tools

Bone Rendering:

ShowDebug Bones command displays Skeletal Mesh Bones in white lines.
ShowDebugToggleSubCategory 3DBones command for 3D bone view.

Animation Debug Output:

ShowDebug Animation command provides detailed debug information in five sections.
Toggle sections with ShowDebugToggleSubCategory for targeted debugging.

##### Youtube Video Unreal Engine 5 Tutorial - Animation Blueprint Part 2: Blend Spaces

<iframe width="560" height="315" src="https://www.youtube.com/embed/0Ab_MeAh6_k?si=mo3fT7my-kNvJ1FL" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

I found a youtube video explaining how blend spaces work in Unreal. The video showed me how to blend my animations together which would be very useful as I had 3 animations; idle, walk and run. 

- Set up axis (vertical axis is speed)
- Idle helps with acceleration
- Plug blend space into output animation pose
- Update animation and calculate from velocity

I found this video particularly helpful to get my animation correct based on my speed. 

## Implementation

### What was the process of completing the task? What influenced your decision making?

- For this task I used animation from my Alive Below game project where I created a blend space for my zombie character.
- Used the blend space in my enemy blueprint

<iframe src="https://blueprintue.com/render/uk4uthg-/" scrolling="no" allowfullscreen></iframe>

*Animation blueprint event graph*

- I created an attack animation montage for my enemy, in case I wanted a variety of animations for the attack.
- I added a montage notify in my zombie attack montage. This is timed to be where the enemies hand begins to come down, as that is where the player appears to be taking damage.
- In my enemy blueprints I played the animation montage when the player was within attack range. 

<iframe src="https://blueprintue.com/render/muk6va19/" scrolling="no" allowfullscreen></iframe>

*Blueprints for enemy attack animation*


<br>



### What creative or technical approaches did you use or try, and how did this contribute to the outcome?

- I added footstep sounds to my animation blueprint using the play sound notify
- This allowed me to precisely match the footstep sounds to the actual walking/running of the zombie
- I disconnected the top and lower body

<br>



## Outcome



[Enemy animation](https://www.youtube.com/watch?v=Di2K0OgP76Q&ab_channel=WSzramkowska)

<iframe width="560" height="315" src="https://www.youtube.com/embed/Di2K0OgP76Q?si=MK6J8ufW9gO_DBI5" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- It was very easy to avoid the player attack because the enemy would stand still whilst attacking. I did this to prevent an awkward sliding motion.
- To fix this I seperate the torso from the legs so the enemy was still able to attack whilst running.

## Critical Reflection

### What did or did not work well and why?

- The animation works well, I like that it transitions based on the speed of the character as it makes it feel more natural.
- The animations are accurate to the current state of the enemy (idle, chasing, patrolling, attacking).
- I think I could have more variety in animations to make it more interesting.

### What would you do differently next time?

- I would like to try more complex animations where my enemy could cycle through different attacks
- I think it would be interesdting to randomise these animations

## Bibliography

Unreal Engine 5 Tutorial -  Animation Blueprint Part 2: Blend Spaces (2023) At: https://www.youtube.com/watch?v=0Ab_MeAh6_k (Accessed  06/12/2024).

Animation System Overview | Unreal Engine 4.27 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/skeletal-mesh-animation-system-in-unreal-engine (Accessed  15/11/2024).



## Declared Assets

Used to assist in research for Animation System Development Journal:
ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/11/2024).
