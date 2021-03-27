<body>
	<form name="input">
		Enter initial crypto value: <input type="number" name="initial">
		</br>
		Enter final crypto value: <input type="number" name="final">
		</br>
		Enter investment amount: <input type="number" name="investAmount">
		</br>
	</form>
	<p>Your current value would be: ${{newAmount}}</p>
	<p>earningsString</p>
</body>

<script>
	export default {
		name: 'index',
		
		data: () => ({
			perIncrease: 100*((final-initial)/abs(initial));
			newAmount: investAmount*perIncrease;
			earnings: newAmount-investAmount;
			earningsString: printEarnings;
		})
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
