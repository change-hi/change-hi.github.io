---
title: "1. Introduction to Data Visualization"
published: true
morea_id: experience-introduction
morea_type: experience
morea_summary: "Introdce the idea of visualizations"
morea_sort_order: 3
morea_labels:
  - 2:00pm
morea_enable_toc: true
---

# 1. Introduction to Data Visualization

<div class="alert alert-info mt-3" role="alert" markdown="1">

<i class="fa-solid fa-book-open fa-xl"></i> **Learning Outcomes**
<hr/>
This workshop will enable you to:

* understand the role of data visualization in the research enterprise;
* increase your awareness of what makes good and bad visualizations;
* know basic steps for creating effective visualizations;
* know about contemporary tools for creating visualizations. 

<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>
Data Visualization is a vast field so it would be impossible to cover everything in a 2-hour workshop. Like literacy, good data visualization takes years to master.

So this workshop is intended to introduce you to data visualization by:

1. Giving you an example of a good visualization;
2. Increasing you awareness of common visualization mistakes;
3. Providing you with tips on how to approach creating more effective visualizations;
4. Providing you with a source for good visualizations for you to aspire to;
5. Introducing you to contemporary tools.
</div>

Data visualization is the representation of data through use of graphics, such as charts, infographics, and animations.
The goal is to communicate complex data relationships and data-driven insights in a way that is easy to understand.

Visualization can be applied throughout your entire research workflow to help you:
1. find problems with the data early in the gathering process, so you can correct the problem before wasting time collecting potentially erroneous data.
2. comprehend large amounts of data.
3. see both large-scale and small-scale features to understand the “forest for the trees.”
4. discover unanticipated emergent features.
5. answer questions about the data.
6. ask new questions or form new hypotheses about the data.
7. tell stories about the data to others, such as to lay audiences.

