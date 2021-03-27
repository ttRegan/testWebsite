<html>
	<body>
		<div>Enter initial crypto value:</div> <input id="initial" type="number" name="initial">
		<p>Enter final crypto value:</p> <input id="final" type="number" name="final">
		<p>Enter investment amount:</p> <input id="investAmount" type="number" name="investAmount">
		<br/>
		<button onClick="calculate()">Calculate</button>
		<br/>
		<h2 id="show1" style="display:none;">Your current value would be: $<span id="earnings"></span></h2>
		<h2 id="show2" style="display:none;"><span id="earningsString"></span></h2>
	</body>
</html>

<script>
	var initial;
	var final;
	var investAmount;
	var submitted = false;
	var perIncrease = 0;
	var newAmount = 0;
	var earnings = 0;
	var earningsString = "";
	function calculate() {
		this.initial = document.getElementById("initial").value;
		this.final = document.getElementById("final").value;
		this.investAmount = document.getElementById("investAmount").value;
		this.submitted = true;
		console.log(this.submitted);
		this.perIncrease = 100*((this.final-this.initial)/Math.abs(this.initial));
		this.newAmount = this.investAmount*this.perIncrease;
		this.earnings = this.newAmount-this.investAmount;
		if ((this.earnings) >= 0 ){
			this.earningsString =  "You earnt: $" + String(this.earnings);
		} else {
			this.earningsString = "You lost: $" + String(Math.abs(this.earnings));
		}
		console.log(this.earnings);
		console.log(this.earningsString);
		document.getElementById('earnings').innerHTML = String(this.earnings);
		document.getElementById('earningsString').innerHTML = this.earningsString;
		document.getElementById('show1').style.display = "";
		document.getElementById('show2').style.display = "";
	}
</script>
