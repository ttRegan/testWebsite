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
	name: 'testWebsite',
	
	data: () => ({
		initial: null;
		final: null;
		investAmount: null;
		submitted: false;
		perIncrease: 0;
		newAmount: 0;
		earnings: 0;
		earningsString: "";
	})
	methods: {
		calculate() {
			this.submitted = true;
			this.perIncrease = 100*((this.final-this.initial)/abs(this.initial));
			this.newAmount = this.investAmount*this.perIncrease;
			this.earnings: this.newAmount-this.investAmount;
			if ((this.earnings) >= 0 ){
				this.earningsString = "You earnt: $" + String(this.earnings);
			} else {
				this.earningsString = "You lost: $" + String(abs(this.earnings));
			}
		}
	}
</script>
