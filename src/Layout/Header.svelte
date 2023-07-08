<script>
	import { redirect } from '@sveltejs/kit';
</script>

<header>
	<a href="/"> <div class="logo" /> </a>
	<nav>
		<a href="/about" class="button" rel="prefetch">About Us</a>
		<a href="/buyer">Find Talent</a>
		<a href="#">Do Work</a>
		<a href="#">Sign In / Join</a>
		<a href="#">FAQ</a>
	</nav>
	<input class="search-bar" type="search" placeholder="What service are you looking for?" />
	<select>
		<option value="en">Lang-Eng</option>
		<option value="es">Lang-Esp</option>
		<option value="fr">Lang-Fra</option>
		<!-- Add more options here for other languages -->
	</select>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		box-sizing: border-box;
		color: white;

		padding-right: 20px;
		padding-left: 20px;
		box-sizing: border-box;
		width: 100%;
		height: 80px;
		flex-shrink: 0;
		background: #212324;
		position: relative;
	}
	.logo {
		width: 52px;
		height: 37px;
		background-color: #b91a1a;
		border-radius: 1px;
	}
	nav {
		display: flex;
		gap: 40px;
		margin-right: auto;
		margin-left: 80px;
	}
	nav a {
		color: white;
		text-decoration: none;
		display: flex;
		flex-direction: column;
		flex-shrink: 0;
		color: #fff;
		font-size: 14px;
	}
	.search-bar {
		width: 400px;
		height: 25px;
		flex-shrink: 0;
		border-radius: 3px;
		color: #000;
		text-align: left;
		font-family: 'Times New Roman', Times, serif;
		margin-top: 10px;
		font-size: 16px;

		margin-right: -20px;
	}

	select {
		width: 132px;
		height: 32px;
		appearance: none;
		background: transparent;
		border: none;
		color: #fff;

		font-size: 17px;
		margin-right: -40px;

		margin-left: 40px;
		margin-top: 10px;
	}

	select::-ms-expand {
		display: none;
	}

	select:focus {
		outline: none;
	}
</style>
