<script>
	// @ts-nocheck
	let currentStep = 1;
	let userType = 0; // 0 = Both, 1 = Buyer, 2 = Seller
	const totalSteps = 6;

	let userOptions = [
		{ id: 1, name: 'Buyer', selected: false },
		{ id: 2, name: 'Seller', selected: false },
		{ id: 3, name: 'Both', selected: false }
	];

	let continueOptions = [
		{ id: 1, name: 'Explore', selected: false },
		{ id: 2, name: 'Finish', selected: false }
	];

	const toggleSelection = (option) => (option.selected = !option.selected);

	const goToNextStep = () => {
		if (currentStep < totalSteps) {
			currentStep += 1;
		}
	};

	const isNextDisabled = () => currentStep === totalSteps;

	const handleProfilePictureUpload = (event) => {
		const file = event.target.files[0];
		// Handle file upload logic here.
	};
</script>

<body>
	<div id="main-registration-box">
		<form id="registration-form">
			{#if currentStep === 1}
				<div class="username-group">
					<h3>Your Username</h3>
					<input placeholder="" />
				</div>

				<div class="option-boxes">
					<h3>What kind of user will you be? If unsure, select both (changeable later).</h3>
					{#each userOptions as option}
						<!-- svelte-ignore a11y-click-events-have-key-events -->
						<div class="option-box" on:click={() => toggleSelection(option)}>
							<input type="checkbox" bind:checked={option.selected} id={`option-${option.id}`} />
							<label
								for={`option-${option.id}`}
								class="custom-checkbox {option.selected ? 'selected' : ''}"
							>
								{option.name}
							</label>
						</div>
					{/each}
				</div>
			{/if}

			{#if currentStep === 2}
				<div class="continue-options">
					<h3>Welcome to TodoCar! Explore our services or finish your profile.</h3>
					<div class="continue-options-boxes">
						{#each continueOptions as option}
							<!-- svelte-ignore a11y-click-events-have-key-events -->
							<div class="option-box" on:click={() => toggleSelection(option)}>
								<input
									type="checkbox"
									bind:checked={option.selected}
									id={`continue-${option.id}`}
								/>
								<label
									for={`continue-${option.id}`}
									class="custom-checkbox {option.selected ? 'selected' : ''}"
								>
									{option.name}
								</label>
							</div>
						{/each}
					</div>
				</div>
			{/if}

			{#if currentStep === 3}
				<div class="profile-upload">
					<h3>Choose a profile picture</h3>
					<label for="profile-picture-upload" class="profile-picture-upload-label">
						<input
							type="file"
							id="profile-picture-upload"
							accept="image/*"
							on:change={handleProfilePictureUpload}
						/>
						<div class="upload-placeholder">Click to upload</div>
					</label>
					<div class="name-inputs">
						<h3>Enter your legal full name. (ID verification may be required.)</h3>
						<input type="text" placeholder="First" class="first-name-input" />
						<input type="text" placeholder="Last" class="last-name-input" />
					</div>
				</div>
			{/if}

			{#if currentStep === 4 && (userType === 1 || userType === 0)}
				<div class="car-amount">
					<h3>
						Enter the make, model, and mileage of your primary vehicle. (More can be added later.)
					</h3>
					<label for="vehicle-info-make"> Make</label>
					<input type="text" id="vehicle-info-make" />
					<label for="vehicle-info-model">Model (include year)</label>
					<input type="text" id="vehicle-info-model" />
					<label for="vehicle-info-mileage">Mileage</label>
					<input type="text" id="vehicle-info-mileage" />
				</div>
			{/if}

			{#if currentStep === 5}
				<div />
			{/if}
			{#if currentStep === 6}
				<div />
			{/if}

			{#if currentStep < totalSteps}
				<button on:click={goToNextStep} disabled={isNextDisabled()} id="next-button">Next</button>
			{/if}
		</form>
	</div>
</body>

<style>
	body {
		display: flex;
		justify-content: center;
		align-items: center;
		min-height: 100vh;
		font-family: 'Jost', sans-serif;
		background: linear-gradient(to bottom, #b91a1a, #016473);
		margin: 0;
		padding: 0;
	}

	#registration-form {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	#main-registration-box {
		width: 40%;
		min-height: 80%; /* Use min-height to allow expansion if needed */
		background: #fff;
		border-radius: 10px;
		padding: 20px;
		overflow: auto; /* Add overflow handling */
		display: flex; /* Make it a flex container */
		flex-direction: column; /* Stack children vertically */
	}
	#registration-form {
		width: 100%;
		height: 100%;
	}

	.username-group,
	.profile-upload {
		text-align: center;
		margin-top: 30px;
	}
	.continue-options {
		text-align: center;
		margin-top: 50px;
	}

	.username-group input,
	.name-inputs input[type='text'] {
		width: 80%;
		height: 40px;
		margin-top: 10px;
		padding: 5px;
	}

	.option-boxes,
	.continue-options-boxes {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		margin-top: 20px;
	}

	.option-box {
		display: inline-flex;
		align-items: center;
		margin: 5px;
		cursor: pointer;
	}

	#option-1,
	#option-2,
	#option-3,
	#continue-1,
	#continue-2,
	#continue-3 {
		display: none;
	}

	.custom-checkbox {
		width: 100px;
		height: 100px;
		border: 1px solid #555;
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
		margin-right: 8px;
		transition: background-color 0.3s;
		border-radius: 20px;
		background-color: #fefefe;
	}

	.custom-checkbox.selected {
		background-color: #b91a1a;
	}

	.option-input {
		display: none; /* Hide the default checkbox */
	}

	.upload-placeholder {
		width: 230px;
		height: 230px;
		background: #c0c0c0;
		border-radius: 50%;
		display: flex;
		justify-content: center;
		align-items: center;
		margin: 0 auto;
	}

	.last-name-input {
		margin-bottom: 0;
	}
	.car-amount {
		display: flex;
		flex-direction: column;
	}

	.car-amount label,
	.car-amount input[type='text'] {
		align-self: center;
		width: 80%;
		margin-top: 10px;
	}

	.car-amount label {
		align-self: flex-start;
		margin-left: 10%;
		font-size: 20px;
	}

	#next-button {
		width: 150px;
		height: 50px;
		background-color: #095870;
		color: #fff;
		border: none;
		border-radius: 5px;
		margin-top: 20px;
		cursor: pointer;
		margin-top: 50px;
	}
</style>
