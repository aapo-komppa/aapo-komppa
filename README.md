Hello!

I'm Aapo and I like to try new stuff out and isn't afraid of jumping into the deep end of the projects.

I've been programming now for 8-ish years and bit over 5 years professionally.

For more about me:
https://www.ceon.fi/people/aapo/

Enjoy waiting for this being sorted by bogosort:

<html>
<head>
<style>
	#table{
		height: 300px;
		width: 900px;
		background-color: #f2f2f2;
	}
	
	#table > * {
		width: 34px;
		background-color: hotpink;
		display: inline-block;
		margin: 0 1px;
	}	

	#table #div1{height: 12px;}
	#table #div2{height: 24px;}
	#table #div3{height: 36px;}
	#table #div4{height: 48px;}
	#table #div5{height: 60px;}
	#table #div6{height: 72px;}
	#table #div7{height: 84px;}
	#table #div8{height: 96px;}
	#table #div9{height: 108px;}
	#table #div10{height: 120px;}
	#table #div11{height: 132px;}
	#table #div12{height: 144px;}
	#table #div13{height: 156px;}
	#table #div14{height: 168px;}
	#table #div15{height: 180px;}
	#table #div16{height: 192px;}
	#table #div17{height: 204px;}
	#table #div18{height: 216px;}
	#table #div19{height: 228px;}
	#table #div20{height: 240px;}
	#table #div21{height: 252px;}
	#table #div22{height: 264px;}
	#table #div23{height: 276px;}
	#table #div24{height: 288px;}
	#table #div25{height: 300px;}
</style>
</head>
<body>

<div id="table">
</div>

<p><a href="bogosort_simple.html">4-item one</a> This finishes in reasonable time</p>

<script>

// define vars
var list = [];
var sortState = false;

// create list of items
for(let i = 0; i<25; i++) {
	list[i] = i+1;
}

// start loop
loop();

function loop() {
    setTimeout(function () {
	
	// empty the table
	table.innerHTML = null;
	// create new table
	draw();

	// check if the table is in order
	if(checkList(list) == true) {
	    sortState = true;
	}
	
	// restart the loop
        if (sortState == false) {
            loop();
        }

    }, 100)
}

function draw() {
	
	// suffle the list
	list = shuffle(list);

	console.log(list);
	
	// draw the table
	var table = document.getElementById("table");
	for(let i = 0; i < list.length; i++) {
		let para = document.createElement("div");
		para.setAttribute("id", "div" + list[i]);
		table.appendChild(para);
	}
}

function checkList(list) {
	
	// go through the list 
	for(let i = 1; i < list.length; i++) {
		
		// and check if it is in order
		if(list[i-1] > list[i]) {
			console.log("false");
			return false;
		}

	}
	console.log("true");
	return true;
}

// this is de facto way to randomise in JS according to Stackoverflow
function shuffle(array) {
  var currentIndex = array.length, temporaryValue, randomIndex;

  // While there remain elements to shuffle...
  while (0 !== currentIndex) {

    // Pick a remaining element...
    randomIndex = Math.floor(Math.random() * currentIndex);
    currentIndex -= 1;

    // And swap it with the current element.
    temporaryValue = array[currentIndex];
    array[currentIndex] = array[randomIndex];
    array[randomIndex] = temporaryValue;
  }

  return array;
}

</script>

</body>
</html>
