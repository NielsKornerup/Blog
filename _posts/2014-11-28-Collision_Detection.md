---
layout: default
title: Collision Detection
excerpt: During Thanksgiving break, I started a Natural Selection simulator.
---

About three days ago, I decided that it was time for me to start another project, as I have been spending the last couple of weeks improving my older ones. Thinking about different options, I eventually settled on a simulator that would demonstrate the principles of natural selection from a logical point of view. Objects are divided into three types: producers, herbivores, and consumers. Producers require no energy and cannot move. They use pollen to create offspring. Herbivores move around and eat producers, and consumers eat herbivores. The idea is to have different genes within the population (such as reproduction rate, size, metabolism rate, etc), and have inheritance with a small room for mutations. Over time, lifeforms with "bad" genes will be consumed, or starve, and those with "good" genes will be able to pass them on, like Darwin discussed in his on the origin of species. After spending some time on this project, I successfully got plant reproduction working; however, in order to test for collisions between pollen and plants, I had to compare every pollen grain to every plant in each frame. Combined with the fact that I am using a five year old computer, this made the rendering speed very slow, and the animation choppy. To fix this, I figured out how to optimize collision detection.

The simplest way to do collision detection is to check all objects against all objects, but this has a run time of O(nk) where n and k are the two numbers of objects in question. Sadly, from a notation perspective (and to the best of my limited knowledge), this is the most efficient possible time to do such calculations. Despite this, there is no point in checking if objects on the opposite sides of the screen collide in each frame, as there is no way they could travel such a distance in such a short time. Using this, I can optimize my collision detection via [bounding boxes](https://en.wikipedia.org/wiki/Minimum_bounding_box). By dividing the screen up into smaller parts, and then determining which part an object could collide with the selected one in, we can save the redundancy of checking if particles on opposite sides of the screen are touching. Despite not actually causing an improvement in algorithm efficiency (it is still O(nk) in worst case), this process optimized my code, allowing for my computer to handle larger numbers of potential collisions. If you want to check out my code, it is on [Github](https://github.com/NielsKornerup/selection). I apologize that it is currently a little bit unreadable, but I plan to work on that in the near future. I hope to give you another update once this project is closer to completion.