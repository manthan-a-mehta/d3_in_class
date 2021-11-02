Questions
## Our goal is to use this dataset to answer questions like:##

1. What are the airlines with more routes, and how does the distribution looks like? Are there airlines with many more routes that others?

2. Which regions of the world do these airlines cover?

3. Does a given airline operate in a regional or intercontinental scale?

### Task 1 ###

Complete all the TODO between the <style> tags.

### Task 2 ###

Next order of tasks:
1. Loading Data(loadData())

2. Preparing The Data (groupByAirline(data)):
The dataset we are loading contains one line for each route, but what we want to visualize is the list of airlines and we just need the number of routes for each airline. For this reason, we need to create a function that takes as input a list of routes and group these routes by airline. we will call this function "groupByAirline". 

The function will return a list of objects, where each object represents one airline and contains the following fields:

AirlineID: The id of the airline

AirlineName: The name of the airline

Count: The number of routes the given airline has.

Add this function to your file and complete the TODOs

3. showData(): ALready done

4. getAirlinesChartConfig():
One important thing to consider is the size of our chart, here we will create a function that will set and return details about the size of our chart. The function will return an object 

Add the function bellow to your code, and complete the TODOs

5. getAirlinesChartScales(airlines, config):
The next step is to create the scales, that will help us to convert the data from the data space to the graphical space. We will use information from our dataset as information on what is the size of the chart to create those scales. 

Copy the function bellow to your index.html file and complete the TODOs

6. drawBarsAirlinesChart(airlines, scales, config):
We finally have the information we need to draw the bars, we will use some information from our size configuration, as well as the scales generated by the getAirlinesChartScales function. 

Copy the function bellow to your index.html file and complete the TODOs

7. drawAirlinesChart(airlines):
Main function

8. drawAxesAirlinesChart(airlines, scales, config)
The last step is to add the axes, so we can know which bar belongs to which airline. Lets add a new function that will do this job, called drawAxesAirlinesChart. It will receive the same parameters of our last function. 

9. drawAirlinesChart(airlines): Main function

10. getMapConfig():
Similar to what we did for the bar chart, we will create a function to set and return information about the size of the map called getMapConfig(). 

Add the function bellow to your code, and complete the TODOs

11. getMapProjection(config)
The next step is to choose which projection to use, we will create a function that return the projection. We will need to translate the projection to make sure that the center of the world is also in the center of our svg, for this reason, this function will receive as parameter the width and height of the map. We will also save the projection on our store, so we can easily access it later.

Add the function bellow to your code, and complete the TODOs

12. drawBaseMap(container, countries, projection)
Our last function is the one responsible for actually drawing the map, this function will receive as parameter, the container, the features of the GeoJSON file, a.k.a. the countries we want to draw, and the projection to use.

Add the function bellow to your code, and complete the TODOs

13. drawMap(geoJeon):
Finally, lets add a function that will be responsible for calling the previous functions in the right sequence. It will be called drawMap. And it should look like the code below.


14. groupByAirport(data):
Similarly to what we did fro the airlines bar chart, we will have to group the routes by airport this time. One major difference here is that each route have two airports, so we have to make sure to consider both airports when doing the aggregation. Bellow is the groupByAirport function that will group the routes by airport. 

Copy this function to your file

15. drawAirports(airports)
Because we have already created the projection and set the configurations of the map container in the previous part of our project, we will need only one function to draw the airports in the map, we will call this function drawAirports. It will receive as parameter the airports, and it will use some methods we created before to obtain the projection and the container it should use.

Copy the function bellow to your file and complete the TODOs

16. drawRoutes(airlineID):
Lets start by creating the function that will draw the routes. You can think of this dataset of a network of airports that are linked by routes, each route has a source and a destination. For this reason we will represent the connections between the airports, that is the routes, using a line that connects each airport.

We will create a function called drawRoutes that will receive an airlineID as parameter and draw all routes for this airline. Note that we don't need to create any scale here, since we can use the projection we created in previous steps. What we will do is load the routes and the projection from our store variable, then we will filter to select only routes of the selected airline and finally we will draw those lines. 

It is a short function, but it will touch in many concepts that we saw throughout the course.

Copy the function below to your file and complete the TODOs

17. drawBarsAirlinesChart(airlines, scales, config)
To call the function on hovering, we will have to listen for an event, however, we will need 2 events to represent hovering. The first is 'mouseenter', we will use it to know when the mouse enter the bar and when that happen, show the routes. The second is 'mouseleave', we will use it to know when the mouse is not hover the bar anymore, and in this case, remove the lines for that airline from the chart. 

As the mouse enters and leaves the bar, we will also change the color of the bar to make clear to the user which bar the mouse is hover.

These listeners should be added to our bars, so we will have to edit our drawBarsAirlinesChart function we created early in the project. We will add the code after the line that is setting the fill color of the bar. You will have to change that section as the code below.