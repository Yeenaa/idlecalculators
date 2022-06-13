<html>
<head>
<script type="text/javascript">
function get_online(form) {
var inputhours = form.inputhours.value;
var inputminutes = form.inputminutes.value;
var inputcleartime = form.inputcleartime.value;
var inputstagedrop = form.inputstagedrop.value;
var hrminutes = inputhours * 60;
var totalmin = inputminutes + hrminutes;
var totalcleartime = inputcleartime + 5;
var clearsperminute = 60 / totalcleartime;
var droplowstage = 235 / 10000;
var gainslowstage = (totalmin * clearsperminute) * (droplowstage * (inputstagedrop / 100));
var drophighstage = 26 / 1000;
var gainshighstage = (totalmin * clearsperminute) * (drophighstage * (inputstagedrop / 100));
var onlinegains_txt = "Your online Chest gains per hour are " + gainslowstage;
var onlinegains2_txt = "Your online Chest gains per hour are " + gainshighstage;
document.getElementById('calculationresult').innerHTML = onlinegains_txt + "<br>" + onlinegains2_txt; 
}
</script>
</head>
<body>



<form name="online_calc">
    <label>Hours:</label>
	<br>
    <input type="text" name="inputhours">
	<br>
    <label>Minutes:</label>
	<br>
    <input type="text" name="inputminutes">
	<br>
    <label>Cleartime</label>
	<br>
    <label>(please only put pure stage clear time in here, do not count transition time!):</label>
	<br>
    <input type="text" name="inputcleartime">
    <br>
	<label>Stage Drop %</label>
	<br>
    <label>(you can find this in your character's stats window):</label>
    <br>
	<input type="text" name="inputstagedrop">
	<br>
    <input type="button" value="Calculate" onclick="get_online(this.form)">
</form>


<div id="calculationresult">
</div>
</body>
</html>
