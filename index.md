<html>
	<body>
		<p>Enter initial crypto value:</p> <input type="number" name="initial">
		</br>
		<p>Enter final crypto value:</p> <input type="number" name="final">
		</br>
		<p>Enter investment amount:</p> <input type="number" name="investAmount">
		</br>
		<button onClick="calculate()">Calculate</button>
		<p>Your current value would be: ${{newAmount}}</p>
		<p>earningsString</p>
	</body>
</html>

<script>
	export default {
		name: 'index',
		
		data: () => ({
			perIncrease: 100*((final-initial)/abs(initial));
			newAmount: investAmount*perIncrease;
			earnings: newAmount-investAmount;
			earningsString: printEarnings;
		})
		methods: {
			calculate() {
				
			}
		}
		computed: {
			printEarnings: function() {
				if (this.earnings) >= 0:
					return ("You earnt: $" + String(this.earnings));
				else: 
					return ("You lost: $" + String(abs(this.earnings)));
			}
		}
	}
</script>
