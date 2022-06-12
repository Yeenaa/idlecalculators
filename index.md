<script type="text/javascript">
function get_c() {
var eingabe = document.exmplform.eingabe.value;
var a = eingabe * 21;
var b = eingabe * 85;
var c = eingabe * a +b * 585;
document.getElementById('ergebnis').innerHTML = c; 
}
</script>

<form name="exmplform">
<input type="text" name="eingabe">
<input type="button" value="Berechnen" onclick="get_c()">
</form>
<div id="ergebnis">
</div>
