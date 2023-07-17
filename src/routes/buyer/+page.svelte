<script>
	import Footer from '../../Layout/Footer.svelte';
	import Header from '../../Layout/Header.svelte';
	import ServiceCard from '../../Buyer/serviceCard.svelte';
	let user = 'Jacobo';
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
	<div id="post-button-square">
		<p>Hi {user},<br /> Get matched with the right service provider.</p>

		<button id="post-button" />
	</div>
</div>

<div class="gigs-showcase">

<!-- Add showcase of service cards that may be relevant to the user -->


</div>

<style>
	.category-buttons {
		display: flex;
		justify-content: space-between;
		background-color: #212324;
		width: 100%;
		height: 30px;
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
		height: 1px;
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
		display: flex;
		width: 61%;
		height: 60%;
		background-color: #838181;
		border-radius: 10px;
	}

	.banner-section #post-button-square {
		display: flex;
		justify-content: center;
		align-content: space-around;
		flex-direction: column;

		width: 17%;
		height: 70%;
		background-color: black;
		margin-right: 30px;
		border-radius: 10px;
	}

	.banner-section #post-button-square p {
		color: white;
		text-align: center;
		font-size: 15px;
		margin: 10px;
	}

	.banner-section #post-button-square #post-button {
		margin: 10px;
		width: 50%;
		height: 14%;
		background-color: red;
		border: none;
		border-radius: 7px;
		align-self: center;
	}
</style>
