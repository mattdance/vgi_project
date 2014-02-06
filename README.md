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
	<li>The geostack that I envision is stackconcept.png</li>
	<li>The splash page will inlcude a disclaimer that indicates a user is about to contribute potentially provate data to a (see wf1.jpg).</li>
	<li>The main page posses the zoom, drawing and layer control tools (see wf2.jpg).</li>
	<li>When the user selects a drawing tool, they must also provide a title and description of that tool prior to saving whatever spatial element that they contribute (see wf2.jpg and wf3.jpg).</li>

</p>

<p>
As seen in wf1.jpg, the splash page has a few components of note:
	<ul>
		<li>A consent pop-up that will outline the limitation of data presented (i.e. not for navigation); privacy implications of adding spatial data; and that contributions will be moderated for inappropriate content.</li>
		<li>The side panel has a more detailed project overview, as well as links to other sites such as a twitter, facebook and blog pages.</li>
		<li>If the user does not consent, they will be allowed to view the data, but not add any spatial features - the draw tools will not be activiated.</li>
	</ul>
</p>

<p>
Once the user hits the "contribute" button, they will be allowed to add content via the draw button (see wf2.jpg). The work flow is as follows:
	<ol>	
		<li>The user will select the point, line or polygon button (*NOTE* add a trash button) to draw a feature. </li>
		<li>When the user presses the save icon on the draw toolbar, a popup will appear asking for a title and description of the feature just drawn (see wf3.jpg).</li> 
		<li>When "save" button is pressed, the data are saved and the user is presented with a confirmation popup indicating that the data is in a moderation queue.</li>
		<li>Once the user closes the "confirmation and moderation" popup window, they are presented with a blank map allowing for more data input.</li>
	</ol>
</p>

<p>
On the back end, several things are happening.  In step two (from above and in reference to wf2.jpg) when the user presses the "cancel" button, nothing happens, the data is not saved anywhere. When the user presses the "save" button, the data is saved, via SQL script, to an unmoderated CartoDB table.  In addition, to the input data, a contributors IP, Postal Code and other pertainant data will be saved to the same unmoderated table.  If there are issues with the contribution, the users IP can be blocked. An admin will have to go into CartoDB to moderate the contribution, and add the data to a moderated VGI table.
</p>

<h4>Questions</h4>
<p>
<ol>
<li>Should we require a valid email to complete the "save"? </li>
<li>How to we cartographically manage overlapping contributions that overlap?</li>
<li>How do me manage contribtions that are historical versus contemporary?<li>
</ol>
</p>

<h2>More to come.</h2>
