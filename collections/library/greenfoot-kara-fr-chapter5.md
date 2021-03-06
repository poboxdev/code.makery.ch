---
layout: article
title: "GreenfootKara - Chapitre 5: Méthodes"
date: 2014-07-10 00:00
slug: greenfoot-kara/fr/chapter5
canonical: /library/greenfoot-kara/chapter5/
github: https://github.com/marcojakob/code.makery.ch/edit/master/collections/library/greenfoot-kara-fr-chapter5.md
published: true
prettify: true
comments: true
sidebars:
- header: Articles de cette Série
  body:
  - text: "Introduction"
    link: /library/greenfoot-kara/fr/
    paging: Intro
  - text: "Chapitre 1: Premiers Pas"
    link: /library/greenfoot-kara/fr/chapter1/
    paging: 1
  - text: "Chapitre 2: Ordinogramme"
    link: /library/greenfoot-kara/fr/chapter2/
    paging: 2
  - text: "Chapitre 3: Variables"
    link: /library/greenfoot-kara/fr/chapter3/
    paging: 3
  - text: "Chapitre 4: Jeu Sokoban"
    link: /library/greenfoot-kara/fr/chapter4/
    paging: 4
  - text: "Chapitre 5: Méthodes"
    link: /library/greenfoot-kara/fr/chapter5/
    paging: 5
    active: true
  - text: "Solutions Chapitre 5"
    link: /library/greenfoot-kara/fr/chapter5-solutions/
    icon-css: fa fa-fw fa-check-square-o
- header: Downloads
  body:
  - text: scenarios-chapter-5.zip
    link: https://github.com/marcojakob/greenfoot-kara/releases/download/v2.1.1/scenarios-chapter-5.zip
    icon-css: fa fa-fw fa-file-archive-o
  - text: Page as Word File
    link: /library/convert-web-page-to-word/
    icon-css: fa fa-fw fa-file-word-o
- header: Languages
  languages: true
  body:
  - text: English
    link: /library/greenfoot-kara/chapter5/
    icon-css: fa fa-fw fa-globe
  - text: Deutsch
    link: /library/greenfoot-kara/de/chapter5/
    icon-css: fa fa-fw fa-globe
  - text: Français
    link: /library/greenfoot-kara/fr/chapter5/
    icon-css: fa fa-fw fa-globe
    active: true
---

<div class="alert alert-warning">
  <i class="fa fa-language"></i> This page needs a French translation. If you'd like to help out please read <a href="/library/how-to-contribute/" class="alert-link">how to contribute</a>.
</div>

<div class="row">
  <div class="col-sm-6">
    <img alt="Rotkäppchen" src="/assets/library/greenfoot-kara/chapter5/red-riding-hood.jpg">
  </div>
  <div class="col-sm-6">
    <p>
      <em>Once upon a time, there was a little girl who always wore a red riding cloak. So everyone called her Little Red Riding Hood. One moning the mother said to the child: "Red Riding Hood, today is your grandmother's birthday.Bake her favorite cake, take a bottle of good old wine from the cellar, put everything in one basket, and go visit her."</em>
    </p>
    <p><strong>Help Little Red Riding Hood bake a cake! Carefully read the theory first.
    </strong></p>
  </div>
</div>


## Method with Parameters

With parameters, values can be passed to a method. In the following method you can specify how many steps Kara should take:

<pre class="prettyprint lang-java">
public void multiMove(int steps) {
    int i = 0;
    
    while (i &lt; steps)     {
        move();
    
        i = i + 1;
    }
}
</pre>

To go 5 steps just put the number 5 between the parentheses:

<pre class="prettyprint lang-java">
multiMove(5);
</pre>

To invoke a method with multiple parameters, the values are separated by commas.

<pre class="prettyprint lang-java">
drawRectangle(21, 4);
</pre>


#### Explanation

1. In previous programs it was rather cumbersome to always write the parentheses `()` for each method. Now it is clear that the previously used methods were merely cases where no parameter was passed.
2. Inside the parentheses of a method declaration, the parameter (in this case `steps`) is specified with a type (here `int`). Multiple parameters are separated by commas as seen in this example:   
<pre class="prettyprint lang-java">
public void drawRectangle(int width, int height)
</pre>
3. When such a method is called, the values are copied into the variables (in this case into `width` and `height`).


### Baking the Cake

We will now use Kara to "bake" a birthday cake for the grandmother. The cake will be made of leafs.

Open the scenario **Kara 501 ...** from the folder **scenarios-chapter-5**.

In preparation for baking, the following methods are provided:

1. `public void turnAround()`   
Kara rotates by 180 degrees.

2. `public void multiMove(int steps)`   
Kara takes the number of steps in the current direction (see example in theory section above).

3. public void putLeafs(int count)`   
Kara puts the specified number of leafs. The first one he places at the current position, the other fol-lowing in his line of sight.


#### <i class="fa fa-rocket"></i> TASK 5.01: Baking a Cake

![TASK 5.01](/assets/library/greenfoot-kara/chapter5/task01.png) 

Kara draws a rectangle with leafs symbolizing the cake. Kara starts in the lower left corner and looks to the right.

Kara should be able to make a **rectangle with variable width and height**! 
The method call `drawRectangle(21, 4)` should therefore create a rectangle with width 21 and height of 4.


#### <i class="fa fa-rocket"></i> TASK 5.02: Candles on Cake

![TASK 5.02](/assets/library/greenfoot-kara/chapter5/task02.png) 

To make the cake look like a birthday cake it needs a few candles, of course. Extend your program with an additional method `drawCandles(int count)` which sets the specified number of candles on the cake. 


***

## Methods with Return Values

A method can return a value as a result. The following method will create a random number (between 0 and 9) and return the result:

<pre class="prettyprint lang-java">
public int randomNumber() {
    int random = Greenfoot.getRandomNumber(10);
    return random;
}
</pre>


The result can either be stored in a variable or directly be used as follows:

<pre class="prettyprint lang-java">
multiMove(randomNumber());
</pre>


#### Explanations

1. The type of the return value (in this case `int`) is specified before the name of the method. If the method does not return a value, we write `void`.
2. To return a value we write `return` followed by the value.


#### <i class="fa fa-rocket"></i> TASK 5.03: Candles for Age

We want to put on the cake a **candle for every decade** of grandmother's age. As Little Red Riding Hood does not know exactly how old her grandmother is, she must first ask her mother.

Your program should place the right number of candles on the cake after asking about how old grandmother is.

**Hint:** The following method can be used to ask fort the age. It returns an `int`): 
<pre class="prettyprint lang-java">
intInput("Message...")
</pre>


#### <i class="fa fa-rocket"></i> TASK 5.04 (advanced): Layered Cake

![TASK 5.04](/assets/library/greenfoot-kara/chapter5/task04.png) 

Let Kara bake a layered cake for the grandmother. Kara should add a layer for every decade that the grandmother is over 50. Each layer should have two lines and is indented on both sides by two leaves.


***

## The End and How to Continue

Congratulations, you've reached the end of this series!

Here are some options of how you could continue with your programming adventure:

* *Option 1:* Develop a custom project with [Greenfoot](http://www.greenfoot.org)
* *Option 2:* Start using a professional development environment like Eclipse, Netbeans, etc. (see [GameGridKara](/library/gamegrid-kara/))
* *Option 3:* Start [GUI-programming with JavaFX](/java/javafx-2-tutorial-intro/)


### Feedback

I'd love to hear from you. Let me know when you successfully completed this series or when you have some suggestions. <a href="#disqus_thread"><i class="fa fa-comment-o"></i></a>

<i class="fa fa-beer"></i> Marco
