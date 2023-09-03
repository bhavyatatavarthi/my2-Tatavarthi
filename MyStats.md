# Bhavya Tatavarthi
I am Bhavya Tatavarthi. I love playing chess and that's my favourite hobby. I completed my BTech in Electrical and electronics Engineering at India. After coming to united states, I started to play tennis and learning more about coding as my major in masters is Applied computer science.

![Image](bhavya.jpg)
[Hello](README.md)

***
# Sports
The table below consists of columns which contains different names of the sports, reason why I recommend it and how many hours in a week I would spend participating in the
sport.<br>

| Sports | Reason | Hours |
|---|:---:|---| 
|Cricket|Physical fitness|15|
|Tennis|Strengthens muscular endurance|20|
|BasketBall|Develops fundamental movement skills|10|
|Golf|Mental Relaxation|25|
---
# Quotes
>"The important thing is not to stop questioning." -*Albert Einstein*

>"The more I learn, the more I realize how much I don't know." - *Isaac Newton*
---
# Snippets
>Is it possible to position items around the circle?
[stackoverflow](https://stackoverflow.com/questions/34827096/is-it-possible-to-position-items-around-the-circle)<br>

The Mixin
```
/// Mixin to place items on a circle
/// @author Kitty Giraudel
/// @author Ana Tudor
/// @param {Integer} $item-count - Number of items on the circle
/// @param {Length} $circle-size - Large circle size
/// @param {Length} $item-size - Single item size
@mixin on-circle($item-count, $circle-size, $item-size) {
  position: relative;
  width:  $circle-size;
  height: $circle-size;
  padding: 0;
  border-radius: 50%; 
  list-style: none;       
  
  > * {
    display: block;
    position: absolute;
    top:  50%; 
    left: 50%;
    width:  $item-size;
    height: $item-size;
    margin: -($item-size / 2);
  
    $angle: (360 / $item-count);
    $rot: 0;

    @for $i from 1 through $item-count {
      &:nth-of-type(#{$i}) {
        transform: 
          rotate($rot * 1deg) 
          translate($circle-size / 2) 
          rotate($rot * -1deg);
      }

      $rot: $rot + $angle;
    }
  }
}
```
Demo
```
<ul class='circle-container'>
  <li><img src='http://lorempixel.com/100/100/city' alt="..." /></li>
  <li><img src='http://lorempixel.com/100/100/nature' alt="..." /></li>
  <li><img src='http://lorempixel.com/100/100/abstract' alt="..." /></li>
  <li><img src='http://lorempixel.com/100/100/cats' alt="..." /></li>
  <li><img src='http://lorempixel.com/100/100/food' alt="..." /></li>
  <li><img src='http://lorempixel.com/100/100/animals' alt="..." /></li>
  <li><img src='http://lorempixel.com/100/100/business' alt="..." /></li>
  <li><img src='http://lorempixel.com/100/100/people' alt="..." /></li>
</ul>
```
```
.circle-container {
  @include on-circle($item-count: 8, $circle-size: 20em, $item-size: 6em); 
  margin: 5em auto 0;
  border: solid 5px tomato;
  
  img { 
    display: block; 
    max-width: 100%; 
    border-radius: 50%;
    filter: grayscale(100%);
    border: solid 5px tomato;
    transition: .15s;
    
    &:hover,
    &:active {
      filter: grayscale(0);
    }
  }
}
```
[placing items on circle](https://css-tricks.com/snippets/sass/placing-items-circle/)





