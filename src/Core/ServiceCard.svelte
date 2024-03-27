<script>
	export let provider = {
		imgUrl:
			'https://fiverr-res.cloudinary.com/t_gig_cards_web_x2,q_auto,f_auto/gigs/192403028/original/302d5737af69903c1d188acbd81f528c6410aa44.jpg', // placeholder image URL
		profileImgUrl: 'https://placeimg.com/100/100/people', // placeholder profile image URL
		username: 'MikeCJones',
		starRating: 4.5,
		price: 50,
		job_description: 'I will do *sample job* using *sample tools*'
	};
</script>

<div class="provider-card">
	<div class="image-container">
		<img src={provider.imgUrl} alt={provider.username} class="service-image" />
	</div>
	<div class="user-info">
		<!-- svelte-ignore a11y-missing-attribute -->
		<img src={provider.profileImgUrl} class="profile-image" />
		<h2 id="username">{provider.username}</h2>
	</div>
	<div class="rating-container">
		<p id="job_description">{provider.job_description}</p>
		<div class="star-section">
			<img src="starRating.png" alt="star" class="star-image" />
			<p class="star-rating">{provider.starRating}</p>
		</div>
		<p id="price">${provider.price}</p>
	</div>
</div>

<style>
	.provider-card {
		width: 225px;
		border: 1px solid #ddd;
		border-radius: 10px;
		padding: 20px;
		margin: 10px;
		text-align: center;
		box-sizing: border-box;
		border: none;
	}

	/* Reset the default margins and set uniform margins */
	#price,
	#job_description,
	.star-rating {
		margin-top: 10px;
		margin-bottom: 10px;
	}

	#username {
		font-size: 15px;
		margin: 0; /* Removes any default margin */
		line-height: 1.2; /* Adjust line height if necessary */
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
		margin-top: 25px;
		font-size: 13px;
	}
	#job_description {
		font-size: 14px;
		margin-left: 4px;
	}

	.rating-container {
		text-align: left;
	}

	.star-section {
		display: flex;
		align-items: center;
		gap: 5px; /* spacing between the image and text */
	}

	.star-image {
		width: 20px;
		height: 20px;
		border-radius: 50%;
	}

	.star-rating {
		margin: 0;
		font-size: 16px;
		font-weight: 700;
	}

	#price {
		margin-left: 4px;
	}

	.image-container {
		width: 100%;
		height: 125px; /* Adjust according to your requirement */
		overflow: hidden;
		position: relative;
		margin-bottom: -15px;
		border-radius: 10px;
	}

	.service-image {
		width: 100%;
		height: 100%;
		object-fit: cover; /* This ensures the image covers the whole area without distortion */
		object-position: center; /* This ensures the image is centered */
	}

	.user-info {
		display: flex;
		align-items: center; /* Ensures vertical centering */
		justify-content: center;
		gap: 10px;
	}

	.profile-image {
		width: 25px; /* Adjust according to your requirement */
		height: 25px; /* Adjust according to your requirement */
		border-radius: 50%; /* This makes the image circular */
		object-fit: contain;
		object-position: center;
		margin-left: -50px;
		margin-top: 19px;
		margin-bottom: 0;
	}
</style>
