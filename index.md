## Abstract:

In the new corporate world, time is everything. An optimized way of working is vital. Similarly, in Computer Science an algorithm that is practical, easy and best solves the problem is necessarily not optimal if it runs in exponential time. Nevertheless, an algorithm that is more complex but solves the same problem in constant time is more valuable. Therefore, generating an optimal solution to any problem in any field is fundamental to our life. Finding the shortest path falls in the same line, being crucial to spatial analysis and wayfinding tasks. When you are driving from City A to City B using Google maps, Google maps automatically routes you to the path that takes the least time to reach the destination. This routing is based on the problem of finding the shortest path. This problem is also used to compute the shortest path on the road networks of the USA and Europe. In the field of networking, the shortest path algorithm is used to find the minimum delay. The other applications of this problem include Robotics, VLSI, and transportation. 

## Introduction:

## Previous Work:
James A. Storer and John H. Reif presented an algorithm in 1992 that finds the shortest path between two points through obstacles comprising of minimum length sub paths in O(kn) time complexity, where n is the number of edges in the obstacles and k is the number of connected components in the graph built [1]. They also find the shortest path considering the movement of a circular disk. 
Danny Z. Chen and Haitao Wang formulate the same path finding problem between obstacles, but they do it with curved obstacles called splinegons, instead of polygons [2]. Infact, polygons are special splinegons. If each edge of a polygon is replaced by a convex curve, it can be called as a splinegon. A sub algorithm also gives an efficient way of computing the Voronoi diagram of the convex splinegons.
Insu Hong develops a graph which is sure to contain the solution to the Euclidean Shortest Path problem [3]. He calls it the convex-path algorithm and claims that builds graph that finds the Euclidean Shortest Path more efficiently as compared to a visibility graph or a local visibility graph. He has also implemented multi-core CPU parallelization to make the convex-path algorithm efficient even in big data environments. 

## Methodology:
There are many aspects to be considered before starting off with the implementation. The UI has to be designed since that is the primary source of our inputs. Those inputs have to be integrated well in the code in the sense that the data structures must comply with them. The flow of the algorithm has to be pre-decided so that there don’t have to be any changes made in the previous modules of code at any point in the future. The sub-algorithm for every module along with its time complexity also has to be fixed ahead of time. Once the algorithm has been implemented, the UI that was used to get inputs in the first stage will have to read in the final output and show visual results.
In our implementation, we have let the object moving from start to destination be a disk object instead of a point object. Since the object is something of a bigger size while we are dealing with Cartesian coordinates to find Euclidean distances, there had to be some alterations made to the algorithm to have the final visualization look captivating to the eye, else the moving object would overlap all the edges of the polygons. The shortest path between obstacles would always lie along the edges of the polygons leaving no cushion in between. Since we have considered a disk-like object, we had to inflate the polygons by the size of the radius of the disk in every direction outwardly in a way that it compensates for the size of the object. After inflating the polygons and obtaining those new vertices, the disk object can be considered as a point object for the further implementation. However, the inflated vertices of the polygon are only for implementation purposes. The final visual output will show the polygons initially drawn by the user itself along with the animation of the circular disk moving along the shortest path from start to destination. The following steps elaborate on the sub-modules that our implementation comprised of:

1. **Draw polygons in the UI window and read input vertices**

The UI has been implemented using the Swing GUI widget toolkit for Java. The guidelines to be followed are listed right above the canvas. There are a number of buttons provided for efficient functionality. The user can built polygons with mouse clicks on the points where he wants to have a vertex of the polygon and when the last vertex has been plotted, he can close the polygon by clicking on the “MAKE” button which which draw an edge between the first vertex of that polygon and the last vertex just plotted. The user will not be able to proceed if there are two or less than two vertices plotted for a polygon. A polygon needs to have three or more vertices to be closed. 
Our algorithm needs the points to be plotted in an anti-clockwise fashion. The validations of the UI are such that it will not let the user proceed until two or more polygons have been drawn. Once the polygons have been drawn, the user can click the “FINISH” button to indicate that he has finished drawing the polygons. It will not let the user pass through this if the last polygon has not been closed. 
Once the polygons drawn pass through the previous validations, the user can choose the radius of the disk (which is 20 by default) and then select the start and the destination point for the disk object by clicking on the start point and dragging the cursor further without releasing it until the destination point is reached. After that there is a button called “FIND SHORTEST PATH” that starts running the core algorithm. This button will not be valid to be clicked until the start and destination points are fixed else it will give the user a warning in a dialogue box. The click of that button will continue with the steps mentioned further in the algorithm.






Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/dhavalc25/dhavalc25.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