### An Example of a Good Visualization
The figure below shows a visualization made by [Charles Joseph Minard](https://www.paraview.org/) in 1861 depicting Napoleon’s losses during his 1812 march to and from Moscow, from Lithuania.
This is a compelling visualization because it is able to depict 5 pieces of information in one image:
1. the size of the thick tan line shows the size of Napolean’s army, its location, and time during their march to Moscow (on the right).
2. the thick black line shows the same for the return journey.
3. the location of major river crossings.
4. the temperature on the return journey.
5. the direction of the movement of the army and when armies separate and rejoin.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/PastedGraphic3.png" alt="plotly" caption="" %}

### Some Examples of Bad Visualizations
Now let’s take a look at a few common visualization mistakes, starting with Tables.
To most people the following table looks fine. To a visualization expert there are many things that can be done to make it easier to interpret.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/nielson.png" alt="plotly" caption="" %}

Here is a better version of the table:

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/nielson2.png" alt="plotly" caption="" %}

Several rules have been applied to improve the presentation of the table. They are:
1. The results should not show greater accuracy than the original measurements. Don’t let Excel etc add on extra digits.
2. The numbers should only show enough precision for the audience to see the trend – more digits can obscure that trend.
3. Space padding for improved readability.
4. Right justify numbers to make magnitudes easier to compare.
5. Left justify text.
6. Align decimal points.

For graphs (e.g. line graphs):
1. Just because a charting program produces a chart does not necessarily mean it is a good chart. Below is a chart made by an old version of Microsoft Excel.
2. Make sure the graph lines and glyphs are easily visible for the target medium (e.g. print, or presentation on a projector). Even though a chart may look fine on a computer screen, it may not be clearly visible when projected on a screen, or seen at the back of a large auditorium.
3. Avoid simply using the typical fully saturated color values: e.g. red (255,0,0), green (0,255,0), blue (0,0,255), cyan (0,255,255), magenta (255,0,255), yellow (255,255,0). These colors are typically used on older computers with limited color palettes. Modern computers are equipped with over 16 million colors to choose from.
4. Make sure the chart has units, a legend, labels for the axes and a title.
5. Make sure numbers don’t have extraneous significant digits.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/PastedGraphic4.png" alt="plotly" caption="" %}

6. Try to avoid using 3D in charts. They look pretty but they make it harder to compare data. Here are some examples:
In this 3D piechart the 29% looks bigger than the 35%.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/3dpie.png" alt="plotly" caption="" %}

The following chart distorts the depiction of data not only because it uses 3D but because the population axis does not start at zero.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/3dbar.png" alt="plotly" caption="" %}

The chart gives the impression that the population in the US has been increasing dramatically from 2000 to 2007.
Compare this against the less dramatic representation below where zero is included in the vertical axis. Also note, in this representation commas have been included to make the interpretation of the population numbers easier.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/2dline.png" alt="plotly" caption="" %}

Often when presenters present a chart they expect the viewer to be able to instantly interpret it. This is never the case.

To ensure they truly understand your chart you need to:
1. give them time to read and interpret the axes of the chart, as well as time to see the trend in the chart.
2. include a short sentence describing the graph’s conclusion, in addition to the title.

For example. If I were to present the following chart to an audience I might say:
“This is a chart comparing power/weight ratio and lap times for 19 cars driven around the Laguna Seca race track. The vertical axis shows the power to weight ratio of the car- bigger values are better. The horizontal axis shows the time per lap- smaller values are better. This chart shows that you achieve the best lap times with cars that are lighter and more powerful.”

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/Comparison_of_PowerWeight_Ratio.png" alt="plotly" caption="" %}

Pie chart are popular in financial reports. But in truth they are one of the worst types of charts to use.

Pie charts are only good for comparing 2 to 3 different data points whose values are very different.


{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/Pie-I-have-Eaten.jpg" alt="plotly" caption="" %}

They are poor for comparing between themselves.

For example, let’s say the following 3 pie charts show the votes for 5 candidates in 3 polling stations. Notice how the orientation of the pie wedges make them difficult to compare between the 5 candidates.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/rowofpie.png" alt="plotly" caption="" %}

Now look at the same data when simply plotted on bar charts. The differences between the candidates and polling stations are instantly apparent.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/rowofbar.png" alt="plotly" caption="" %}

As it so happens, a pie chart is also poor for comparing between itself.
For example in this chart, how much bigger is Pinot Grigio and Tempranillo?

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/winepie.png" alt="plotly" caption="" %}

Notice that to answer my question your eyes have to move to the legend then find the corresponding pie slice in the chart. Then you had to try and compare the size of the slices accounting for their differing orientation.

Now instead compare it against a simple bar chart:

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/winebar.png" alt="plotly" caption="" %}

You can quickly estimate that the answer is about 3 times.

Using the wrong font (with poor kerning- space between letters in a font) can have catastrophic, if not amusing effects.

<div class="text-center">
<img src="/morea/data-visualization/fig/bad-letter-spacing-4__605.jpg" width="45%"/> <img src="/morea/data-visualization/fig/funny-importance-of-kerning.jpg" width="45%"/> 
</div>
<!-- {% include figure.html url="" max-width="70%" file="/morea/data-visualization/fig/bad-letter-spacing-4__605.jpg" alt="plotly" caption="" %} |  {% include figure.html url="" max-width="70%" file="/morea/data-visualization/fig/funny-importance-of-kerning.jpg" alt="plotly" caption="" %} -->

<hr/>

Here are some simple rules of thumb to help you choose fonts:
1. Generally Sans-serif fonts (e.g. Helvetica, Arial) are good for on-screen text.
2. Serif fonts (e.g. Times, Georgia) - are good for printed text (because print often has more resolution than computer screens).
3. Monospace fonts (e.g. courier) are good for when you need exact alignment of text characters (e.g. source code or numbers in tables).
4. Stylish fonts are best left for party invitations.
5. Lower case words are read faster than words than upper case.
6. Individual letters and nonsense words like UA1138 are read faster in upper case.

Fonts can also evoke different emotions. Here's a brief guide:

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/Psychology_Behind_Type.jpg" alt="plotly" caption="" %}

{% include next-button.html 
           top-label="2. Paraview Tutorial ->" 
           bottom-label="2:40pm" 
           url="/morea/data-visualization/experience-paraview-tutorial.html" %}
