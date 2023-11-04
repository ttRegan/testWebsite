<html>
	<body>
		<div>Enter initial crypto value:</div> <input id="initial" type="number" name="initial">
		<div>Enter final crypto value:</div> <input id="final" type="number" name="final">
		<div>Enter investment amount:</div> <input id="investAmount" type="number" name="investAmount">
		<br/>
		<button onClick="calculate()">Calculate</button>
		<br/>
		<br/>
		<div id="show1" style="display:none;">Your current value would be: $<span id="newAmount"></span></div>
		<div id="show2" style="display:none;"><span id="earningsString"></span></div>
	</body>
</html>

<script>
	var initial;
	var final;
	var investAmount;
	var submitted = false;
	var perIncrease = 0;
	var increase = 0;
	var newAmount = 0;
	var earnings = 0;
	var earningsString = "";
	function calculate() {
		this.initial = document.getElementById("initial").value;
		this.final = document.getElementById("final").value;
		this.investAmount = document.getElementById("investAmount").value;
		this.submitted = true;
		this.perIncrease = ((this.final-this.initial)/Math.abs(this.initial));
		this.increase = this.investAmount*this.perIncrease;
		this.newAmount = parseFloat(this.investAmount)+parseFloat(this.increase);
		this.earnings = this.newAmount-this.investAmount;
		console.log(this.perIncrease);
		console.log(this.increase);
		console.log(this.newAmount);
		console.log(this.earnings);
		if ((this.earnings) >= 0 ){
			this.earningsString =  "You earnt: $" + String(this.earnings);
		} else {
			this.earningsString = "You lost: $" + String(Math.abs(this.earnings));
		}
		document.getElementById('newAmount').innerHTML = String(this.newAmount);
		document.getElementById('earningsString').innerHTML = this.earningsString;
		document.getElementById('show1').style.display = "";
		document.getElementById('show2').style.display = "";
	}
</script>
