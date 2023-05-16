---
layout: resource
title: "Manim - simple animation introduction "

description: Manim is a powerful animation tool that is used extensibly by STEM youtubers to animate mathematical concepts. It's integration with python allows you to calculate and display examples within the same script. This is a quickstart guide on how to create Manim animations. 

icon: star-o
people:
  - jeep
---

## Introduction
Are you ready to dive into the exciting world of animation? Look no further! In this quick guide, I'll give you some tips and tricks for getting started with Manim, the powerful Python library for creating stunning animations. With Manim, you can bring complex algorithmic concepts to life. 

After successfully using Manim to visualize the underlying graph structure of the longest increasing subsequence problem as a part of [my LIS video](https://youtu.be/buB-VifgeNE?t=412) ([GitHub](https://github.com/jeeepx/AlgoAnimation)), I want to share some tips and tricks I wish I had known when I first started using the library.

## Getting Started

1. **Pick which version of Manim to use!** <br>
   Interestingly, there are not one but [three versions](https://docs.manim.community/en/stable/faq/installation.html#:~:text=Why%20are%20there%20different%20versions%20of%20Manim%3F%23) of Manim.
   * **[ManimGL](https://github.com/3b1b/manim)** <br>
   This version of Manim is the most updated version, and it is maintained by Grant Sanderson, the creator of Manim and the famous 3b1b YouTube channel. This option is good if you want to learn more about how Manim is built or want to contribute to the project. It is the latest version; It is recommended that you are very experienced in Python to use this option since it is not well documented.
    * **[Manim CE (Manim Community)](https://www.manim.community/)** <br>
   This version of the Manim is a lot more documented and stable, and it is maintained by the community. If you are new to Manim, I would highly recommend this option. Honestly, if your focus is just on making an awesome animation, this version is all you need. There is also more help available online for these options. I also used this version to create my animations.
   *  **[ManimCairo](https://github.com/3b1b/manim/tree/cairo-backend)** <br>
   This is the older version of Manim, and it was discontinued at the end of 2019. There is no documentation for this version. I believe people only use this version to run Grant's older project.

2. **[Installing Manim](https://docs.manim.community/en/stable/installation.html)** <br>
   **Conda** is a package manager or Python that allows you to create and manage isolated environments. I recommend [installing Manim using Conda](https://docs.manim.community/en/stable/installation.html#conda-installation:~:text=Installing%20Manim%20in%20conda%23) because you don't have to install dependencies like FFmpeg, or Pycairo. The process is much shorter than [locally installing](https://docs.manim.community/en/stable/installation.html#conda-installation:~:text=Working%20with%20Manim-,Installing%20Manim%20locally,-%23) it, and it worked out well for me. 

## Creating Graphs

### Graph Construction
One of the main questions I had when starting to create graph-based animation was how to create a graph structure iteratively rather than hardcoding every node. This can be a daunting task, especially when dealing with complex graphs.

Fortunately, I came across [Python locals() function](https://www.w3schools.com/python/ref_func_locals.asp#:~:text=The%20locals()%20function%20returns,information%20about%20the%20current%20program.), which returns the local symbol table as a dictionary. Instead of manually creating each node and assigning its position, I was able to define an array of offsets (for x and y positioning) for each level of the graph and use a simple for loop to create all the nodes. This made my code much more efficient and manageable. Here is an [example code](https://github.com/jeeepx/AlgoAnimation/blob/master/project/Animations/LcsNaiveRecursion.py) from `LCSNaiveRecursion.py`:
```
for level in range(1, 6):
    for node in range(2\**level):
        dist = some numerical value
        cur_node = 'n'+str(level)+str(node+1) 
        locals()[cur_node].shift((dist)*RIGHT) //using locals to reference the variable
```

### Animating the Graph
After we efficiently created the graphs, we will now find out how to show different levels of the graph. [MovingCameraScene](https://docs.manim.community/en/stable/reference/manim.scene.moving_camera_scene.MovingCameraScene.html), as the name suggested, moves the camera around the scene and enables you to show different parts of your graph. 
```
self.camera.frame.save_state() //save the current frame state
self.play(self.camera.frame.animate.set(width=objectToMoveTo.width*3).move_to(locals()['objectToMoveTo']))
//set the width of the frame to be x times the width of "objectToMoveTo" and move the camera to object with name "nodeToMoveTo"
self.wait(1)
self.play(Restore(self.camera.frame)) //go back to the frame we saved
```


## Creating Tables
When creating animations for dynamic programming problems, one common challenge is hardcoding each entry of the table. This can quickly become tedious and prone to errors for large tables.

To avoid this, I wrote out the LCS algorithm and stored the output of the algorithm in a dictionary. This allowed me to easily access the values of each entry without having to hardcode them one by one.

For example, in `LcsDpTable.py`([full code](https://github.com/jeeepx/AlgoAnimation/blob/master/project/Animations/LcsDpTable.py)), I filled up the table from the bottom up and stored the output in a dictionary called "dict." The key for each entry in the dictionary was simply the concatenation of the row and column strings. Later, when adding a background color to each cell, I used the value stored in each key to determine the color code that I should use to represent each condition.
```
        for r in range(2,10):
            for l in range(r,10):
                if r>3:
                        if dict[str(r-1-3)+str(l-2)] > dict[str(r-1-3)+str(r-3)] + 1:
                            table.add_highlighted_cell((r-1,l), color=ORANGE)
                        elif dict[str(r-1-3)+str(l-2)] == dict[str(r-1-3)+str(r-3)] + 1:
                            table.add_highlighted_cell((r-1,l), color=ORANGE)
                            table.add_highlighted_cell((r-1,r-1), color=ORANGE)
                        else:
                            table.add_highlighted_cell((r-1,r-1), color=ORANGE)
```
Another problem I encountered is that I cannot unhighlight a cell once it is highlighted. You can use the following code: `tableName[0].set_opacity(0)`. Here, `tableName[i]` represents the last ith call of add_highlighted_cell  (reverse order). It's important to note that this solution wasn't well-documented in the Manim documentation while working on my project, so I had to rely on external sources to find a solution. 

## Resources
Interestingly, I found most answers to my problem in [r/manim](https://www.reddit.com/r/manim/) Reddit.

## Conclusion
Manim is a powerful Python library that can help you create stunning animations to visualize complex concepts. In this guide, we've covered some tips and tricks to help you get started with Manim, including choosing the right version to use, installing Manim, creating graphs and tables, and animating your creations. I hope this guide is helpful for the readers, and if you have any questions about this guide, feel free to reach me at kchayanid@gmail.com. I am looking forwards to seeing more cool algorithmic animations !

## Examples and Turorials!
- Most of the animations created by our fellow CAs can be viewed [here](CA-created-resources)