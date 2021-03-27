<html>
	<body>
		<div>Enter initial crypto value:</div> <input type="number" name="initial">
		<p>Enter final crypto value:</p> <input type="number" name="final">
		<p>Enter investment amount:</p> <input type="number" name="investAmount">
		<button onClick="calculate()">Calculate</button>
		<p>Your current value would be: ${{newAmount}}</p>
		<p>{{earningsString}}</p>
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
	var earningsString : function() {
		this.submitted = true;
		this.perIncrease = 100*((this.final-this.initial)/abs(this.initial));
		this.newAmount = this.investAmount*this.perIncrease;
		this.earnings: this.newAmount-this.investAmount;
		if ((this.earnings) >= 0 ){
			return "You earnt: $" + String(this.earnings);
		} else {
			return "You lost: $" + String(abs(this.earnings));
		}
	}
</script>
