<div class="bg-home-1">
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

	@media screen and (max-width: 408px) {
		.bg-home-1 {
			min-height: 40vh;
		}
		.text-title {
			font-size: 1.2rem;
		}
	}

	@media screen and (max-width: 360px) {
		.bg-home-1 {
			min-height: 30vh;
		}
	}
</style>
