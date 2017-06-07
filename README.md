# P6

~SUMMARY~

Prosper is a company which facilitates peer-to-peer lending. The interactive graphs I created show how the number and size of loans made each month changed over four years of operation.

The primary purpose of the visualisation(s) created is to show how Prosper became more dependent on high-multiple-of-debtors'-monthly-pay loans as it grew in size and popularity. Secondary purposes are to highlight the cap imposed on loans in 2013 (starting May 2013, loans of more than 3x monthly income almost vanish), and to show how the numbers change when you keep score with loans made instead of money loaned (example: in Feb 2014, loans of less than 2x debtors' monthly income made up ~1/2 of loans made but only ~1/3 of money loaned).

~DESIGN~

-Initial Design Decisions-

The initial design was very different to the final output, due to the large amount of feedback and trial-and-error incorporated into plans.

The first design would have drawn coloured rectangles for the different categories of loan; height indicating average loan amount for the category, width indicating number of loans made, and area therefore indicating the total money loaned out in that category per month. An initial animation of the changes over time would have been shown, followed by giving the reader the opportunity to go back through it to view individual months (martini-glass narrative structure).

The first feedback session suggested that this was overcomplicated and hard to unambiguously explain, and that a stacked line chart would be easier to read.

-Final Design-

This section will work through the features of the final visualisation(s) in approximately the order they would appear to a viewer.

The first, main graph shows both the key points: Prosper's explosive - if unsteady - growth, and its increased dependence on high-proportion-of-monthly-income loans. A stacked line chart was chosen over stacked bar as the x-axis (time) is a continuous quantity.

The phrasing used for the key is very inelegant, but it was the only short phrase which unambiguously communicated how loan categories worked. A smoother but less clear phrase was replaced with this one after the final round of feedback.

There is a fine line to walk regarding chart colours. On one hand, the categories involved are sequential, so the colours involved should follow a sequence in order to acommodate that. But they need to be distinct enough that the viewer will pay more attention to them than to the total trend (the last two rounds of feedback brought up that viewers tended to focus on the overall trend more than intra-category changes). The compromise used here is a variation on a diverging 'temperature' colour palette. Larger and riskier loans are assigned more 'dangerous' colours, like orange and red. The top category is given a darkish red, while all the others are light; this represents the category's unique character ("4+" is a conceptually different kind of category to "3 to 4"), and draws the viewer's eye to it.

The stacked bar chart makes it hard to read exact values. To compensate, when the viewer hovers the mouse over a datapoint in the graph, a custom tooltip shows the month and total money loaned for the loan category in question. The exact number of dollars loaned is given, since the standard rounding eliminated too much information; the numbers are comma'd (95673 -> 95,673 etc.) to reduce the chances of misreading orders of magnitude. Custom tooltips are also present in the other three graphs.

The hover mechanism is never explicitly explained, but the viewer knows the graph is interactive, and datapoints are ubiquitous enough (and large enough) that waving the mouse over the graph will consistently reveal one. One piece of feedback was that the tooltip could appear when hovering over the fill instead of the datapoints, but the benefits of this approach were gained more easily by making the circles involved larger.

Below the chart is a 2x2 table of buttons which let the user view three other graphs of the same data. The main graph shows all the key points, and serves as a good introduction to the scenario, so the reader could just read the first graph; or, they could go through the other three graphs to make things clearer (low-tech martini-glass narrative structure). The suggested reading order for the graphs is indicated on the buttons.

(An early plan was to store the graphs themselves in a large 2x2 table, but this idea was nixed in the first feedback session)

The second graph shows variation in proportions of loans. This clarifies, and draws the viewer's attention to, the most important finding: Prosper's proportion of money loaned changing over time. The second feedback session suggested this was clear from the first graph, but I disagree: the second graph shows proportions with a fidelity the first couldn't, due to the small scale at the start and the overall motion throughout. It also makes clearer exactly how sudden and thorough the capping of "4+" loans was.

The third and fourth graphs don't communicate key findings, and exist mostly to give the viewer more choices. They do hit one of the secondary points given in the summary: showing how keeping score with people instead of money gives different results.

~FEEDBACK~

OSMOND, osmondwang19@gmail.com (on conceptual design):

-Start with one graph. A 2x2 table of graphs would not be a good idea.
-Having a second graph which varies based on mouse position in the first is a clever thought.
-Consider using a graph which shows the percentage value instead of absolute value, making changes in proportion clear.
-(Not explicitly said by Osmond) Took too long to make sense of main graph, even with axes labelled and me explaining it. Main graph should probably become secondary.

CHRIS (on first stable build):

-The key needs reversing: start with the 0-to-1 interval.
-Fix up units.
-Numbers in the key lack explanation.
-Default colours would be okay if ordered correctly (green to red), though current plans for changes in colour are sensible. Either way, giving the highest category a qualitatively different colour to indicate open-endedness makes sense.
-No need for dots at datapoints; clear enough from data where months are.
-Changes in relative share are clear enough from the graph. No need for one which keeps score with percentages.
-Animation should happen when you hover over an area, not a line.

TINA (On mostly-finishing first graph):

-Key language ambiguous. "Loans categorised as multiples of debtors' monthly incomes" better; awkward, but clear.
-Write short explainer about Prosper up top.
-Motion in total more interesting than motion between colours.
-Colours too similar! Turn up saturation, seperate them more. ESPECIALLY if the more interesting thing is the differences between categories.
-Total Loaned -> Total Loaned Per Month.

~RESOURCES~

http://stackoverflow.com/questions/22188162/adding-timeaxis-with-dimple-js#22203359

http://www.d3noob.org/2012/12/formatting-date-time-on-d3js-graph.html

http://dimplejs.org/examples_viewer.html?id=areas_horizontal_stacked

http://stackoverflow.com/questions/25015266/ordering-columns-in-a-stacked-bar-chart-dimple

http://stackoverflow.com/questions/14404446/selected-element-wont-change-in-d3

http://blog.endpoint.com/2016/05/how-to-add-labels-to-dimple-js-line.html

http://stackoverflow.com/questions/3552461/how-to-format-a-javascript-date

http://stackoverflow.com/questions/2901102/how-to-print-a-number-with-commas-as-thousands-separators-in-javascript#2901298

https://www.w3schools.com/html/html_tables.asp
