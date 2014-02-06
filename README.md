<h1>VGI</h1>
=====

<h2>A VGI project with <a href="http://edmontonpipelines.org/">Edmonton Pipelines</a><h2>

<p>I was initially interested in building this project myself.  I have since learned, though trial and error, that the JS component is (at this point) beyond me.  So, I would like some help in building a map that:
<ol>
<li>Is open and available on GitHub;</li>
<li>Supports user contributions of point, line, and polygon;</li>
<li>Allows the user to label and describe their geometry;</li>
<li>Saves the geometry and metadata in a database;</li>
<li>Supports the moderation of contributions.</li>
</ol></p>

<p>To the best of my understanding, the stack that will best support a VGI workflow is:
<ol>
<li><a href="http://cartodb.com/">CartoDB</a>: As the DB where contributions will be written and stored for moderation via SQL.I also like the <a href="https://github.com/CartoDB/cartodb-publishing-templates">CartoDB SidePanel Template.</a></li>
<li><a href="https://www.mapbox.com/"> MapBox</a>: To provide a custom (cartocss) base-map.</li>
<li><a href="http://leafletjs.com/">LeafLet</a>: As the user interface and to provide the <a href="https://github.com/Leaflet/Leaflet.draw">LeafLetDraw Plugin</a> as well as the pan, zoom and layer control.</li>
<li>HTML/CSS: Basic web functionality, look and feel.</li>
<li>Javascript: To power the map, LeafLet plugins and custom windows associated with the VGI contributions.</li>
<li>SQL: CartoDB describes <a href="http://blog.cartodb.com/post/53510434258/read-and-write-to-cartodb-with-the-leaflet-draw-plugin"> here</a> how they use SQL to link the LeafLetDraw plugin to a table.
</ol>
</p>

<p>
	Other project components include:

	
	<ul>
	<li>The geostack that I envision is [The GeoStack] (stack_concept.png)</li>
	<li>The splash page will inlcude a disclaimer that indicates a user is about to contribute potentially provate data to a (see wireframe_splash.png).</li>
	<li>The main page posses the zoom, drawing and layer control tools (see wireframe_main.png).</li>
	<li>When the user selects a drawing tool, they must also provide a title and description of that tool prior to saving whatever spatial element that they contribute (see wireframe_add_polygon.png).</li>

</p>





<p>
	More to come.
</p>
