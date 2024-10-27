# Linear Interpolation

Technical Art

Sid Szramkowska

2106125

## Research

### What sources or references have you identified as relevant to this task?


For my research I started off with Unreal Documentation as that is the engine I am using, and I have previously used lerp in Unity so it will be good to compare in Unreal.

I also like to include a more visual source which helps me personally understand and absorb the information more easily, although I have to be careful to make sure the source is reliable and up to date. More specifically I would like to find a video which explains how to use the Lerp node in blueprints.



#### Sources

##### Unreal Documentation


My task consisted of using the Lerp node to blend between two values so I wanted to research Lerp and how it works within Unreal. Although I didn't find a dedicated documentation to Lerp, I found a document about Math Material Expressions which had a section on Linear Interpolation (Math Material Expressions in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community, s.d.).

The documentation does quite a good job at explaining Lerp in a fairly simple way, saying the Lerp expression blends two input values based on a third 'mask' value which controls the mix between the two inputs. When the alpha value is 0.0 only the first input is shown, and when the alpha value is 1.0 only the second input is shown. Values between 0.0 and 1.0 create a blend of the two inputs. 

I found the Unreal documentation very helpful despite it being quite short, it was to the point and explained how Lerp works. It also included a screenshot of Blueprints which showed the Lerp node and how to use it within your material which could help me with my task for the week.

##### Youtube Video Linear Interpolate or Lerp Node EXPLAINED! Unreal Engine Materials by Hoj Dee

<iframe width="560" height="315" src="https://www.youtube.com/embed/tBib8qQxd1M?si=Y__kkT24sTDc5uMP" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

I found this video by Hoj Dee which explained what Lerp was, similair to the Unreal Documentation, but went into further detail about how to use it. According to the video Lerp blends between two values based on a third value thats used as a mask.

- Input values A and B can be anything: constant, scalar constant 2 vector, constant 3 vector, constant 4 vector, texture samples. Make sure to lerp between inputs with the same number of channels.
- Alpha input (mask) defines the blend of A and B inputs. If Alpha is 0.0 the A input is shown, if alpha is 1.0 the B input is shown. Values between 0.0 and 1.0 create a blend of the two inputs with values below 0.5 being weighted towards the A input and values from 0.5 becoming weighted towards the B input.
- In texture samples the black parts have a value of 0 (where the first input will be) and the white parts have a value of 1 (where the second input will be). Shades of grey will be values between white and black and therefore create a blend of the two inputs.
- You should always clamp the alpha values between 0.0 and 1.0 to avoid extrapolating. You can use the saturate node for this. Clamping will clamp any value below 0 to 0 and any value above 1 to 1.

This video was incredibly helpful, especially as I don't really have any experience with the Unreal Engine. Hoj Dee explains how to get each node and even provides the keyboard shortcuts for them. When using other nodes such as Clamp or Component Mask to showcase the Lerp node, he provides cards which link you to videos that explain those nodes. There are also captions for general keyboard shortcuts used in blueprints such as 'ctrl D' for duplicate. In addition to the blueprints, Hoj Dee also provides diagrams to support his knowledge. At the end of the video there was a number of examples to show how you can change your material's brightness, roughness and how to animate textures using Lerp and Panner nodes. 


```Markdown
# Example Documentation




# Example Game Source

Just Cause 3 is an action-adventure game developed by Avalanche Studios, it features a mechanic where the player can navigate the open world with the use of a parachute and a wingsuit(Just Cause 3, 2015).

The wind becomes more prominent in the mix and its volume and speed is based on the player's velocity when using the wingsuit or parachute. It is not too overwhelming during action sequences to ensure audio responses can be clearly heard.

I found their implementation and choice great for the context of their narrative and game mechanics. However, for the sequences featured in the assignment, it is more “cinematic” allowing for a different approach for the mix and can be “exaggerated” to drive its narrative function.


```

## Implementation

### What was the process of completing the task? What influenced your decision making?

- What was the process of completing the task at hand? Did you do any initial planning?
- Did you receive any feedback from users, peers or lecturers? How did you react to it?

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