<script>
</script>

<body>
	<div class="container">
		<div class="google-signin">
			<button class="google-signin-btn">
				<img src="path-to-google-icon.png" alt="" />
				Sign in with Google
			</button>
		</div>

		<div class="divider">OR</div>

		<div class="auth-forms">
			<div class="main">
				<input type="checkbox" id="chk" aria-hidden="true" />

				<div class="signup">
					<form>
						<label for="chk" aria-hidden="true">Sign up</label>
						<input type="text" name="txt" placeholder="User name" />
						<input type="email" name="email" placeholder="Email" />
						<input type="password" name="pswd" placeholder="Password" />
						<button>Sign up</button>
					</form>
				</div>

				<div class="login">
					<form>
						<label for="chk" aria-hidden="true">Login</label>
						<input type="email" name="email" placeholder="Email" />
						<input type="password" name="pswd" placeholder="Password" />
						<button>Login</button>
					</form>
				</div>
			</div>
		</div>
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

	.main {
		width: 350px;
		height: 500px;
		background: #fff; /* Changed for a cleaner look */
		overflow: hidden;
		background: url('your-image-url') no-repeat center/cover; /* Replace with your image URL */
		border-radius: 10px;
		box-shadow: 5px 20px 50px #000;
	}

	#chk {
		display: none;
	}

	.signup,
	.login {
		position: relative;
		width: 100%;
		height: 100%;
	}

	label {
		color: #f3f3f3; /* Deep red color for titles */
		font-size: 2.3em;
		justify-content: center;
		display: flex;
		margin: 60px;
		font-weight: bold;
		cursor: pointer;
		transition: 0.5s ease-in-out;
	}

	input {
		width: 60%;
		height: 20px;
		background: #f0f0f0; /* Lighter shade for input fields */
		justify-content: center;
		display: flex;
		margin: 20px auto;
		padding: 10px;
		border: none;
		outline: none;
		border-radius: 5px;
	}

	button {
		width: 60%;
		height: 40px;
		margin: 10px auto;
		justify-content: center;
		display: block;
		color: #fff;
		background: #016473; /* Teal color for buttons */
		font-size: 1em;
		font-weight: bold;
		margin-top: 20px;
		outline: none;
		border: none;
		border-radius: 5px;
		transition: 0.2s ease-in;
		cursor: pointer;
	}

	button:hover {
		background: #014d59; /* Slightly darker teal on hover */
	}

	.login {
		height: 460px;
		background: #f8f8f8; /* Light grey for the login form background */
		border-radius: 60% / 10%;
		transform: translateY(-180px);
		transition: 0.8s ease-in-out;
	}

	.login label {
		color: #b91a1a; /* Deep red for login title */
		transform: scale(0.6);
	}

	#chk:checked ~ .login {
		transform: translateY(-500px);
	}

	#chk:checked ~ .login label {
		transform: scale(1);
	}

	#chk:checked ~ .signup label {
		transform: scale(0.6);
	}

	.container {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 20px; /* Spacing between elements */
	}

	.google-signin-btn {
		background-color: #db4437;
		color: white;
		padding: 28px 8px;
		border: none;
		border-radius: 2px;
		font-family: 'Roboto', sans-serif;
		display: flex;
		align-items: center;
		cursor: pointer;
		font-size: 13px;
		border-radius: 10px;
		text-align: center;
	}

	.google-signin-btn img {
		margin-right: 10px;
	}

	.divider {
		font-size: 1.5em;
		color: #fff;
	}

	.auth-forms {
		width: 300px; /* Adjusted width for smaller size */
		height: 450px; /* Adjusted height for smaller size */
		/* Other styles for the auth-forms... */
	}
</style>
