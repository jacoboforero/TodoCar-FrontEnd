<script>
	import Footer from '../../Layout/Footer.svelte';
	import Header from '../../Layout/Header.svelte';

	// Mock function to simulate fetching seller data
	const getSellerData = () => {
		return {
			name: 'John Doe',
			contact: {
				email: 'johndoe@example.com',
				phone: '+1234567890'
			},
			description:
				"With over 10 years of experience in the car industry, I specialize in providing top-notch car maintenance services, including oil changes, brake repairs, and performance enhancements. Your vehicle's care and performance are my top priorities.",
			location: '1234 Main St, Anytown, AT 12345',
			servicesOffered: [
				'Oil Change',
				'Brake Repair',
				'Performance Enhancements',
				'Tire Rotation',
				'Car Detailing'
			]
		};
	};

	let sellerData = getSellerData();

	/**
	 * @type {any[]}
	 */
	let jobs = [];

	let isLoading = true;
	// Simulate loading from a backend
	setTimeout(() => {
		isLoading = false;
		for (let i = 1; i <= 3; i++) {
			jobs.push({
				username: ` User ${i}`,
				location: `Some place ${i}`,
				price: i * 3 + 7,
				job_description: 'my car broke down, need help fixing it'
			});
		}
	}, 2000);

	//reactivity

	let isDescriptionExpanded = false;

	function toggleDescription() {
		isDescriptionExpanded = !isDescriptionExpanded;
	}
</script>

<main>
	<Header />

	<div id="main_container">
		<div id="profile_section">
			<div id="profile_image">
				<!-- Use the `src` attribute to bind the profile image URL -->
				<img src="" alt="" />
			</div>
			<h1>{sellerData.name}</h1>
			<div class="seller_info">
				<div class="info_item">
					<span class="title">Email:</span><span class="content">{sellerData.contact.email}</span>
				</div>
				<div class="info_item">
					<span class="title">Phone:</span><span class="content">{sellerData.contact.phone}</span>
				</div>
				<div class="info_item">
					<span class="title">Description:</span><span class="content"
						>{sellerData.description}</span
					>
				</div>
				<div class="info_item">
					<span class="title">Location:</span><span class="content">{sellerData.location}</span>
				</div>
				<h2>Services Offered:</h2>
				<ul>
					{#each sellerData.servicesOffered as service}
						<li>{service}</li>
					{/each}
				</ul>
			</div>
		</div>
		<div id="jobs_section">
			<h1>Jobs for you</h1>
			{#if isLoading}
				<p>Loading...</p>
			{:else}
				{#each jobs as job}
					<div id="box">
						<h2>{job.username}</h2>
						<p>{job.job_description}</p>
						<p>{job.location}</p>
						<p>${job.price}</p>
					</div>
				{/each}
			{/if}
		</div>
	</div>
	<Footer />
</main>

<style>
	#main_container {
		display: flex;
		justify-content: flex-start;
		padding-top: 60px;
		align-items: center;
		min-height: 100vh;
		font-family: 'Jost', sans-serif;
		background: linear-gradient(to bottom, #b91a1a, #016473);
		margin: 0;
		padding: 0;
		text-align: center;
		gap: 20px;
	}

	#profile_section {
		width: 30vw;
		min-height: 90vh;
		background: #ffffff;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
		border-radius: 10px;
		padding: 20px;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
		overflow: hidden;
	}

	#profile_image img {
		width: 150px;
		height: 150px;
		border-radius: 50%;
		object-fit: cover;
		margin-bottom: 20px;
		border: 3px solid #eaeaea;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
	}

	.info_item {
		display: flex;
		justify-content: space-between;
		width: 100%;
		margin-bottom: 10px; /* Adjust spacing between items as needed */
	}

	.title {
		text-align: left;
		padding-right: 10px;
		flex-basis: 40%;
	}

	.content {
		text-align: right;
		padding-left: 10px;
		flex-basis: 60%;
	}

	.seller_info {
		align-self: flex-start;
		text-align: center;
	}

	.seller_info h2,
	.seller_info ul,
	.seller_info ul li {
		text-align: left;
	}

	.seller_info h2 {
		margin-bottom: 10px;
	}

	.seller_info ul {
		list-style: none;
		padding: 0;
		margin-bottom: 20px;
	}

	.seller_info ul li {
		margin-bottom: 5px;
	}
	#jobs_section {
		display: flex;
		width: 65vw;
		min-height: 62vh;
		background: #fefefe;
		flex-direction: column;
		justify-content: flex-start;
		align-items: start;
		padding: 20px;
		border-radius: 10px;
	}

	#jobs_section #box {
		display: flex;
		width: 90%;
		background: #ffffff;
		padding: 20px;
		margin: 10px 0;
		border-radius: 10px;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
		flex-direction: column;
		align-items: flex-start;
		justify-content: flex-start;
	}
</style>
