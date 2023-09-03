<script>
	import Footer from '../../Layout/Footer.svelte';
	import Header from '../../Layout/Header.svelte';
	import ServiceCard from '../../Core/ServiceCard.svelte';

	let user = 'Jacobo';
	/**
	 * @type {any[]}
	 */
	let providers = [];

	// Implement a loading state
	let isLoading = true;

	// Simulate loading from a backend
	setTimeout(() => {
		isLoading = false;
		for (let i = 1; i <= 5; i++) {
			providers.push({
				imgUrl:
					'https://fiverr-res.cloudinary.com/t_gig_cards_web_x2,q_auto,f_auto/gigs/192403028/original/302d5737af69903c1d188acbd81f528c6410aa44.jpg',
				profileImgUrl: '/expertConsultantPhoto.avif',
				username: ` User ${i}`,
				starRating: 4.5,
				price: 50,
				job_description: 'I will do *sample job* using *sample tools*'
			});
		}
	}, 2000);
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

<div class="banner-section">
	<div id="banner" />
	<div id="post-button-square">
		<p>Hi {user},<br /> Get matched with the right service provider. By posting a request</p>

		<button id="post-button">Post</button>
	</div>
</div>

<h2 id="services-heading">Relevant services</h2>

<!-- Display a loading state -->
{#if isLoading}
	<p>Loading...</p>
{:else}
	<div class="gigs-showcase">
		{#each providers as provider}
			<ServiceCard {provider} />
		{/each}
	</div>
{/if}

<Footer />

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
		transition: background-color 0.3s ease;
	}

	.category-buttons button:hover {
		background-color: #333;
		cursor: pointer;
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

	#post-button {
		color: black;
		font-weight: 600;
	}

	#services-heading {
		margin-left: 50px;
		margin-bottom: 0;
	}

	.gigs-showcase {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 16px;
		padding: 20px;
	}
</style>
