<script>
	// @ts-nocheck

	let user_options = [
		{ id: 1, name: 'Buyer', selected: false },
		{ id: 2, name: 'Seller', selected: false },
		{ id: 3, name: 'Both', selected: false }
	];

	function toggleSelection(option) {
		option.selected = !option.selected;
	}
</script>

<body>
	<div id="main-registration-box">
		<form id="registration-form">
			<div class="username-group">
				<h3 class="username-text">Your Username</h3>
				<p><input placeholder="" /></p>
			</div>

			<div class="option-boxes">
				<h3 class="option-text">
					What kind of user will you be? if you are not sure, select both (Don't worry, you can
					change this later)
				</h3>
				{#each user_options as option}
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<div class="option-box" on:click={() => toggleSelection(option)}>
						<input
							class="option-input"
							type="checkbox"
							bind:checked={option.selected}
							id={'option-' + option.id}
						/>
						<label
							for={'option-' + option.id}
							class="custom-checkbox {option.selected ? 'selected' : ''}"
						>
							{option.name}
						</label>
					</div>
				{/each}
			</div>
		</form>
	</div>
</body>

<style>
	body {
		margin: 0;
		padding: 0;
		display: flex;
		justify-content: center;
		align-items: center;
		min-height: 100vh;
		font-family: 'Jost', sans-serif;
		background: linear-gradient(to bottom, #b91a1a, #016473);
	}

	#main-registration-box {
		width: 350px;
		height: 500px;
		background: #fff; /* Changed for a cleaner look */
		overflow: hidden;
		border-radius: 10px;
		width: 40%;
		height: 80%;
		padding: 20px;
	}

	#registration-form {
		position: relative;
		width: 100%;
		height: 100%;
	}

	.username-group {
		text-align: center; /* Center the username group content */
		margin-top: 70px;
		margin-bottom: 30px; /* Add more space between the username section and options */
	}

	.username-group input {
		height: 50px;
		width: 40%; /* Adjust the input width as needed */
		padding: 5px; /* Add some padding for better appearance */
		margin-top: 10px; /* Space between label and input */
	}

	.username-text {
		margin-bottom: 5px; /* Optional: Adjust the space between the title and the input */
	}

	.option-boxes {
		display: flex; /* Use flexbox to arrange children horizontally */
		justify-content: center; /* Center the items horizontally */
		flex-wrap: wrap; /* Wrap items to the next line if needed */
	}

	.option-box {
		display: inline-flex; /* Use flexbox within each option */
		align-items: center; /* Vertically align items in the center */
		margin: 5px; /* Space between boxes */
		cursor: pointer;
	}

	.custom-checkbox {
		width: 100px;
		height: 100px;
		border: 1px solid #555;
		display: flex; /* Use flexbox for internal alignment */
		justify-content: center; /* Center content horizontally */
		align-items: center; /* Center content vertically */
		text-align: center; /* Align text in the center */
		margin-right: 8px;
		transition: background-color 0.3s;
		border-radius: 20px;
		background-color: #fefefe;
	}

	.custom-checkbox.selected {
		background-color: #b91a1a; /* Change color when selected */
	}

	.option-input {
		display: none; /* Hide the default checkbox */
	}

	.option-text {
		text-align: center;
	}
</style>
