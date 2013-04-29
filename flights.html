
<!DOCTYPE html>
<html>
  <head>
  	<title>Flights</title>
    <meta http-equiv="Content-Type" content="text/html;charset=utf-8"/>
    <script type="text/javascript" src="d3.v3.min.js"></script>
    <script type="text/javascript" src="geo.js"></script>
    <link type="text/css" rel="stylesheet" href="style.css"/>
  </head>
  <body>
    <div id="body">
	    <div id="info">
	    	<div class="stat">
	    		<div id="flight_num" class="stat_num">#</div>
	    		<p>Flights on</p>
	    		<p id="flight_date"></p>
	    	</div>

	    	<div class="stat">
	    		<div id="airport_num" class="stat_num">#</div>
	    		<p>Airports</p>
	    	</div>
	    </div>
    </div>
    <script type="text/javascript">
		var feature;
		var airports;

		var projection = d3.geo.azimuthal()
		    .scale(380)
		    .origin([-85.03,30.37])
		    .mode("orthographic")
		    .translate([640, 400]);

		var circle = d3.geo.greatCircle()
		    .origin(projection.origin());

		// TODO fix d3.geo.azimuthal to be consistent with scale
		var scale = {
		  orthographic: 380,
		  stereographic: 380,
		  gnomonic: 380,
		  equidistant: 380 / Math.PI * 2,
		  equalarea: 380 / Math.SQRT2
		};

		var path = d3.geo.path()
		    .projection(projection);

		var svg = d3.select("#body").append("svg:svg")
		    .attr("width", 1280)
		    .attr("height", 800)
		    .attr("id","globe")
		    .on("mousedown", mousedown);


		d3.json("world-countries.json", function(collection) {
		  
		  feature = svg.selectAll("path")
		      .data(collection.features)
		    .enter().append("svg:path")
		      .attr("d", clip)
		      .attr("class",function(d){return d.properties.class;});

		  feature.append("svg:title")
		      .text(function(d) { return d.properties.name; });
		});


		d3.json("flights.json", function(collection) {
		  airports = svg.selectAll("path")
		      .data(collection.features, function(d){return d.properties.name;})
		    .enter().insert("svg:path")
		      .attr("d", clip)
		      .attr("class",function(d){return d.properties.class;});

		  airports.append("svg:title")
		      .text(function(d) { return d.properties.name; });

		  document.getElementById("flight_num").innerHTML = collection.num_flights;
		  document.getElementById("flight_date").innerHTML = collection.flight_date;
		  document.getElementById("airport_num").innerHTML = collection.num_airports;
		});

		var lineLegend = svg.append("g")
				lineLegend.selectAll("line")
				.data(["flight-historical","flight-today","flight-future"])
				.enter()
				.append("line")
				.attr("x1", 40)
				.attr("y1", function(d,i){return 320 + (i*15) ;})
				.attr("x2", 91)
				.attr("y2", function(d,i){return 320 + (i*15) ;})
				.attr("class",function(d){return d + " flight";})

			lineLegend.selectAll('text')
      			.data(["Historical Flight","Flight Today","Future Flight"])
      			.enter()
			    .append("text")
			    .attr("class","stat_sublabel")
				.attr("x", 100)
      			.attr("y", function(d, i){ return 320 + (i*15) + 5;})
	  			.text(function(d) { return d; });


		d3.select(window)
		    .on("mousemove", mousemove)
		    .on("mouseup", mouseup);

		var m0,
		    o0;

		function mousedown() {
		  m0 = [d3.event.pageX, d3.event.pageY];
		  o0 = projection.origin();
		  d3.event.preventDefault();
		}

		function mousemove() {
		  if (m0) {
		    var m1 = [d3.event.pageX, d3.event.pageY],
		        o1 = [o0[0] + (m0[0] - m1[0]) / 8, o0[1] + (m1[1] - m0[1]) / 8];
		    projection.origin(o1);
		    circle.origin(o1)

		    refresh();
		  }
		}

		function mouseup() {
		  if (m0) {
		    mousemove();
		    m0 = null;
		  }
		}

		function refresh(duration) {
		  (duration ? feature.transition().duration(duration) : feature).attr("d", clip);
		  (duration ? airports.transition().duration(duration) : airports).attr("d", clip);
		}

		function clip(d) {
		  return path(circle.clip(d));
		}

    </script>
  </body>
</html>