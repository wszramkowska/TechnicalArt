# Single Layer Water Material

Technical Art

Sid Szramkowska

2106125

## Research

### What sources or references have you identified as relevant to this task?


For this task I will be creating a single layer water material in Unreal. As I did  for previous tasks, I will be looking at Unreal documentation to give me a foundation level of knowledge.

My secondary source will be a video as I find these the most helpful for me. This task is also quite artistic so I think visuals will be key to understanding how materials in Unreal work.


#### Sources

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


### What creative or technical approaches did you use or try, and how did this contribute to the outcome?

- Did you try any new software or approaches? How did the effect development?

<br>

![onhover image description](https://beforesandafters.com/wp-content/uploads/2021/05/Welcome-to-Unreal-Engine-5-Early-Access-11-16-screenshot.png)
*Figure 2. An example of an image as a figure. This image shows where to package your Unreal project!.*

### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- Did you have any issues completing the task? How did you overcome them?

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


ChatGPT (s.d.) At: https://chatgpt.com (Accessed  10/11/2024).

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
