## You can view my Tableau Public Dashboards using the below links

<script src="https://www.example.com/javascripts/api/tableau-2.js"></script>
<div id="tableauViz"></div>

1.  <a href='https://public.tableau.com/views/London_Bike_Rides_Visualization/Dashboard1?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link'> London Bike Rides Analysis </a>

2.


function initializeViz() {
var placeholderDiv = document.getElementById("tableauViz");
var url = "https://public.tableau.com/views/London_Bike_Rides_Visualization/Dashboard1?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link";
var options = {
 width: '600px',
 height: '600px',
 hideTabs: true,
 hideToolbar: true,
 };
viz = new tableau.Viz(placeholderDiv, url, options);
}
