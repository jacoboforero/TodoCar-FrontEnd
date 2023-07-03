<script>
	import BannerImage from "../Landing/BannerImage.svelte";
  import Maincontent from "../Landing/maincontent.svelte";
  import Footer from "../Layout/Footer.svelte";
import Header from "../Layout/Header.svelte";
</script>

<main>
	<Header></Header>
	<BannerImage></BannerImage>
	<Maincontent></Maincontent>
	<Footer></Footer>
</main>

<style>
	main {
		text-align: center;
		max-width: 240px;
		margin: 0 auto;
	}

	

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>