
# Live Project
## Introduction
&emsp;  The purpose of this Live Project is to give us experience of what it could be like in a job setting. For this live project, we were given the task of creating a sandbox game. So I decided to do something a little nostalgic for me. When I was little, there was a game I played (by which I mean my sister would play and I’d watch). That game was Toy Story 2. We honestly never left the first level because we loved replaying it over and over (and we probably didn’t know how to proceed). Regardless, I thought it would be fun to make a sandbox about a toy exploring their old home before leaving. Including parkour, an NPC side mission, and collecting.

Below are descriptions of the stories I worked on, along with some screenshots of blueprints and GIFs.

## User Stories
 * [Landscape](#landscape)
 * [HUD](#hud)
 * [Collectables](#collectables)
 * [Main Menu](#main-menu)
 * [GamePlay](#gameplay)
 * [Sounds](#sounds)
 * [New Level](#new-level)
 * [Game Instance](#game-instance)
 * [NPC](#npc)
 * [Polish](#polish)
 * [Assets](*assets)

##

### Landscape

&emsp;  This story was only about building at a very basic level. I decided to make a simple house, walls, and some furniture. For this, I wanted to try actually creating some of the furniture myself. I did this by using the Cubegrid in Modeling mode. Is it the best, no. But I did get to learn more about the modeling mode in Unreal Engine.
    

<p align=center>
<img src = Image/Story1/Level1_Furniture.png/>
</p>
<br/>

&emsp; For the level’s layout, I made a joke of a home. I’m aware it’s the bare minimum, but for now I can see where I want to go from here. Where I want the kitchen, living room, and bedroom.

<p align=center>
<img src = Image/Story1/OverviewLevel.png/>
</p>
<br/>


&emsp;  In retrospect, I could have made the house a little smaller and less intimidating for myself. But I will say it was fun later on when I was trying to polish the final look of the game.


*Jump To: [Page Top](#introduction), [Collectables](#collectables), [Main Menu](#main-menu), [GamePlay](#gameplay), [Sounds](#game-over),[New Level](#new-level), [Game Instance](#game-instance), [NPC](#npc), [Polish](#polish)*
##

### HUD

&emsp; This story focused on adding a HUD, along with a health system and stamina. First, I set up the system.
 
<br/> <br/>


#### Decrimate Health
&emsp; For the time being, I used a basic health damage system.
<p align=center>
<img src = Image/Story2/BasicHealthDecrimateSystem.png/>
</p>
<br/>

&emsp;  I didn’t add a way to replenish health with this story, mostly because I wanted to focus on the UI aspect. I decided to add healing to another story for the time being.


&emsp;  After this, I started making the Overlay and connecting it to the player. I made a Widget for the Overlay (I built the healthbar in this), and a Stamina widget. I would be using this repeatedly, so I made a function for it to clean up the code a bit.

<p align=center>
<img src = Image/Story2/CasttoControllerFunction.png/>
</p>


&emsp; And finally, putting everything together (I did add a pain volume that I was using to test the health system).

<p align=center>
<img src = Image/Story2/FinalLookofHealth.png>
</p>

<p align=center>
<video src ="Video/HealthUI.mp4"  autoplay loop muted playsinline width="60%">
  Your browser does not support the video tag.</video>
</p>


#### Stamina
&emsp; Then Came the Stamina. I’ll be honest and say I just wanted to try to make a stamina system in a game. I saw the opportunity and made one for this project. For this, I did had to look up how to actually build a Stamina System (*https://www.youtube.com/watch?v=oqqcvd-6aBo&t=939s).

First, I made a Function for decrementing the Stamina. I made variables for Stamina, Walking, and Running. I added a LeftShift Event to add Running and Walking.

Decrimate Stamina.
<p align = center>
<img src =  Image/Story2/DecrimateStamina.png>
</p>

IsRunning? and IsWalking?

<p align = center>
<img src =  Image/Story2/LeftShift.png>
</p>



Made a custom Event Called ConsumeStamina

<p align=center>
<img src = Image/Story2/ConsumeStaminaPart1.png/>
</p>

&emsp; Another Custom Event and Function that replenishes the stamina.

Replenish Stamina Function

<p align = center>
<img src =  Image/Story2/ReplenishingStamina.png>
</p>


ReplenishStamina Event
<p align=center>
<img src = Image/Story2/ConsumeStaminaPart2.png/>
</p>

<p align=center>
<img src = Image/Story2/ConsumeStaminaPart3.png/>
</p>


And finally, putting it all together.

<p align=center>
<video src ="Video/StaminaUI.mp4"  autoplay loop muted playsinline width="60%">
  Your browser does not support the video tag.</video>
</p>



&emsp; In hindsight, I should have made the healthbar a separate widget. It still works and didn’t cause too many problems later on. It just made it confusing when I tried to edit the overlay, and the Health bar would change along with it. 

*Jump To: [Page Top](#introduction), [Landscape](#landscape), [Main Menu](#main-menu), [GamePlay](#gameplay), [Sounds](#game-over),[New Level](#new-level), [Game Instance](#game-instance), [NPC](#npc), [Polish](#polish)*

##

### Collectables


&emsp; I made this story overly complicated for myself when I started it. I wanted three different collectables: Keys, Notes, and Food. I was trying to add a function to all of the collectables (keys to unlock the next level, notes to pick for a side mission, and food to replenish health). When I realized that two of them wouldn’t be possible at the moment, I decided to pin them for a later story. Thus, I was finally able to make it simple by focusing on two things: one, the health, and two, updating the UI.

#### Notes
&emsp; For the Notes, I decided to just make the player pick up a BP_Note and for the UI to show how many notes were picked up. I did make a parent BP since these two were similar.

The Sprite I used
<p align=center>
<img src = Image/Story3/NoteSprite.png/>
</p>


The Code updating the widget, and I won’t lie, for a moment I thought it wasn’t working till I realized I forgot to add it to the UI
<p align=center>
<img src = Image/Story3/NotesWidgetCode.png/>
</p>

The Code in the BP_Note that counts the letters.
<p align=center>
<img src = Image/Story3/BPNote.png/>
</p>

<p align=center>
<video src ="Video/NotePickup.mp4"  autoplay loop muted playsinline width="60%">
  Your browser does not support the video tag.</video>
</p>

#### Onions
&emsp; This was going to replenish the player’s health. I did my best to make it as simple as possible.

The Sprite
<p align=center>
<img src = Image/Story3/HealthSprite.png/>
</p>


The Code For the BP_Health
<p align=center>
<img src = Image/Story3/BPHealth.png/>
</p>

Then it was finally time to test it.

<p align=center>
<video src ="Video/HealthPickup.mp4"  autoplay loop muted playsinline width="60%">
  Your browser does not support the video tag.</video>
</p>

#### Falling damage 

&emsp; You probably noticed that the player was somehow getting damage when they fell in the GIF. I had decided to also add falling damage. Since this was a small character, I figured it would make it more challenging for the player. I didn’t know where to start, so I did follow a YouTube video for this too (https://www.youtube.com/watch?v=QaH7zqFuyvg&t=1s)


First, we need to calculate the distance of the player.
<p align=center>
<img src = Image/Story3/CalculatingDistance.png/>
</p>

Connecting the Fall to the Decreased Health.
<p align=center>
<img src = Image/Story3/FallingDamage.png/>
</p>

Then finally putting them together to calculate how much damage each length of fall would do.

<p align=center>
<img src = Image/Story3/IsFalling.png/>
</p>


*Jump To: [Page Top](#introduction), [Landscape](#landscape), [HUD](#hud), [GamePlay](#gameplay), [Sounds](#game-over),[New Level](#new-level), [Game Instance](#game-instance), [NPC](#npc), [Polish](#polish)*
##

### Main Menu

&emsp; This was by far the simplest story. I just had a lot of fun looking up images to use for the background. I made sure to program the buttons for the start and quit.

The Code for the Start and Quit Buttons.

<p align=center>
<img src = Image/Story4/StartQuitButton.png/>
</p>

The Main Menu,
<p align=center>
<img src = Image/Story4/MainMenu.png/>
</p>

The Lose Screen,

<p align=center>
<img src = Image/Story4/LoseWidget.png/>
</p>


and the Win Screen.

<p align=center>
<img src = Image/Story4/WinWidget.png/>
</p>


&emsp; In hindsight, I should have removed the options button. I, unfortunately, will completely forget about this. I will definitely strive to make sure all buttons are working in future projects.




*Jump To: [Page Top](#introduction), [Landscape](#landscape), [HUD](#hud), [Collectables](#collectables), [Sounds](#game-over),[New Level](#new-level), [Game Instance](#game-instance), [NPC](#npc), [Polish](#polish)*


##

### GamePlay

&emsp; For this, I also tried to make it simple. A win condition (Collecting 3 keys to open the door). And A lose Condition (Connecting the lose Screen when the player dies.)

#### Winning Condition

&emsp; I want to make this simple so that the player has to collect three keys to unlock the door. I made a BP for the Key and Lock.

<p align=center>
<img src = Image/Story5/BPKey.png/>
</p>

And the code for the lock.
<p align=center>
<img src = Image/Story5/BPLock.png/>
</p>


#### Losing Condition

&emsp; For this, I added a new event to the player called OnDeath. This would activate after the player hit 0 and trigger the widget to pull up.

I added an OnDeath Custom Event that would pull up the lose widget.
<p align=center>
<img src = Image/Story5/OnDeathEvent.png/>
</p>

And updated the Health system

<p align=center>
<img src = Image/Story5/UpdatedHealthSystem.png/>
</p>


*Jump To: [Page Top](#introduction), [Landscape](#landscape), [HUD](#hud), [Collectables](#collectables), [New Level](#new-level), [Main Menu](#main-menu), [Game Instance](#game-instance), [NPC](#npc), [Polish](#polish)*

##

### Sounds

&emsp; This one was also pretty simple. Collecting all the sounds I wanted, and even wanted to try adding songs to the level. For this, I added sounds for the Player Walking, Jumping, and Running. A sound for each collectable. In addition, I also attached Ambience songs depending on what area you were in.

I made a Meta sound for the Footsteps for running and walking.

<p align=center>
<img src = Image/Story6/MetaSoundFootStep.png/>
</p>

Then added them to the animations: Walking, Running, Jumping, and Landing.
<p align=center>
<img src = Image/Story6/RunningSoundEffects.png/>
</p>

And added them to Collectables just before they get destroyed.
<p align=center>
<img src = Image/Story6/AddingSounds.png/>
</p>


*Jump To: [Page Top](#introduction), [Landscape](#landscape), [HUD](#hud), [Collectables](#collectables), [Main Menu](#main-menu), [GamePlay](#gameplay), [Sounds](#game-over), [NPC](#npc), [Polish](#polish)*

##


### New Level

&emsp; This one was also simple. I did the same thing I did with level one: add a few assets to get a gist of where I want everything to be. (Leaving to make it look nice in the final story).

<p align=center>
<img src = Image/Story7/Level2Draft.png/>
</p>


*Jump To: [Page Top](#introduction), [Landscape](#landscape), [HUD](#hud), [Collectables](#collectables), [Main Menu](#main-menu), [GamePlay](#gameplay), [Sounds](#game-over), [NPC](#npc), [Polish](#polish)*

##

### Game Instance

&emsp; This was a bit tricky since this was my first time making a Game Instance. So I did what anyone would have done... And looked it up (https://www.youtube.com/watch?v=YpPq--LL9z4).

I will be completely honest and say I did have to rewatch this multiple times and look up a few things to make sure I was doing this correctly.

I wanted to carry the health and notes over to the next level. So I made a GameInstance Blueprint called “GI_MainGameInstance”. In this, I made a few variables: PersistentHealth and PersistentNotes.

The reason why I was so convinced I was doing it wrong was that nothing was updating. It took a minute for me to realize I was only looking at the Widgets. After using a debug string and attaching it to the code, I realized I did do it correctly. I just forgot to make sure the UI gets updated too.



<p align=center>
<img src = Image/Story8/GameInstance.png/>
</p>




*Jump To: [Page Top](#introduction), [Landscape](#landscape), [HUD](#hud), [Collectables](#collectables), [Main Menu](#main-menu), [GamePlay](#gameplay), [Sounds](#game-over), [New Level](#new-level), [Game Instance](#game-instance), [Polish](#polish)*
##

### NPC

&emsp; By far the most difficult story for me. I watched all sorts of tutorials (not at the same time and all great tutorials! but too complicated for a simple game like this), and for the life of me, I couldn’t get the mission to trigger when the player got close. In the end, I decided to go for simple: NPC offers the mission, Player collects 5 pages, NPC thanks the player.

#### Updating the Pickup

&emsp; Since this was for the side mission, I wanted to make the Notes a little different and have the player interact with the game more. So after looking around, I found this YouTube video (https://www.youtube.com/watch?v=GMDwtFkChWY&t=158s) that was exactly what I wanted for the pickup system.

First, I made a new InputAction called ‘IA_Pickup’ for the Controls and hooked it to the InputMappingContext, set as Boolean. I put the IA_Pickup in the BP_Note.

<p align=center>
<img src = Image/Story9/IAPickup.png/>
</p>

But I still need to keep count of the Notes, so I attached the old Notes Code to the end of this.

<p align=center>
<img src = Image/Story9/AttachingNoteCounting.png/>
</p>


I also wanted to make sure the player can only click on it when they are close enough.


<p align=center>
<img src = Image/Story9/ConnectingToPlayer.png/>
</p>

I added in the GameMode itself a way to keep track of how many notes there were in the level.

<p align=center>
<img src = Image/Story9/KeepingTrackOFTheNotes.png/>
</p>



#### NPC
&emsp; To accomplish this, I decided to go with a method I used in an earlier project: the branch method. Was it the most climactic solution? Absolutely not. But I was still proud I got it to work in the end. It took trial and error to finally get everything correctly. Making a widget to let me know if the branch system was working and to update the words when the player picks up the notes.

What the NPC would look like. I still wanted to do toys, so I thought A teddy bear would be nice.
<p align=center>
<img src = Image/Story9/NPCStaticMesh.png/>
</p>

&emsp; Then it was setting up the Branch System. I did work backwards on this. I wanted to make sure that when all five notes were picked up, the NPC would say something. I did make a widget for this.

So first it would look to see if the player has all five Notes.
<p align=center>
<img src = Image/Story9/NPCPart1.png/>
</p>

And if it did, then the NPC widget would trigger to say thank you to the player.

<p align=center>
<img src = Image/Story9/NPCPart2.png/>
</p>

And if the player didn’t have any Notes. It would go to the second branch. This is a check of whether the player has Less than or equal to 0 Notes.

<p align=center>
<img src = Image/Story9/NPCPart3.png/>
</p>

If True, then the NPC would ask the player if they can go gather the notes,
<p align=center>
<img src = Image/Story9/NPCPart4.png/>
</p>

and if the player has more than 1 letter, then the NPC will ask if they found any yet.

<p align=center>
<img src = Image/Story9/NPCPart5.png/>
</p>  



&emsp; In hindsight, I wish I had added a clearer way to let the player know which items they have to pick up with a keyboard. (I also realize I made a small editing error for the NPC dialogue. It was supposed to say ‘pick up by clicking F’)


## Polish

&emsp; Finally, the last step of the project. This meant finally cleaning up. I went back to clean up the code, make the levels look nicer, and properly place the pickable items.

### The Final look of Level One

<p align=center>
<img src = Image/Story10/Level1_FinalLook1.png/>
</p>

<p align=center>
<img src = Image/Story10/Level1_FinalLook2.png/>
</p>

<p align=center>
<img src = Image/Story10/Level1_FinalLook3.png/>
</p>

<p align=center>
<img src = Image/Story10/Level1_FinalLook4.png/>
</p>

<p align=center>
<img src = Image/Story10/Level1_FinalLook5.png/>
</p>


### The Final Look of Level 2
<p align=center>
<img src = Image/Story10/Level2_FinalLook1.png/>
</p>
<p align=center>
<img src = Image/Story10/Level2_FinalLook2.png/>
</p>
<p align=center>
<img src = Image/Story10/Level2_FinalLook3.png/>
</p>
<p align=center>
<img src = Image/Story10/Level2_FinalLook4.png/>
</p>
<p align=center>
<img src = Image/Story10/Level2_FinalLook5.png/>
</p>


### Cleaning up Code

&emsp; I’m still learning how to properly clean up the code.

I color-coded the parts I added to the BP_ThirdPersonCharacter.

<p align=center>
<img src = Image/Story10/ColorCode.png/>
</p>

And the Overall Look of what the Blueprint looks like.
<p align=center>
<img src = Image/Story10/BPThirdPerson.png/>
</p>


I will say that Looking back over the code: I will be looking into how to properly divide the responsibilities and try to utilize Interfaces.

&emsp;  Overall, I say this was a fun project to do. I definitely felt I could have done better, but I’m eager to keep learning and expanding my skillset. I even had my sister play the game at the end. It felt nostalgic to see my sister explore the levels I worked so hard to create. Reminding me of simpler times when we were kids.


## Assets

#### Pickup
* https://hitrison.itch.io/menu-sfx-pack
* https://pixabay.com/sound-effects/film-special-effects-jingling-keys-419578/
* https://pixabay.com/sound-effects/film-special-effects-unlock-deadbolt-102497/
* https://clockworkraven.itch.io/raven-fantasy-icons


#### Footstops
 * https://pixabay.com/sound-effects/film-special-effects-st3-footstep-sfx-323056/
 * https://pixabay.com/sound-effects/film-special-effects-st2-footstep-sfx-323055/
 * https://pixabay.com/sound-effects/film-special-effects-st1-footstep-sfx-323053/
 * https://pixabay.com/sound-effects/film-special-effects-footstep-372877/
 * https://pixabay.com/sound-effects/film-special-effects-footstep-1-83098/

### UI
* https://itch.io/queue/c/7616777/personal-projects?game_id=1313954&password=
* https://free-game-assets.itch.io/free-post-apocalyptic-pixel-art-backgrounds
* https://free-game-assets.itch.io/free-pixel-art-cloud-and-sky-backgrounds


#### Font
* https://yukipixels.itch.io/boldpixels


#### FAB


*Jump To: [Page Top](#introduction), [Landscape](#landscape), [HUD](#hud), [Collectables](#collectables), [Main Menu](#main-menu), [GamePlay](#gameplay), [Sounds](#game-over), [New Level](#new-level), [Game Instance](#game-instance), [NPC](#npc), [Polish](#polish)*
