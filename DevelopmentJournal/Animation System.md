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




##### Youtube Video Fire Simulation FX in Unreal Engine Niagara | in 12 minutes by Motion Dreams

<iframe width="560" height="315" src="https://www.youtube.com/embed/q8avHL7syC4?si=0RI2MJx4VxcJB63_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

After reading the Unreal documentation I wanted to get straight into creating my effect and I thought the easiest way to learn would be a tutorial. I watched this youtube video by Motion Dreams and then tried to create my own fire based on what I had learned. To make things simpler, the video provided chapters which included the different emitters within the system. The emitters I wanted to create for my fire were flames, smoke, embers and a glow which would cast onto the ground, so I tried to pay extra attention for those chapters in the video.

One of the first things this video covers is how to actually create a Niagara system and select a template. Motion dreams edits a lot of modules, changing things like; spawn rate, life time, sprite size, drag, noise and velocity. 

One thing that stood out to me was unchecking or deleting gravity force which would stop my particles from dropping and give me a flame effect. 

Another important setting for me was the Sprite renderer where I could add a material from the starter content which looked like fire. Using the Sub UVAnimation module I could animate that material. 

The video also taught me how to use the 'color from curve' setting which gives you a colour ramp so you can add multiple colours and choose how they are blended.Top markers on the ramp control the colour, whilst the bottom markers control opacity. This will be valuable when trying to recreate the colour of flames, which blend yellows, oranges and reds.

I found this video to be a great learning tool. It gave me a base to work from, where I could play around with the modules to create my own fire effect. All of the information was up to date and worked with my version of Unreal.


## Implementation

### What was the process of completing the task? What influenced your decision making?

- For this task I created a fire particle effect using Niagara.
- I created 3 emitters; flames, smoke and embers.
- Gave the fire a glowing effect.


###### Flames
- I used the fountain emitter template as a base for my flames.
- Changed various settings within 'initirialize particle' module such as; lifetime, uniform sprite. 
- Changed velocity module settings.
- Turned off gravity to make the flame go up.
- Added curl noise force module to give a flame flickering effect.
- Changed material texture to fire_subuv.
- Used colour from curve in the colour module, picked reds, oranges and yellows to blend. 

###### Smoke
- Used my flame emitter as a base.
- Changed material texture to smoke_subuv.
- Changed colour to just black.
- Changed alpha to make the smoke more transparent.
- Increased sprite size, velocity and lifetime to make the smoke bigger than the fire, and last longer.
- I also changed the sim target to use the gpu for this simulation.

###### Embers
- Used the fountain template as a base.
- Made the particles small using uniform sprite size.
- I copy and pasted the colour module from my flame emitter to match the embers to the flames.


After creating my semi realistic fire particle I had a go at making a more simplistic stylised version. I was able to apply many of the skills I learned and mess around with parameters. Although not as detailed, I really like how it looks and can see it working well for a stylised game.

<br>



### What creative or technical approaches did you use or try, and how did this contribute to the outcome?

- To make my fire more realistic I added a glow that would come off it and cast to its surroundings (ground, walls etc.)
- To do this I added a Light Renderer module.

<br>



### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- I struggled to make my fire glow. To fix this I added a value and multiplied it with the texture sample, connecting the node to the emissive colour. This wasn't shown in the youtube video I watched (Fire Simulation FX in Unreal Engine Niagara | in 12 minutes, 2023) so I had to figure it out myself.

## Outcome



[Fire Particle System](https://www.youtube.com/watch?v=TQfRk6fm998&ab_channel=WSzramkowska)


<iframe width="560" height="315" src="https://www.youtube.com/embed/TQfRk6fm998?si=CakYgXliBS5EyVxl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

*Figure 1. Fire Particle Effect*



## Critical Reflection

### What did or did not work well and why?

- I thought the task was very successful. I liked the visuals of my fire effects.
- I layered multiple emitters to create a semi-realistic fire effect.
- I used various modules and edited multiple parameters to achieve my fire effect.
- I created two versions, a simplistic stylised fire and a semi-realistic fire. This helped better my understanding of the capabilities of the Niagara System.
- There are still many modules I haven't used which would take time and practice to learn.

### What would you do differently next time?

- I  could try to create an effect without using a template to further my knowledge, although I don't think it is a necessary skill for me as a developer.
- I could also add more emitters for a more complex fire system. For example heat distortion.
- I would also like to try creating effects other than fire.

## Bibliography

Niagara Overview | Unreal Engine 4.27 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/overview-of-niagara-effects-for-unreal-engine (Accessed  27/10/2024).

Niagara Editor UI Reference | Unreal Engine 4.27 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/editor-ui-reference-for-niagara-effects-in-unreal-engine (Accessed  27/10/2024).

Fire Simulation FX in Unreal Engine Niagara | in 12 minutes (2023) At: https://www.youtube.com/watch?v=q8avHL7syC4 (Accessed  27/10/2024).

## Declared Assets

Used to assist in research for Animation System Development Journal:
ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/11/2024).
