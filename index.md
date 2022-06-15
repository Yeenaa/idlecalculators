<html>
<head>
<script type="text/javascript">
function get_online(form) {
var inputhours = Number(form.inputhours.value);
var inputminutes = Number(form.inputminutes.value);
var inputcleartime = Number(form.inputcleartime.value);
var inputstagedrop = Number(form.inputstagedrop.value);
var hrminutes = Number(0);
var totalmin = Number(0);
var totalcleartime = Number(0);
var clearsperminute = Number(0);
var droplowstage = Number(0);
var stagedroprate = Number(0);
var gainslowstage = Number(0);
var drophighstage = Number(0);
var gainshighstage = Number(0);
hrminutes = inputhours * 60
totalmin = hrminutes+inputminutes;
totalcleartime = inputcleartime + 5;
clearsperminute = 60 / totalcleartime;
droplowstage = 235 / 10000;
stagedroprate = inputstagedrop / 100;
gainslowstage = (totalmin * clearsperminute) * (droplowstage * stagedroprate);
drophighstage = (26 / 1000);
gainshighstage = (totalmin * clearsperminute) * (drophighstage * stagedroprate);
var onlinegains_txt = "Your Stage 2-50 - 14-50 online Bonanza Chest gains per hour are " + gainslowstage;
var onlinegains2_txt = "Your Stage 15-25 - 44-50 online Bonanza Chest gains per hour are " + gainshighstage;
document.getElementById('calculationresult').innerHTML = onlinegains_txt + "<br>" + onlinegains2_txt; 
}
</script>
</head>
<body>

<title>
Stage Drop calculator
</title>

<header>
<b>
Stage Drop calculator
</b>
</header>
<form name="online_calc">
	<br>
    <label>Hours:</label>
	<br>
    <input type="text" name="inputhours">
	<br>
	<br>
    <label>Minutes:</label>
	<br>
    <input type="text" name="inputminutes">
	<br>
	<br>
    <label>Cleartime</label>
	<br>
    <label>(please only put pure stage clear time in here, do not count transition time!):</label>
	<br>
    <input type="text" name="inputcleartime">
    <br>
	<br>
	<label>Stage Drop %</label>
	<br>
    <label>(you can find this in your character's stats window):</label>
    <br>
	<input type="text" name="inputstagedrop">
	<br>
	<br>
    <input type="button" value="Calculate" onclick="get_online(this.form)">
</form>

<br>
<br>
<b>
<div id="calculationresult">
</div>
</b>
<footer>
<br><br>Please note, Stage 25-25 has lower Accessory Chest drop chances than other stages and is thus not recommended to be farmed until Mobirix fixes this
</footer>
</body>
</html>
