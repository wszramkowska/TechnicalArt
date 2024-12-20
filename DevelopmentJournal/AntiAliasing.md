# Anti-Aliasing

Technical Art

Sid Szramkowska

2106125

## Research

### What sources or references have you identified as relevant to this task?

I haven't previously done any in-depth research into anti-aliasing, therefore I thought a good place to start would be Unreal official documentation as that is the engine I would be using to test and measure various anti-aliasing methods. 

To further my research I thought it would be a good idea to find some video sources as it would help visualise the effects of anti-aliasing, which would give me a base idea of why a player or developer might use one method of anti-aliasing over another.




#### Sources

##### Unreal Documentation



To get a good grasp of how anti-aliasing works, specifically in Unreal Engine, I turned to the official documentation. This is written by the Epic Developer Community, which makes this a good, reliable source. (Anti Aliasing and Upscaling in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community, s.d.). I found documentation about 'Anti-aliasing and Upscaling' which explained the different methods (TSR, TAAU, FXAA, MSAA).

Although the methods are different they all aim to smooth the jagged edges in images.

TSR
- Temporal Super Resolution uses a specific algorithm to enhance image quality through focusing the GPU resources on the upscaling process.
- Rendered at much lower internal resolution, compared to what the Unreal Engine 4 Temporal anti-aliasing can achieve.
- High quality visuals, whilst using less processing power.

TAAU
- Temporal Anti-Aliasing Upsampling samples different locations within a frame, and uses past frames.
- You can choose the quality using the Engine Scalability Settings.

FXAA
- Fast Approximate Anti-Aliasing is a quick method used after rendering an image.
- Finds edges using a high-contrast filter and blends the colours to make them look better.
- Works well on low-end devices.
- Final image may be worse in quality compared to other methods.

MSAA
- Multi Sample Anti-Aliasing smooths parts of an image, where the jagged edges are particularly noticeable.
- It manipulates the colour along these edges to blend the colours of the surrounding pixels, creating the illusion of a smoother edge.
- More samples lead to better quality but worse performance.

Overall I found the Unreal documentation contained a good amount of useful information which could assist with optimisation. The documentation also tells you where to find the settings to change things like dithering quality or set the primary screen percentage, to further customise the anti-aliasing. There were also images included in the documentation, with sliders that show you the difference between no anti aliasing and with anti aliasing which I thought was helpful to compare the methods. However I thought some of the language was difficult to understand unless you already have some knowledge on anti-aliasing in Unreal, as very specific terms are used. 

##### Youtube Video "Tech Focus: Anti-Aliasing - What Is It And Why Do We Need It?" by Digital Foundry

<iframe width="560" height="315" src="https://www.youtube.com/embed/NbrA4Nxd8Vo?si=c2svQXcOZbi72KMg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

I did further research to better my understanding, this time looking for a more visual source. I thought this would be very helpful as anti-aliasing is used to create smoother visuals, therefore a video might be better suited to show that off, rather than documentation. I found a video by Digitak Foundry (Tech Focus: Anti-Aliasing - What Is It And Why Do We Need It? - YouTube, s.d.) which looks more in depth into what anti-aliasing actually is and why it is important. "Digital Foundry specialises in game technology and hardware reviews, using bespoke capture and analysis tools to provide a unique look at the way games play."

- SSAA (Super Sampling Anti-aliasing) is costly with great quality.
- MSAA (Multisample anti-aliasing) is less costly but barely available anymore.
- TAA (Temporal anti-aliasing) is cheaper and of high quality but with ghosting and blur.
- Post AA, such as FXAA (Fast Approximate anti-aliasing) is the cheapest with okay quality. Best used in combination with other aa methods.

This video was incredibly useful for me to improve my understanding, with plenty of video game footage to show the effects of anti-aliasing within an actual game. All points were supported by visual examples, which made them easy to follow whilst still allowing an in depth explanation. However, this video was uploaded 6 years ago, which means anti-aliasing methods have potentially changed or improved since then. From my previous research, the information does still seem quite accurate.






## Implementation

### What was the process of completing the task? What influenced your decision making?

- Using Unreal Engine I tested the different anti-aliasing methods. 
- To get an idea of how performance is affected, I created a stress test.
- I have also created this development journal to record my research and implementation of the different topics within my Technical Art course. For this I had to learn markdown, starting with the syntax.
- To submit my work I learned to convert my markdown to html so all my figures and links would appear as images and videos, making the development journal easier to view.

*Figure 1. Blueprints for the spinning cubes*

<iframe src="https://blueprintue.com/render/ehihxtcn/" scrolling="no" allowfullscreen></iframe>

<br>

*Figure 2. Blueprints for the spinning cube object manager*

<iframe src="https://blueprintue.com/render/5nn9wlta/" scrolling="no" allowfullscreen></iframe>

### What creative or technical approaches did you use or try, and how did this contribute to the outcome?

- For my stress test I made blueprints to keep spawning in spinning cubes.
- This would allow me to see how anti-aliasing affects performance, and how well each method works when met with a demanding game. 

<br>

### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- As the anti-aliasing is already built into the Unreal engine, I didn't have many problems with this task, it was more of a simple observation and then comparison.

### Outcome

*Figure 3. Video of my stress test in Unreal Engine*

[Stress Test](https://www.youtube.com/watch?v=vxJWbTaEc8A&ab_channel=WSzramkowska)
<iframe width="560" height="315" src="https://www.youtube.com/embed/vxJWbTaEc8A?si=blZrN1Bc7LV1P9mn" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- From my test I could see a drop in performance when using anti-aliasing by looking at the FPS.
- FXAA seemed to have the best performance whilst MSAA seemed to have the lowest, with increased lag and a rapid FPS drop.
- This matches the conclusions from my research.


## Critical Reflection

### What did or did not work well and why?

- Overall I was quite happy with my results as they supported my research. It was interesting to be able to test these methods myself as it allowed more control over the experiment.
- On the other hand my test was done using cubes which made the visual element of anti-aliasing more difficult to recognise.

### What would you do differently next time?

- To improve the test I could create a scene with higher quality visuals in order to compare their appearance.
- I could also do another test in a different game engine and compare that to my Unreal engine results.

## Bibliography

Anti Aliasing and Upscaling in Unreal Engine | Unreal Engine 5.5 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/anti-aliasing-and-upscaling-in-unreal-engine (Accessed  12/10/2024).


Tech Focus: Anti-Aliasing - What Is It And Why Do We Need It? - YouTube (s.d.) At: https://www.youtube.com/watch?v=NbrA4Nxd8Vo&ab_channel=DigitalFoundry (Accessed  12/10/2024).
