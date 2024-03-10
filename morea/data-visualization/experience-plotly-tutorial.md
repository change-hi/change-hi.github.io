---
title: "2. Design Principles for Visualizations"
published: true
morea_id: experience-plotly-tutorial
morea_type: experience
morea_summary: "Design Principles for Visualizations"
morea_sort_order: 3
morea_labels:
  - 2:30pm
---

# 2. Design Principles for Visualizations

<div class="alert alert-info mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Objectives**
* Give you an overview of design principles for visualization.
* Examples of well desinged visuals.
</div> 

### A Little Deeper

Before we talk about contemporary visualization tools, let’s go a little deeper and look into how the human brain interprets visualizations and what are the most fundamental elements (visual encodings) visualization experts and graphic designers manipulate to produce visualizations.

The figure below (from Alberto Cairo’s ["The Functional Art"](http://www.thefunctionalart.com/)) depicts how your brain processes visual information.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/PastedGraphic28.png" alt="viz-intro" caption="" %}

When your brain sees a visualization, it is stored in “Iconic Memory”.

Iconic Memory is a short-term buffer & processor to maintain a coherent picture of the world at all times. It also perceives basic visual attributes like shape, edges, relative size, patches of color. These visual attributes are also referred to as Pre-Attentive attributes. It means you don’t have to think hard to do it. If you know what the brain pre-attentively processes, you can use that to make important data in your visualizations stand out to the user.

Iconic memory’s information is passed to visual working memory. Visual working memory is also a short-term storage (stores about 5 +/- 2 things at a time). Lastly, long-term memory kicks in to associate things in short-term memory to enable comprehension of what you are seeing.

The goal in producing a good visualization is to:
1. take advantage of pre-attentive visual attributes to make important features in the data stand out.
2. not require visual working memory to hold more than 5 +/- 2 things at a time. I.e. you don’t want the user to have to refer to more than 5 encodings to make sense of something.
3. associate it with something that the user might be familiar with from past experience (i.e. relate the data to something from their long term memory). For example, if you wanted to explain to someone that a wind turbine is 853 ft tall, compare it next to something they might know- like Diamond Head, or the Statue of Liberty, or the Empire State Building.

{% include figure.html url="" max-width="90%" file="/morea/data-visualization/fig/wind.png" alt="viz-intro" caption="" %}

Pre-attentive visual attributes - are those that are processed in sensory memory without our conscious thought. It takes our brain less than half a second to process a pre-attentive property of an image. Four basic visual properties that can be defined as pre-attentive include: <strong> Form, Movement, Spatial Positioning and Color.</strong>

Examples of Form include: orientation, curvature, length, width, added marks, numerosity, shapes, size, and spatial grouping.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/PastedGraphic30.png" alt="viz-intro" caption="" %}

Examples of movement include: Flicker, Velocity, Direction.


<div class="text-center">
<img src="/morea/data-visualization/fig/tg_flick.gif" width="32%"/> 
<img src="/morea/data-visualization/fig/tg_vel.gif" width="32%"/> 
<img src="/morea/data-visualization/fig/tg_dir.gif" width="32%"/> 
</div>

Examples of Spatial Positioning include:
* 2D positioning – plotting something on a 2D map;
* Stereoscopic depth - seeing depth by virtue of the fact that we have 2 eyes. As it turns out depth perception is the most rapidly detected preattentive stimulus;
* Concave and convex positioning – being able to see whether something is concave or convex.

{% include figure.html url="" max-width="90%" file="/morea/data-visualization/fig/PastedGraphic32.png" alt="viz-intro" caption="" %}



We often use the word Color to mean a combination of: hue, saturation and value.

* Hue refers to the origin of the colors we can see (red, green, blue, etc).
* Saturation describes the purity/vividness of a hue.
* Value describes the lightness or darkness  of a hue.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/colors.png" alt="viz-intro" caption="" %}

Picking the right color (hue, saturation, value) is a challenging problem for most who are inexperienced in data visualizations, however there are helpful guides available at: [sciviscolor](https://sciviscolor.org/tools/).

{% include figure.html url="https://sciviscolor.org/tools/" max-width="90%" file="/morea/data-visualization/fig/PastedGraphic36.png" alt="viz-intro" caption="" %}

### To Sum Up

This chart below shows the relative accuracy of comparison using various visual encodings [[William Cleveland and Robert McGill1984](https://en.wikipedia.org/wiki/Graphical_perception#cite_note-Cleveland_1993-2)].

{% include figure.html url="" max-width="90%" file="/morea/data-visualization/fig/PastedGraphic37.png" alt="viz-intro" caption="" %}

For color, this paper compares mean error when users view data visualizations using a variety of color mapping schemes [[Bujack2017](https://ieeexplore.ieee.org/document/8017653)]. As summarized in the figure below, the results of the study suggests that Blue-Orange Divergent provides the most resolving power.

{% include figure.html url="" max-width="90%" file="/morea/data-visualization/fig/ComparisonofMeanError.png" alt="viz-intro" caption="" %}

The following figure shows a combustion visualization depicted in a variety of colormaps to illustrate their respective resolving power. Many charting tools like Plot.ly, ParaView, and Tableau support most of these colormaps and also allow you to create your own. Note: the allocation of data values to colors in the colormap need not be linear. For example, if there is a large number of data points  share similar values a linear scale may assign all those data points to the same color. Instead one could assign more colors to those data points to make the details easier to resolve.

{% include figure.html url="" max-width="90%" file="/morea/data-visualization/fig/PastedGraphic35.png" alt="viz-intro" caption="" %}


If you are interested in learning more about data visualization, the University of Hawaii at Manoa and at Hilo offers classes on the subject in the Information and Computer Sciences Department. In the next section we will introduce you to a number of popular visualization tools.

{% include figure.html url="" max-width="90%" file="/morea/data-visualization/fig/Intro-to-Visualization-SHORT.png" alt="viz-intro" caption="" %}


### Tools of the Trade

We don't all have time to become visualization experts so there are a number of tools that can help you get most of the job done.

The ones we are covering are: Plot.ly, ParaView and Tableau.
Again since we have limited time we can only cover the very basics to get you started.

#### Ploy.ly

Plot.ly is a general charting library for producing statistical charts. There are numerous similar tools available (e.g. Matplotlib, Chart.js), however, plot.ly is notable because: it provides an application programming interface for Javascript, R and Python (as well as Jupyter). It also provides Chart Studio- which allows you to produce charts and simple dashboards without programming. And it provides Dash to enable you to create charts as well as fully functioning dashboards purely in Python. Lastly, Plot.ly is free and open source.

{% include figure.html url="" max-width="90%" file="/morea/data-visualization/fig/plotly.png" alt="viz-intro" caption="" %}


#### Paraview

ParaView is a Scientific Visualization tool. The other major scientific visualization tool is [VisIT](https://visit-dav.github.io/visit-website/). Scientific Visualization tools are typically used to represent data that have some form of naturalistic physical representation (e.g. visualizations of air flow around a car, tornado visualizations, visualizations of Magnetic Resonance Imaging scans from the hospital, visualizations of the formation of clusters of galaxies.) Unlike most statistical visualization tools, ParaView and VisIT can run on supercomputers/computer clusters to visualize data sets too large to run on desktop PCs. Both ParaView and VisIT are open source, and ParaView is built on top of the Visualization Toolkit ([VTK](https://vtk.org))- a widely used application programming interface for producing scientific visualizations.


<div class="text-center">
<img src="/morea/data-visualization/fig/carflow.jpeg" width="30%"/>
<img src="/morea/data-visualization/fig/tornadoScreenshot.png" width="30%"/> 
</div>
<hr>

<div class="text-center">
<img src="/morea/data-visualization/fig/cardio.jpg" width="30%"/> 
<img src="/morea/data-visualization/fig/cluster.jpg" width="30%"/> 
</div>

#### Tableau

Tableau is a relatively new tool. It is also a statistical visualization tool. We are including Tableau in our workshop because it is fast becoming popular in the commercial sector. For example, First Hawaiian Bank uses Tableau. Unlike plot.ly, which has multiple use modalities (application programming interface, no-code interface), Tableau is a standalone application like Microsoft Excel. Tableau is a commercial product, so it is not free, although students and faculty can get a free annual licenses.

{% include figure.html url="" max-width="90%" file="/morea/data-visualization/fig/tableau.png" alt="viz-intro" caption="" %}

Lastly, for geospatial visualization (anything to do with maps), the most well known tool is ESRI's [ArcGIS](https://www.esri.com/en-us/arcgis/about-arcgis/overview). It is an commercial tool, which is free to students and faculty. Most government agencies uses ArcGIS' suite of products.

If you prefer to use an open source tool, we recommend taking a look at [QGIS](https://www.qgis.org/en/site/). Unfortunately we will not be able to cover geospatial visualization tools in this workshop.

### Just One More Visualization
Below are two visualizations produced by [W.E.B. Du Bois](https://en.wikipedia.org/wiki/W._E._B._Du_Bois), sociologist, author, advocate, historian, and co-founder of the [NAACP](https://naacp.org). He was also the first African American to earn a doctorate (graduate studies at University of Berlin and Harvard University) and became a Professor of history, sociology, and economics at Atlanta University.

<div class="text-center">
<img src="/morea/data-visualization/fig/W.E.B._Du_Bois_by_James_E._Purdy,_1907.jpg" width="25%"/> 
<img src="/morea/data-visualization/fig/duboisian-viz-toolkit-hero.jpg" width="70%"/> 
</div>

Du Bois and his students developed 63 hand-drawn diagrams for the 1900 World's Fair to showcase the success of black Americans despite facing pervasive racism in the U.S. and globally.

The one on the left shows the value of taxable property owned by blacks in Georgia from 1875-1800. It uses color and shape to create an optical gravity well toward the center of the image. The shards help the user understand that the outer circles extends through to the center of the circle, as well as draws viewers' eyes towards it. Property value is represented by the differences in radii. Perhaps for more accurate depiction (to minimize visual distortion often produced when using volumes) the areas should be scaled to appropriately represent the property values instead. However the distortion may have been intentional to enhance the evocativeness of the visualization.

<div class="text-center">
<img src="/morea/data-visualization/fig/service-pnp-ppmsca-33800-33884v.jpg" width="45%"/> 
<img src="/morea/data-visualization/fig/service-pnp-ppmsca-33800-33888v.jpg" width="45%"/> 
</div>

The graphic on the right shows the occupations of Georgia black males over 10. Notice the curved bar at the top. If the bar was entirely linear, proportionally the bars below it would have been 1/3 smaller and more difficult to see. Also note the summary of smaller occupations showing that, together they produce a significant contribution to overall employment.

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>
There are useful guidelines that one can use to select appropriate charts and visual encodings, and there are tools that will help you create those charts. However, the creation of novel forms of visualization is as much science as it is craft.

Design of visualizations is key to their effective communication of results.
</div>

{% include next-button.html 
           top-label="3. Creating Visualizations with Code ->" 
           bottom-label="2:45pm" 
           url="/morea/data-visualization/experience-paraview-tutorial.html" %}
