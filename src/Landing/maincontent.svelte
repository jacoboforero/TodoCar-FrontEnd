<div id="welcome-section">
	<h1 class="title">Welcome to TodoCar</h1>
	<p class="description">
		TodoCar is a Super-app for the Car industry. A free marketplace where car dealers, body shops,
		and customers are brought united with service providers, optimizing each party’s time and money.
		A diverse variety of services can be offered and acquired and delivered on-site, in an open
		market fashion.
	</p>
</div>

<div class="section">
	<h2 class="subtitle">Popular Services</h2>
	<section class="services">
		<article class="service">
			<img class="service-img" src="/tradeInPhoto.avif" alt="Trade in offer by whole sellers" />
			<h2 class="service-title">Trade in offer by whole sellers</h2>
		</article>
		<article class="service">
			<img
				class="service-img"
				src="/expertConsultantPhoto.avif"
				alt="Dealer Advertising Expert Consultant"
			/>
			<h2 class="service-title">Dealer Advertising Expert Consultant</h2>
		</article>
		<article class="service">
			<img class="service-img" src="/carDetailingPhoto.avif" alt="Car Detailing" />
			<h2 class="service-title">Car Detailing</h2>
		</article>
	</section>
</div>

<div class="section" id="marketplace-section">
	<h1 class="title">One-Stop Automotive Marketplace</h1>
	<div class="section-content">
		<p class="description">
			Find a wide range of automotive services for dealerships, body shops, and individual car
			owners, all in one convenient location.
		</p>
		<img class="section-img" src="/handsShaking.png" alt="Hands shaking in front of car" />
	</div>
</div>

<div class="section" id="section-2">
	<h1 class="title">Save Time and Money:</h1>
	<div class="section-content">
		<img class="section-img" src="/saveTimeAndMoney.png" alt="people shaking hands" />
		<p class="description">
			Compare quotes, read reviews, and choose the best service provider to suit your needs and
			budget
		</p>
	</div>
</div>

<style>
	#welcome-section {
		width: 100%;
		height: 260px;
		background: #212324;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
		padding-top: 15px;
		padding-bottom: 80px;
	}

	#welcome-section .title {
		color: #fff;
		font-size: 65px;
	}

	.description {
		color: #fff;
		text-align: left;
		font-size: 22px;
		margin-left: 40px;
	}

	.services {
		display: flex;
		justify-content: space-between;
	}

	.subtitle {
		font-size: 40px;
	}

	.service {
		flex: 1 1 0;
		text-align: center;
		width: 345px;
		height: 404.804px;
	}

	.service-img {
		margin-top: 50px;
		width: 345px;
		height: 404.804px;
		object-fit: cover;
		border-radius: 10px;
	}

	.section {
		width: 100%;
		height: 100vh; /* This will make the section take up the full height of the viewport */
	}

	#marketplace-section {
		background: #016473;
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		padding-top: 20px;
		padding-bottom: 20px;
	}

	#marketplace-section .title {
		color: #fff;
		font-size: 65px;
		margin-left: 70px;
	}

	#marketplace-section .section-content {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		height: 100%;
	}

	#marketplace-section .section-content p {
		width: 555px;
		height: 363px;
		color: #fff;
		font-size: 40px;
	}

	#marketplace-section .section-img {
		width: 495px;
		height: 437px;
		max-width: 100%; /* This ensures the image does not exceed its container */
		margin-right: 200px;
		border-radius: 25px;
	}

	#section-2 {
		background: #60232c;
		padding-bottom: 20px;
		padding-top: 20px;
	}

	#section-2 .title {
		color: #fff;
		font-size: 65px;
		text-align: right;
		margin-right: 70px;
	}

	#section-2 .section-img {
		width: 495px;
		height: 437px;
		max-width: 100%; /* This ensures the image does not exceed its container */
		margin-left: 180px;
		border-radius: 25px;
		margin-bottom: 150px;
	}

	#section-2 .section-content {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		height: 100%;
	}

	#section-2 .section-content p {
		width: 555px;
		height: 363px;
		color: #fff;
		font-size: 40px;
		margin-right: 40px;
	}
</style>
