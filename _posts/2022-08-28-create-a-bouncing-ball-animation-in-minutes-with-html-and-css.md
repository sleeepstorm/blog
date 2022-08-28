 ---
 title: "Creating a bouncing ball animation in minutes with HTML and CSS"
 date: 2022-08-28
 ---

![Title image](https://gifimage.net/wp-content/uploads/2017/10/bouncy-ball-gif-12.gif)
*(Credit: [GIF Image](https://gifimage.net/bouncy-ball-gif-12/))*
 ## Introduction
One of the most iconic things to animate is a bouncing ball and animations can be created using HTML and CSS. Today, let's put our CSS animation skills to test by creating a bouncing ball.

## The Ball

In order to create a bouncing ball, we need a ball to animate so let's create that using HTML and CSS. For the HTML, let's create a `<div>` element:
```
<div class="ball"></div>
```
If you execute the code, You'll see nothing because our `<div>` doesn't have anything to display. Let's change that with CSS. Let's make something appear using CSS:
```
.ball {
    position: relative; /* Will be used later for the animation */
    width: 20px; /* Change this to make the ball wider */
    height: 20px; /* Change this to make the ball taller */
    background-color: red; /* Set this to whatever color you want your ball to be */
}
```
Run the code and you see a... Red square? I thought it was a ball, let's change that by adding the `border-radius` property:
```
.ball {
    position: relative;
    width: 20px; 
    height: 20px; 
    background-color: red; 
    border-radius: 50%; /* Makes the square round */ 
}
```

There we go, now we have a red ball, but wait... It not's moving! Let's make the ball bounce.

## The Bouncing Ball

Let's make the ball bounce using CSS animations. First let's tell our element that it's going to be animated using the `animation` property:
```
.ball {
    position: relative;
    width: 20px; 
    height: 20px; 
    background-color: red; 
    border-radius: 50%;
    animation: bounce 2s forwards;
}
```
We will call our animation "bounce" and it will take 2 seconds to bounce. I used forwards at the end so it bounces only once. If you want it to keep bouncing, change `forwards` to `infinite` at the end. Now let's create the animation:
```
@keyframes bounce {
  0% {
    bottom: 0px;
  }
  50% {
    bottom: -90vh; /* Make it higher if you want it the ball to bounce lower */
  }
  100% {
    bottom: 0px;
  }
}
```
Save the scripts and run the code and the ball should gracefully fall, and gracefully come back up, all in 2 seconds.

## Conclusion
This was a simple project, yet fun to code and I will find a way to make more of these CSS animation projects and upload them on here. If I do they probably will be more site usable and have reasoning
