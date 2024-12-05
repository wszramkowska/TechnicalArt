# [TASK NAME]

Technical Art

Sid Szramkowska

2106125


The theme for this project is 'Alive' so I came up with a couple of initial ideas. One of the ideas was a simplified farming game where you would keep plants or crops alive. My second idea was an fps style game where you would have to continuously kill enemies in order to stay alive. However, since it was my first time making a game in Unreal, I thought these might be a bit too complicated, especially the farming game. I decided to go for a game where the player would be stuck in a building with monsters, trying to stay alive whilst looking for the exit.

## Research

### What sources or references have you identified as relevant to this task?



I wanted to look at some video games to get inspiration for my game, specifically some stealth or chase scenes in horror games. A couple games that came to mind were Outlast and Resident Evil Village which have many tense chase/stealth scenes. 
I will of course also be looking at Unreal documentation throughout my project, when I feel stuck with blueprints or anything else, as documentation is a good, official and up to date source.
For my core mechanics I will try to find video tutorials to help me.

#### Sources

#### Outlast

Outlast is a first-person survival horror game developed and published by Red Barrels. One of the scariest parts of the game for me personally was the sewer section where you are trapped with an enemy. The enemy is Chris Walker, a huge variant who pursues the main character relentlessly. I have narrowed down the 3 things that make this segment of the game so terrifying, and I hope I can implement some of this in my own game.

