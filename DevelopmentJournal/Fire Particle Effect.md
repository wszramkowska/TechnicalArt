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

After reading the Unreal documentation I wanted to get straight into creating my effect and I thought the easiest way to learn would be a tutorial. I watched this youtube video by Motion Dreams and then tried to create my own fire based on what I had learned. To make things simpler, the video provided chapters which included the different emitters within the system. The emitters I wanted to create for my fire were flames, smoke, embers and a glow which would cast onto the ground. 

###### Flames
-







```Markdown
# Example Documentation

I wanted to create an emitter which takes advantage of spread and focus, which was a technique I learned from a previous assignment where the spatialisation of an object changes depending on distance. I also wanted to work specifically with a `Spline Component` to encapsulate the entire ship with an “Ocean Emitter”. This led me to read the Unreal Blueprints API References and Wwise 3D Positioning documentation (Unreal Engine Blueprint API Reference | Unreal Engine 5.4 Documentation | Epic Developer Community, s.d., AudioKinetic Inc, s.d.).

I found a Blueprint node called “Find Location Closest to World Location" which returns a `Vector3` on the spline position closest to another `Vector3`, I believe this can help move the emitter towards the player(Finding time of given results from (Find Location Closest to World Location) from Splines - Programming & Scripting / Blueprint, 2023).

I found the Unreal documentation clear and easy to navigate, however it was much harder to find specific nodes unless you are familiar with the naming conventions used by Unreal, such as “World Location” and the API documentation is separated from the property references. The Wwise documentation on the other hand is much easier to navigate as they have core topics such as “Using Sounds and Motion to Enhance Gameplay” and examples of how they can be applied, which the unreal documentation lacked. 

# Example Game Source

Just Cause 3 is an action-adventure game developed by Avalanche Studios, it features a mechanic where the player can navigate the open world with the use of a parachute and a wingsuit(Just Cause 3, 2015).

The wind becomes more prominent in the mix and its volume and speed is based on the player's velocity when using the wingsuit or parachute. It is not too overwhelming during action sequences to ensure audio responses can be clearly heard.

I found their implementation and choice great for the context of their narrative and game mechanics. However, for the sequences featured in the assignment, it is more “cinematic” allowing for a different approach for the mix and can be “exaggerated” to drive its narrative function.


```

## Implementation

### What was the process of completing the task? What influenced your decision making?

- What was the process of completing the task at hand? Did you do any initial planning?
- Did you receive any feedback from users, peers or lecturers? How did you react to it?
- I used pair programming for this task, similairly to last week but this time I was the navigator which gave me a new perspective. I was now able to better understand both roles within pair programming.

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

![onhover image description](https://beforesandafters.com/wp-content/uploads/2021/05/Welcome-to-Unreal-Engine-5-Early-Access-11-16-screenshot.png)
*Figure 2. An example of an image as a figure. This image shows where to package your Unreal project!.*

### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- I struggled to make my fire glow. To fix this I added a value and multiplied it with the texture sample, connecting the node to the emissive colour.

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

- Are there any new approaches, methodologies or different software that you wish to incorporate if you have another chance?
- Is there another aspect you believe should have been the focus?

## Bibliography

- Please use the [harvard referencing convention](https://mylibrary.uca.ac.uk/referencing).

Video game development (2024) In: Wikipedia. At: https://en.wikipedia.org/w/index.php?title=Video_game_development&oldid=1240603537 (Accessed  03/09/2024).

## Declared Assets

- Please use the [harvard referencing convention](https://mylibrary.uca.ac.uk/referencing).

Infinity Blade: Adversaries in Epic Content - UE Marketplace (s.d.) At: https://www.unrealengine.com/marketplace/en-US/product/infinity-blade-enemies (Accessed  09/09/2024).

---

```Markdown
# General Tips

- Use plenty of images and videos to demonstrate your point. You can embed YouTube tutorials, your own recordings, etc.
- Always reference! Even documentation, tutorials and anything you used for your assignment. Use an inline reference for the sentence and a bibliography reference at the end.
- Word count is not important, you can also chose to use bullet points. As long as it is clear and readable, the format your decide to use can be flexible.
- You are free to use AI but please ensure you have made a note in the declared assets, for example if you have a script called Test.cs , you should note that AI was used to in the creation of this script. You can use a bullet point list for each asset used like:

The following assets were created or modified with the use of GPT 4o:
- Test.cs
- AnotherScript.cs
- Development Journal.html

```