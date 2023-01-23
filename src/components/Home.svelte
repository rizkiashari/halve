<div class="bg-home-1">
	<img src="/images/home-section.png" class="home-mobile" alt="section home" />
	<div class="container">
		<div class="section-home">
			<p class="font-caveat text-title">Let's fight hunger in Indonesia.</p>
		</div>
	</div>
</div>

<style>
	.bg-home-1 {
		background-image: url('/images/home-section.png');
		background-size: cover;
		background-position: center;
		min-height: 90vh;
		height: 100%;
		width: 100%;
	}

	.home-mobile {
		display: none;
	}

	.section-home {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		background-color: transparent;
	}

	.text-title {
		font-size: 2rem;
		background-color: transparent;
		max-width: fit-content;
		width: 100%;
	}

	@media screen and (max-width: 765px) {
		.bg-home-1 {
			min-height: 70vh;
		}

		.container {
			margin: 0 1rem;
		}

		.text-title {
			font-size: 1.8rem;
		}
	}

	@media screen and (max-width: 500px) {
		.bg-home-1 {
			background-image: none;
			position: relative;
			min-height: 40vh;
		}
		.text-title {
			font-size: 1.2rem;
		}

		.home-mobile {
			display: block;
			position: absolute;
			width: 100%;
			bottom: 0;
			left: 0;
			right: 0;
			margin-bottom: 1rem;
		}
	}

	@media screen and (max-width: 360px) {
		.bg-home-1 {
			min-height: 30vh;
		}
		.text-title {
			font-size: 1rem;
		}
	}
</style>