[Outlast Full Chris Walker Sewer Scene](https://www.youtube.com/watch?v=xkJDQPPZA7c&ab_channel=Mitsuownes)

<iframe width="560" height="315" src="https://www.youtube.com/embed/xkJDQPPZA7c?si=YwNpXNClvKvzmNCd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
(OUTLAST (Horror) Full Chris Walker Sewer Chase SCENE | PS5 Gameplay, 2022)



##### Audio
- You hear the rattle of chains before you even see Chris Walker coming, immediately making the player tense in anticipation of getting caught.
- Music ramps up when getting chased, which gives a feeling of something being constantly behind you, however being too afraid to look back and slow yourself down.

##### Trapped
- The player falls into this sewer and is stuck down there with Chris Walker. Since the area is not massive you feel like he is constantly on your tail.
- The sewer can be difficult to navigate which adds further feeling of entrapment as you struggle to find the exit.

##### Lighting 
- It is very dark in this section, especially when you drop down to the lower level of the sewer. This makes it hard to spot Chris Walker.
- Additionally humans have an innate fear of the dark, which is amplified by the knowledge of a dangerous enemy being there with us.
- The player uses a camera which has night vision, but the battery can drain quickly so there is the additional fear of losing what vision you do have.

##### No weapons
- A key feature in the Outlast series is a lack of weapons. This is terrifying when facing enemies out to kill you.
- Player has no defense and can therefore more easily empathise with the fear of the game protagonist. 

<br>

Overall I think I can learn a lot from this section of the game in creating a tense atmosphere which will elevate my project as I am aiming for a horror feel. Through both my research and my own gameplay I think many players agree this is a successfull example of horror done right.

#### Unreal Documentation




#### Sources

- An opening paragraph about the source stating the author, developer or organisation, this paragraph should explain the source's influence, credentials, critical reception, awards, reputation or any issues with the source. For example, if the source is not reputable. If the source is a game, the issues that occurred during development or if had a poor launch.
- List the aspects analysed in reference to the current task.
- An ending paragraph stating what you enjoyed or disliked, what you agreed with or not agree with.

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

#### Planning 
Due to my lack of experience with Unreal I did not want to set myself many aspirational goals which I then might not be able to complete. Instead I kept my mechanics simple and aimed for polish.

- Trapped in a building
- Avoid enemies
- Find the exit 

#### Health and Damage System 
The first thing I did in my project was create a health system. This is because it is one of the only things I am familiar with in Unreal due to some University tutorials on it. I used the third person template, so I did the health system in the BP_ThirdPersonCharacter.

- Made a health bar widget blueprint, designes using a progress bar.


<iframe src="https://blueprintue.com/render/s0uto83x/" scrolling="no" allowfullscreen></iframe>

*Figure 1. Blueprints for updating the health bar* 

- I used AnyDamage and took current health away from my max health. When health is 0 or below the player will die.

<iframe src="https://blueprintue.com/render/3en7eame/" scrolling="no" allowfullscreen></iframe>

*Figure 2. Blueprints for player taking damage*

- For my player death logic I disabled movement, added a game over widget and set the game to paused.

<iframe src="https://blueprintue.com/render/06o1thq7/" scrolling="no" allowfullscreen></iframe>

*Figure 3. Blueprints for player death*

<br>

#### Enemy AI Chase, Patrol, Deal Damage
I knew I wanted my game to have enemies so I tackled enemy AI next. I found a good youtube video by Pixel helmet (Unreal Engine 5 AI Patrol and Chase Tutorial, 2023) which showcased how to create an enemy ai which patrols and chases the player upon seeing them.

- I made a blueprint for my enemy.
- I used NavMeshBoundsVolume to determine the area my enemy ai would work within.
- I gave my enemy a PawnSensing component, which allowed me to choose its sight radius.
- Initially I used a mannequin from the Unreal starter content, but later switched my static mesh to a zombie I found on Mixamo.
- My patrol logic got a random location within the Nav mesh bounds and moved the ai to that location.

<iframe src="https://blueprintue.com/render/iqmhoil-/" scrolling="no" allowfullscreen></iframe>

*Figure 4. Blueprints for enemy patrol*
<br>
- My chase logic uses On See Pawn from the PawnSensing component
- When the enemy sees the player I play a running animation and increase speed.
- Then I move the ai to the player location.
- If the player is hidden for 2 seconds, movement speed and animation is set back to walking.
- If the ai successfully reaches the player, it will attack.

<iframe src="https://blueprintue.com/render/ibymjtv8/" scrolling="no" allowfullscreen></iframe>

*Figure 5. Blueprints for enemy chase*

- For my enemy to deal damage, I used a sphere collision component.
- I attached the sphere to the hand of my zombie as that is what it will be using to hit the player.
- If the player is within the range of this sphere, they will take damage.

<iframe src="https://blueprintue.com/render/45jkgj6e/" scrolling="no" allowfullscreen></iframe>

*Figure 6. Blueprints for enemy deal damage*

<br>
 
#### Enemy Animations
To animate my enemy I used animations from Mixamo. I used a combination of animation blueprints, blend spaces and animation montages. So far in my project I had a good understanding of what was going on but I really struggled with animations. To help I went over my Animation System task journal so I could figure out idle, walk and run animations. I also found a youtube video by Lisowi (AI Attack Tutorial - Unreal Engine 5.2, 2023) which showed me how to play my attack animations once the enemy is in attack range of the player.

- I made a blend space for my zombie character. This would transition between the idle, walking and run animation. 
- I used this blend space in an animation blueprint. This would change the animation based on the speed of the enemy, so during chases it would play the running animation.

<iframe src="https://blueprintue.com/render/uk4uthg-/" scrolling="no" allowfullscreen></iframe>

*Figure 7. Animation blueprint event graph*


- I created an attack animation montage for my enemy, in case I wanted a variety of animations for the attack.
- I added a montage notify in my zombie attack montage. This is timed to be where the enemies hand begins to come down, as that is where the player appears to be taking damage.
- In my enemy blueprints I played the animation montage when the player was within attack range. 

<iframe src="https://blueprintue.com/render/muk6va19/" scrolling="no" allowfullscreen></iframe>

*Figure 8. Blueprints for enemy attack animation*

<br>

#### Building the map
I looked through the asset packs on Fab and found a medieval dungeon asset pack by Infuse Studio which I thought would be perfect to help create an unsettling atmosphere in my game.

- Small map to get the feeling of being trapped with the enemy.
- Lots of 'rooms' for the player to explore the environment, and also to disorient the player, making it a bit more difficult to search for the exit.
- The rooms gave me the idea to include a key the player would have to search for in order to unlock the exit. The key would force the player to move around the map more, which increases the likelihood of them encountering the enemy.
- Slight variation in shape but the map is mostly just a rectangle, with more rectangles inside. This keeps it clean and fair. 
- Since I decided to keep the map small I thought my game would work well with just the one enemy. This is when I had the idea to make the enemy a one shot kill on the player, which would add to the tension. This also meant I would no longer need the HP bar I made at the beginning of the project.

<br>

#### Interact: Key and door
Since I had the idea to add a key into the game, I decided to work on it right away. I found a video tutorial by Matt Aspland (Door And Key System | How To Open A Locked Door With A Key In Unreal Engine 5 (Tutorial), 2023) on making a door and key system. This taught me how to create an interact input, how to animate my door using a timeline, and how to specify which key unlocks which door.

- Made a blueprint interface for 'interact' and 'door'
- Set 'E' as my interaction button and added the interact input logic to my third person character blueprint. I used the enhanced input action system.
- Made a blueprint for key and door. Gave them both collision boxes.
- Animated the door using a timeline

<iframe src="https://blueprintue.com/render/qxpkc30l/" scrolling="no" allowfullscreen></iframe>

*Figure 9. Blueprints for the Interact Input*

- Door opens if 'HasKey?' is true
- Left and right door are animated using set relative rotation and door timeline

<iframe src="https://blueprintue.com/render/msw381ik/" scrolling="no" allowfullscreen></iframe>

*Figure 10 Blueprints for door opening*

- When player picks up key, the key object is destroyed

<iframe src="https://blueprintue.com/render/a1s2vpwl/" scrolling="no" allowfullscreen></iframe>

*Figure 11* Blueprints for destroying the key*











### What creative or technical approaches did you use or try, and how did this contribute to the outcome?

- Did you try any new software or approaches? How did the effect development?

<br>

![onhover image description](https://beforesandafters.com/wp-content/uploads/2021/05/Welcome-to-Unreal-Engine-5-Early-Access-11-16-screenshot.png)
*Figure 2. An example of an image as a figure. This image shows where to package your Unreal project!.*

### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- Did you have any issues completing the task? How did you overcome them?

#####Door
- opened too quick so I used a lerp node instead of setting my rotation inside of my door timeline 
- only set relative rotation
- doors were opening the opposite way so I added a multiply by -1 to the right door

#####Interact prompt
- was too low down and player couldn't see it so i changed the 'space' to world instead of screen as my message doesnt need to appear in a 360 around the door
- text was always shown so i had to set the initial visibility to off

#####Enemy sounds
-footsteps did not work
- fixed them by adding the play sound to my enemy walking and running animation, playing the sound when the foot was down
- zombie breathing didn't work unless the player spawned within its radius, and wouldnt restart if the player left and returned to the radius
- fixed this by checking play when silent



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

Unreal Engine 5 Health and Damage System Tutorial [2023] (2023) At: https://www.youtube.com/watch?v=vO1i9Wcx4Xc (Accessed  03/11/2024).

Unreal Engine 5 AI Patrol and Chase Tutorial (2023) At: https://www.youtube.com/watch?v=lbqZS-cgcQs (Accessed  03/11/2024).

AI Attack Tutorial - Unreal Engine 5.2 (2023) At: https://www.youtube.com/watch?v=N7CqOJNeAyU (Accessed  05/12/2024).

Door And Key System | How To Open A Locked Door With A Key In Unreal Engine 5 (Tutorial) (2023) At: https://www.youtube.com/watch?v=Bcle9sSS4Oo (Accessed  05/12/2024).








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
