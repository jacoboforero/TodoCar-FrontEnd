<script>
	import Header from '../../Layout/Header.svelte';
</script>

<Header />

<!--  modify this section to have dynamic data in order to display the most relevant services to the particular buyer -->

<div class="category-buttons">
	<button>Oil Change</button>
	<button>Towing</button>
	<button>Car Wash</button>
	<button>Touch Up specialist</button>
	<button>Flat Tire aid</button>
	<button>Car Detailing</button>
	<button>Upholstery</button>
	<button>Mechanic</button>
</div>

<div id="dividing-line" />

<!-- Modify this section to display the banner image dynamically, make it an informational slide show (refer to Fiverr buyer homepage to see inspiration) -->

<div class="banner-section">
	<div id="banner" />
	<div id="post-button" />
</div>

<div class="gigs-showcase" />

<footer />

<style>
	.category-buttons {
		display: flex;
		justify-content: space-between;
		background-color: #212324;
		width: 100%;
		height: 44px;
	}

	.category-buttons button {
		background-color: inherit;
		color: white;
		border: none;
		flex-grow: 1;
		margin: 0 10px;
		text-align: center;
		font-size: 12px;
	}

	#dividing-line {
		background-color: white;
		width: 100%;
		height: 2px;
		background-color: #838181;
	}

	.banner-section {
		display: flex;
		justify-content: space-around;
		width: 100%;
		height: 300px;
		background-color: #212324;
		align-items: center;
	}

	.banner-section #banner {
		width: 61%;
		height: 60%;
		background-color: #838181;
		border-radius: 10px;
	}

	.banner-section #post-button {
		width: 14%;
		height: 60%;
		background-color: black;
		margin-right: 30px;
		border-radius: 10px;
	}
</style>
