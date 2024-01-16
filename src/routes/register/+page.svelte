<script>
	// @ts-nocheck
	let currentStep = 3;
	const totalSteps = 6; // Adjust based on the number of steps in your form

	let user_options = [
		{ id: 1, name: 'Buyer', selected: false },
		{ id: 2, name: 'Seller', selected: false },
		{ id: 3, name: 'Both', selected: false }
	];

	let continue_options = [
		{ id: 1, name: 'Explore', selected: false },
		{ id: 2, name: 'Finish', selected: false }
	];

	function toggleSelection(option) {
		option.selected = !option.selected;
	}

	function goToNextStep() {
		if (currentStep < totalSteps) {
			currentStep += 1;
		}
	}

	function handleProfilePictureUpload(event) {
		const file = event.target.files[0];
		// You can handle the file upload process here.
		// For example, you might want to set it to a local state,
		// display a preview, or directly upload it to your server.
	}

	// Additional functions for form handling...
</script>

<body>
	<div id="main-registration-box">
		<form id="registration-form">
			{#if currentStep == 1}
				<div class="username-group">
					<h3 class="input-text">Your Username</h3>
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
			{/if}
			{#if currentStep == 2}
				<div class="continue-options">
					<h3 class="input-text">
						Welcome to TodoCar! You may now explore our services if you wish or finish creating your
						profile.
					</h3>

					<div class="continue-options-boxes">
						{#each continue_options as option}
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
				</div>
			{/if}
			{#if currentStep == 3}
				<div class="profile-upload">
					<h3 class="input-text">Choose a profile picture</h3>
					<label for="profile-picture-upload" class="profile-picture-upload-label">
						<input
							type="file"
							id="profile-picture-upload"
							accept="image/*"
							style="display: none;"
							on:change={handleProfilePictureUpload}
						/>
						<div class="upload-placeholder">
							<!-- Placeholder or icon for upload -->
							Click to upload
						</div>
					</label>
					<div class="name-inputs">
						<h3 class="input-text">
							Enter your legal full name. (You may be asked to present ID later.)
						</h3>
						<input type="text" placeholder="First" class="first-name-input" />
						<input type="text" placeholder="Last" class="last-name-input" />
					</div>
				</div>
			{/if}

			{#if currentStep == 4}
				<div />
			{/if}
			{#if currentStep == 5}
				<div />
			{/if}
			{#if currentStep == 6}
				<div />
			{/if}
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

	.input-text {
		margin-bottom: 5px; /* Optional: Adjust the space between the title and the input */
	}

	.continue-options {
		text-align: center; /* Center the continue options */
		margin-top: 60px;
		margin-bottom: 30px; /* Add more space between the continue options and the options */
		margin-left: 20px;
		margin-right: 20px;
	}

	.continue-options-boxes {
		display: flex; /* Use flexbox to arrange children horizontally */
		justify-content: center; /* Center the items horizontally */
		flex-wrap: wrap; /* Wrap items to the next line if needed */

		margin-top: 40px;
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

	.profile-upload {
		text-align: center;
		margin-top: 30px; /* Adjust as needed */
	}

	.profile-picture-upload-label {
		display: block; /* Change to block if you want the label to take the full width of its container */
		cursor: pointer;
		padding: 10px;
		background: transparent; /* No background since the placeholder has the grey fill */
		width: fit-content; /* Fit the content size */
		margin: 0 auto; /* Center the label */
	}

	.upload-placeholder {
		width: 230px; /* Width of the circle */
		height: 230px; /* Height of the circle, same as width for a perfect circle */
		background: #c0c0c0; /* Grey fill */
		border-radius: 50%; /* Makes it a circle */
		margin: 0 auto; /* Center the placeholder horizontally */
		display: flex; /* Use flexbox for positioning */
		justify-content: center; /* Center horizontally in the flex container */
		align-items: center; /* Center vertically in the flex container */
		text-align: center; /* Center text for single and multi-line support */
		/* Additional styling if needed */
	}
	.name-inputs h3 {
		margin-top: 20px; /* Space between upload and name title /
margin-bottom: 10px; / Space between name title and inputs */
	}

	.name-inputs input[type='text'] {
		margin: 10px;
	}

	.first-name-input {
		/* Additional styles if needed */
	}

	.last-name-input {
		/* Additional styles if needed */
	}
</style>
