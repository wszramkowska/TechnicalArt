# Alive Below

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


## Implementation

### What was the process of completing the task? What influenced your decision making?



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

[AI Test](https://www.youtube.com/watch?v=_tasIn8A2RQ&ab_channel=WSzramkowska)
<iframe width="560" height="315" src="https://www.youtube.com/embed/_tasIn8A2RQ?si=jSHXRMn-J7314x3o" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

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

[Enemy animation](https://www.youtube.com/watch?v=Di2K0OgP76Q&ab_channel=WSzramkowska)

<iframe width="560" height="315" src="https://www.youtube.com/embed/Di2K0OgP76Q?si=MK6J8ufW9gO_DBI5" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


<br>

#### Building the map
I looked through the asset packs on Fab and found a medieval dungeon asset pack by Infuse Studio which I thought would be perfect to help create an unsettling atmosphere in my game.

- Small map to get the feeling of being trapped with the enemy.
- Lots of 'rooms' for the player to explore the environment, and also to disorient the player, making it a bit more difficult to search for the exit.
- The rooms gave me the idea to include a key the player would have to search for in order to unlock the exit. The key would force the player to move around the map more, which increases the likelihood of them encountering the enemy.
- Slight variation in shape but the map is mostly just a rectangle, with more rectangles inside. This keeps it clean and fair. 
- Since I decided to keep the map small I thought my game would work well with just the one enemy. This is when I had the idea to make the enemy a one shot kill on the player, which would add to the tension. This also meant I would no longer need the HP bar I made at the beginning of the project.
- I did some scene dressing, adding in props to make the environment feel more alive and in general be less boring to look at. I tried to vary the rooms, but not have too many props so as not to distract too much from looking for the key.

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

*Figure 11 Blueprints for destroying the key*

[Key and door test](https://www.youtube.com/watch?v=WYU4weehMSc&ab_channel=WSzramkowska)

<iframe width="560" height="315" src="https://www.youtube.com/embed/WYU4weehMSc?si=BMbtg7huz3RYLgm7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


#### Lighting 
For lighting I knew I wanted my level to be fairly dark in order to create a scary atmosphere, hiding my enemy in the shadows. As I have never done this before I searched for a youtube video which could show me some of the possibilities with lighting in Unreal. I found one by Matt Aspland which specifically looks at interiors (How To Light Interiors In Unreal Engine 4 & 5 (Tutorial), 2022).

- I used torches to light up the corridors, using a fire particle asset I created in one of my earlier tasks. 
- I used rect lights in the rooms as the player would have to search for the key in these so I thought it would be fair to make them brighter.
- I used point lights on some of the torches to give a brighter orange glow in the area, replicating the sort of lighting you get from fire.

[Lighting Test](https://www.youtube.com/watch?v=qyXZ1G6vcNA&ab_channel=WSzramkowska)

<iframe width="560" height="315" src="https://www.youtube.com/embed/qyXZ1G6vcNA?si=f1LQDMbGgLZZHKGA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

#### Visual Improvements

- Changed my third person camera to first person by moving the camera attached to my character into the head. First person made the game much scarier as you could no longer see what was happening behind you or to the side of you.
- Adding vignette for a horror feel.
- Decreasing field of view, meaning the player sees less and the enemy is scarier.
- Increased intensity of fog to add to the creepy atmosphere.

#### Audio 
Audio is a key feature in horror games and can really set the tone and mood of the game. I got my sounds and music from Zapsplat and Pixabay.

- I used meta sound source for audio 
- Most of my sounds are set up quite basic escept breathing which has a filter and limiter as it was originally too loud and obnoxious.

<iframe src="https://blueprintue.com/render/kdmyjw2m/" scrolling="no" allowfullscreen></iframe>

*Figure . Meta sound source for human breathing*

- I created sound attenuation for fire, to add a bit of liveliness to the environment.
- I created sound attenuation for the zombie footsteps so the player can only hear them when they are close by.
- Footstep sounds were done by adding a 'play sound' notify to the zombie walk and run animations. I timed these notifies with when the zombies foot was on the ground. This allowed me to achieve footsteps which matched the visual and the sound.
- I also added sound attenuation to zombie breathing so the player starts hearing these disturbing noises when the enemy is nearby.

Background sound to make the environment feel alive:
- Horror music
- Dungeon ambience

Sounds:
- Footsteps - help the player avoid the enemy but also build tension as you know he is near
- Zombie breathing/noises - unsettling almost choking sounds which convey your enemy is a monster and not something human
- Human/player breathing: Faint breathing, people often breathe heavier when experiencing anxiety or fear
- Zombie scream - lets the player know the enemy is directly behind them and attacking

#### Menus 
Now that my main game loop was done I needed to create some menus so the player could navigate the game and there was on obvious win/lose. Although I have done a widget for my health bar early on in my project, I still wasn't the most familiar with UI in Unreal and its capabilities. To learn more about it I watched a video by Unreal University which showed how to create a main menu (How To Create A Main Menu - Unreal Engine 5 Tutorial, 2022). This video helped me learn how to use buttons which turned out to be fairly simple with the 'on clicked' events. I focused on functionality rather than visuals as I wanted feedback on my main gameplay loop.

Main menu 
- Used a screenshot of my game as a background image
- Start and quit buttons 
- Title of my game 
- Tried to pick a horror font but I did not spend too much time on this as it is not the focus for my project or developing my skills.

<iframe src="https://blueprintue.com/render/2iq9qb9i/" scrolling="no" allowfullscreen></iframe>

*Figure . setting input mode blueprints*

<iframe src="https://blueprintue.com/render/xtx_purr/" scrolling="no" allowfullscreen></iframe>

*Figure . blueprints for start and quit button*

Game win
- Button to main menu restart or quit
- Simple Escaped message 

<iframe src="https://blueprintue.com/render/in6q22_q/" scrolling="no" allowfullscreen></iframe>

*Figure . blueprints for game win*

Game Loss
- Button to main menu, restart or quit
- Simple game over message

<iframe src="https://blueprintue.com/render/4285lcww/" scrolling="no" allowfullscreen></iframe>

*Figure blueprints for game over*

[Menus Test](https://www.youtube.com/watch?v=yQ6JdHc166k&ab_channel=WSzramkowska)

<iframe width="560" height="315" src="https://www.youtube.com/embed/yQ6JdHc166k?si=YFVE2nFVEi45mkz4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

#### Feedback
I asked family, friends and colleagues to test out my game and give me their feedback. 

Key points from feedback:
- Game is scary, when the enemy is near there is a good level of tension
- Enemy ai could be more advanced e.g. the enemy can hear the player
- Lighting looks good and effective for the genre
- Once you find the key and escape, there is not much incentive to play again as you know where the key is so the game feels easier
- Map is good, not too big but still able to get away from the enemy
- Menus could look more interesting
- There are no instructions for what to do or how to play 

At this point I had limited time left to polish my project so I picked a couple points that I thought were very important and would greatly improve my game, but were still doable within the remaining time frame.

"No incentive to replay"
I wanted my game to be enjoyable for multiple runs and not just a one shot as that might mean the player doesn't even see the entire environment or potentially might not even meet the enemy if very lucky. To solve this issue I decided I would spawn my key in a random location from a set of predetermined locations. This means finding the key is not enough, you actually have to escape as well because on your next run it might be in a different location. It also encourages exploration.

"No instructions"
I think players can get easily frustrated when the objective of the game is not clear. I do not want players to get discouraged and drop my game so I decided to add a simple quest style bar in the top right which would direct the player. In addition I would add a message to the door saying something like "Press E to open" to make the controls of the game more obvious.

#### Randomly Spawning Key
I found a video by RubaDev on how to randomize actor spawn locations and adapted this to my blueprints in order to get different spawn locations for my key each time the level starts. 

- Set 5 target points where I wanted my key to spawn. I didn't want completely random spawn points as I wanted the locaction of the key to be fair and to make sense within the environment.
- Referenced these target points in my level blueprint and put them in an array.
- Got the locations and randomised them using 'random integer in range'
- Spawned the key

<iframe src="https://blueprintue.com/render/gfmawe9q/" scrolling="no" allowfullscreen></iframe>

*Figure . blueprints for spawning key in random locations*

#### 'Quest' bar
- I created a widget with a small quest bar in the top right of the screen. I added this to viewport from the BP_Key blueprint.
- Initially set to 'find the key'
- Upon player picking up the key I set the text to 'Escape' 

<iframe src="https://blueprintue.com/render/nc8-esjh/" scrolling="no" allowfullscreen></iframe>

*Figure . blueprints for adding the quest bar to viewport and setting the text after picking up ley*

#### Press 'E' prompt on door
- I made a widget and attached it to my door blueprint
- I made the widget visible when the player was within the doors collision box.

<iframe src="https://blueprintue.com/render/kk4k8d5g/" scrolling="no" allowfullscreen></iframe>

*Figure . blueprints for interaction prompt*

<br>

### Did you have any technical difficulties? If so, what were they and did you manage to overcome them?

- Did you have any issues completing the task? How did you overcome them?

##### Door
- opened too quick so I used a lerp node instead of setting my rotation inside of my door timeline 
- only set relative rotation
- doors were opening the opposite way so I added a multiply by -1 to the right door

##### Interact prompt
- was too low down and player couldn't see it so i changed the 'space' to world instead of screen as my message doesnt need to appear in a 360 around the door
- text was always shown so i had to set the initial visibility to off

##### Enemy sounds
- footsteps did not work
- fixed them by adding the play sound to my enemy walking and running animation, playing the sound when the foot was down
- zombie breathing didn't work unless the player spawned within its radius, and wouldnt restart if the player left and returned to the radius
- fixed this by checking play when silent

##### Github
- I had multiple difficulties with using github. Although I have used it for my previous tasks, this unit is the first time I have used github.
- When I downloaded my Medieval Dungeon Asset Pack I was unable to commit and push my changes. To fix this I downloaded git LFS. However that still did not work so I ended up deleting assets I did not need so I was able to commit and push.
- Despite having a .gitignore, whenever I made a build I could not commit my changes in github. I created a folder outside of the github repository, on my desktop, to fix this. However this still did not work so I had to manually delete the build folders within my repository. I also had to discard changes in the commit that were over 100mb, despite having git lfs set up.
- In future projects I will set up git lfs at the start and will also double check my .gitignore is set up correctly. This will hopefully prevent these problems from happening.


## Outcome



[Alive Below Gameplay Trailer](https://www.youtube.com/watch?v=kEkBX7NXY7w&t=89s&ab_channel=WSzramkowska)

<iframe width="560" height="315" src="https://www.youtube.com/embed/kEkBX7NXY7w?si=5UvN41bhssKIN486" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>




[Alive Below Build](https://squlddy.itch.io/alive-below)


<iframe frameborder="0" src="https://itch.io/embed/3156461" width="552" height="167"><a href="https://squlddy.itch.io/alive-below">Alive Below by squiddy</a></iframe>


[Technical Art Github Repository](https://github.com/wszramkowska/TechnicalArt)


## Critical Reflection

### What did or did not work well and why?

#### Improvements
- My enemy ai is very simple, I think a more complex ai could benefit the gameplay. For example adding hearing or adjusting the sight radius to have a more realistic feel. When walking behind the enemy, despite being very close, it won't really notice you unless it turns around.
- I had trouble with the asset pack and my fire particle which could shine through walls in certain areas.
- Time management is a key element for this type of project. Had I been a bit more organised I could have achieved even more and really pushed for complete polish. Since I had no prior knowledge I spent a lot of time reading documentation, watching tutorials and fixing my code. Although this is a normal part of development, as my skills improve I can put more time into my game.
- I used an unstructured method for my blueprints. I think this was okay for my project as it is quite small scale, but I would like to use other methods such as behaviour trees in the future so I can more easily manage bigger projects.

#### What went well
- I actually like the gameplay loop I created even though it is quite simple. Earlier on I had some doubts it would be too boring but after receiving feedback and making keys spawn in random location I think it really elevated the gameplay and gave my game replayability.
- I think I captured a good horror atmosphere through sounds, lighting and level design. When asking for player feedback, many said they felt the tension whilst playing the game.
- I am proud of my research and learning. I was able to implement tutorials and documentation into my own project. It didn't always work but I managed to use problem solving to adapt it and fix it.
- My mechanics are suitable for my genre of game. They work well together, avoiding the enemy, finding the key, escaping. 
- 

### What would you do differently next time?

- Next time I would like to use a method other than unstructured, such as behaviour trees. I hope this will help me with managing my game. 
- I would like to organise my folders better. I made a start on this but I think there is a lot of room for improvement. 
- I think it would be a great addition to make the enemy able to hear the player. It could create more varied gameplay. Along with a crouch this could be a fun mechanic to make the game more stealth like.
- Spend a bit more time on menus, maybe add a settings option to give the player more control over the game. My PC is not the best, so it would lag quite a bit on higher settings which I think reflects in the trailer. I would like to add options to lower the graphics which would fix situations like that.
- Settings could also add accessibility with things like subtitles, even if it is just for the enemy's footsteps in the case of my game.
- I would love to add a cinematic sequence to create a jumpscare when the enemy kills the player.

## Bibliography

Unreal Engine 5 Health and Damage System Tutorial [2023] (2023) At: https://www.youtube.com/watch?v=vO1i9Wcx4Xc (Accessed  03/11/2024).

Unreal Engine 5 AI Patrol and Chase Tutorial (2023) At: https://www.youtube.com/watch?v=lbqZS-cgcQs (Accessed  03/11/2024).

AI Attack Tutorial - Unreal Engine 5.2 (2023) At: https://www.youtube.com/watch?v=N7CqOJNeAyU (Accessed  05/12/2024).

Door And Key System | How To Open A Locked Door With A Key In Unreal Engine 5 (Tutorial) (2023) At: https://www.youtube.com/watch?v=Bcle9sSS4Oo (Accessed  05/12/2024).

How To Create A Main Menu - Unreal Engine 5 Tutorial (2022) At: https://www.youtube.com/watch?v=kumZj_mov58 (Accessed  05/12/2024).

How To Light Interiors In Unreal Engine 4 & 5 (Tutorial) (2022) At: https://www.youtube.com/watch?v=PKjnYulklNA (Accessed  05/12/2024).


## Declared Assets

Medieval Dungeon - Infuse Studio (s.d.) At: https://www.fab.com/listings/c13bd0dc-ac4d-4595-b284-f81386b2e6ef (Accessed 05/12/2024)

Zombie breathing | Huminaatio (s.d.) At: https://pixabay.com/sound-effects/zombie-breathing-54693/ (Accessed  05/12/2024).

Zombie Screaming | Alex_Jauk (s.d.) At: https://pixabay.com/sound-effects/zombie-screaming-207590/ (Accessed  05/12/2024).

Boys sneaker, single footstep on concrete 5 Sound Effect - Download FREE - ZapSplat (s.d.) At: https://www.zapsplat.com/music/boys-sneaker-single-footstep-on-concrete-5/ (Accessed  05/12/2024).

Man breathing, open mouth, medium speed and heavy Sound Effect - Download FREE - ZapSplat (s.d.) At: https://www.zapsplat.com/music/man-breathing-open-mouth-medium-speed-and-heavy/ (Accessed  05/12/2024).

Dungeon ambience, cold dark and eerie droning tone with howling wind outside and water drips, could also be cave Sound Effect - Download FREE - ZapSplat (s.d.) At: https://www.zapsplat.com/music/dungeon-ambience-cold-dark-and-eerie-droning-tone-with-howling-wind-outside-and-water-drips-could-also-be-cave/ (Accessed  05/12/2024).

Horror Background Atmosphere #11 | Royalty-free Music (s.d.) At: https://pixabay.com/music/mystery-horror-background-atmosphere-11-240870/ (Accessed  05/12/2024).


Used to assist in finding research material:
Chat GPT



The following assets were created or modified with the use of GPT 4o:
- Test.cs
- AnotherScript.cs
- Development Journal.html

