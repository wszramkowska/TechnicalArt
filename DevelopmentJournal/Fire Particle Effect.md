# Fire Particle Effect

Technical Art

Sid Szramkowska

2106125

## Research

### What sources or references have you identified as relevant to this task?



For this task I will be creating a fire particle effect using Niagara. As it is a primary tool for VFX within the Unreal Engine I looked to the official documentation.

 I thought it would also be good to find a video tutorial as I have never worked with Niagara or emitters. This would give me a good base which I can then mess around with to achieve my own effects.




#### Sources

##### Unreal Documentation

- An opening paragraph about the source stating the author, developer or organisation, this paragraph should explain the source's influence, credentials, critical reception, awards, reputation or any issues with the source. For example, if the source is not reputable. If the source is a game, the issues that occurred during development or if had a poor launch.
- List the aspects analysed in reference to the current task.
- An ending paragraph stating what you enjoyed or disliked, what you agreed with or not agree with.

When looking at Unreal documentation I found there was actually quite a lot of information about Niagara (Niagara Overview | Unreal Engine 4.27 Documentation | Epic Developer Community, s.d.). I mainly looked at the core Niagara Components and the available templates, but there was also a section on Niagara Paradigms which was an interesting read and something I could potentially use in the future.

###### Systems
- Niagara Systems contain multiple emitters.
- You can essentially layer emitters for one effect. For example my fire system will be made up of flames, smoke and embers.

###### Emitters
- Niagara emitters are containers for modules.
- Key modules in emitters nodes inclue: Emitter Settings, Emitter Spawn, Emitter Update, Particle Spawn, Particle Update, Add Event Handler, Render (Niagara Editor UI Reference | Unreal Engine 4.27 Documentation | Epic Developer Community, s.d.). You can use these to change various things about your effects such as speed, size, colour, spawn rates etc.
- You can run the simulation on CPU or GPU.

###### Modules
- Modules can be seen as the building blocks for particle effects.
- Control aspects such as particle movement, colour, size, velocity etc.
- Modules can work independently or stack with others for various effects.

###### Parameters
- An abstraction of data in a Niagara simulation.
- Types of parameters include:
    - Primitive - Numerical values like integers or floats
    - Enum - Selection from a list of fixed name values. You can choose one at a time like a drop down list.
    - Struct - A combination of primitives and enums.
    - Data Interfaces - Provides data from external sources (other parts of Unreal Engine or outside applications.)
- You can add a custom parameter module to an emitter.

Niagara has templates for commonly used base effects. This will be useful when making my fire effect as the templates include some modules already, meaning I won't have to start from scratch. I think this will also accelerate my learning as I can get straight into experimenting with the modules and seeing how each one changes the effect.

The Unreal documentation provides a lot of guidance on using Niagara. There is various documentation depending on what you are looking for, I mostly used the overview but there is documentation on editor UI, key concepts and systems and emitter modules. All of this, whilst detailed, can be overwhelming for someone who has never used Niagara and therefore I think is most helpful as a reference whilst creating my fire effect. Once I have started my task it will be easier to know the relevant bits of information to look for. 

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
- 

<br>

```csharp
using UnityEngine;
public class HelloWorld : MonoBehaviour 
{
    public void Start() 
    {
        Debug.Log("Hello World!");
    }
}
```
*Figure 1. An example of using a script as a figure. This script has a `Start()` method!*

### What creative or technical approaches did you use or try, and how did this contribute to the outcome?

- Did you try any new software or approaches? How did the effect development?

<br>



### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- I struggled to make my fire glow. To fix this I added a value and multiplied it with the texture sample, connecting the node to the emissive colour. This wasn't shown in the youtube video I watched (Fire Simulation FX in Unreal Engine Niagara | in 12 minutes, 2023) so I had to figure it out myself.

## Outcome

Here you can put links required for delivery of the task, ensure they are properly labelled appropriately and the links function. The required components can vary between tasks, you can find a definative list in the Assessment Information. Images and code snippets can be embedded and annotated if appropriate.

- [Example Video Link](https://www.youtube.com/watch?v=dQw4w9WgXcQ&ab_channel=RickAstley)
- [Example Repo Link](https://github.com/githubtraining/hellogitworld)
- [Example Build Link](https://samperson.itch.io/desktop-goose)

<iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ?si=C4v0qHaYuEISAC01" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

*Figure 3. An example of an embedded video using a HTML code snippet.*

<iframe frameborder="0" src="https://itch.io/embed/2374819" width="552" height="167"><a href="https://bitboyb.itch.io/nephilim-resurrection">Nephilim Resurrection (BETA) by bitboyb</a></iframe>

*Figure 4. An example of a itch.io widget*

## Critical Reflection

### What did or did not work well and why?

- What did not work well? What parts of the assignment that you felt did not fit the brief or ended up being lacklustre.
- What did you think went very well? Were there any specific aspects you thought were very good?

### What would you do differently next time?

- I wanted to create a semi-realistic fire effect which I think I managed to achieve, however I think it would also be interesting to experiment with different stylisations. For example a more cartoon-like fire effect. 
- I  could also try to create an effect without using a template to further my knowledge, although I don't think it is a necessary skill for me as a developer.

## Bibliography

Niagara Overview | Unreal Engine 4.27 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/overview-of-niagara-effects-for-unreal-engine (Accessed  27/10/2024).

Niagara Editor UI Reference | Unreal Engine 4.27 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/editor-ui-reference-for-niagara-effects-in-unreal-engine (Accessed  27/10/2024).

Fire Simulation FX in Unreal Engine Niagara | in 12 minutes (2023) At: https://www.youtube.com/watch?v=q8avHL7syC4 (Accessed  27/10/2024).


