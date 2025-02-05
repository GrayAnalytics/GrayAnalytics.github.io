# Object-Oriented Design Patterns: Strategy  

### OO Designs  
Was recently taking an Object-Oriented Software Development class. In the spirit of 'Learning Out Loud' I figured the design patterns would be an interesting blog series.  

### Educators  

My primary source for this is a college course. Suggested reading includes...  
 * Object-Oriented Design and Patterns, 2nd edition, Horstmann, John Wiley & Sons, 2005. ISBN: 978-0-471-74487-0  
 * Head First Design Patterns, Freeman, O'Reilly Media, 2004. ISBN: 978-0596007126

### Strategy Design    
First up, we'll look into **Strategy Design**  
This design is good for situations where you have an action that could be performed different ways.  

Think of guards in a video game. They have the _Patrol_ function. But different guards may patrol in different ways, or need to change how they patrol.  
1. Follow a set path through an area.  
2. Randomly patrols an area. Randomly turning when he walks into something.  
3. Investigates an area.  
4. Chase    

A guard could start patrolling a set path, but what if he see's the game's hero?  
We'd need him to change to _Chase_. And then when the hero successfully hides, the guard should switch to _Investigate_.  
With the Strategy Design, we can change a guard's patrol strategy whenever we want.  
Let's look at the UML.  

<div class="images">
  <img src="/assets/images/2018-05-20-Object_Oriented_Design_Patterns_Strategy/01_UML.PNG">
  <div class="label">
    Strategy UML
  </div>
</div>  

In our example, the _Client Class_ is guard.  
They have a Strategy object, through which we perform the _Patrol()_ function.  
_Follow a Path_, _Randomly Patrol_, _Investigate_, and _Chase_ would each be a separate Concrete Strategy.  
Each ConcreteStrategy would have separate code for its _Patrol()_ function.  
 * _Random Patrol_'s Patrol() function would randomly choose a directin to walk.
 * _Chase_'s Patrol() function would move the guard directly towards the hero.  
 * etc  

So the guard's strategy object would start

> Strategy  strategy = new FollowAPath();    

After they see the hero, we would then change the strategy.  
> strategy = new Chase();  

Now the guard can continue using  
> strategy.Patrol();  

but the gaurd's actions have now changed.  

And that's the basics of the _Strategy Design Pattern_  



