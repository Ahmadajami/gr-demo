<script lang="ts">
	let imgContainer: HTMLElement;

	function stopImageRotation(intervalId: any) {
		if (intervalId) {
			clearInterval(intervalId);
		}
	}

	$effect(() => {
		if (!imgContainer) return;
		const intervalId = setInterval(() => {
			let last = imgContainer!.firstElementChild;
			last!.remove();
			imgContainer!.appendChild(last!);
		}, 2000);
		return () => {
			stopImageRotation(intervalId);
		};
	});
</script>

<section class="soso">
	<div id="img-container" bind:this={imgContainer}>
		<div class="box">
			<img src="https://i1.sndcdn.com/artworks-000137479333-rpqogd-t500x500.jpg" alt="" />
		</div>
		<div class="box">
			<img src="https://upload.wikimedia.org/wikipedia/en/7/76/Primetimeofyourlife.jpg" alt="" />
		</div>
		<div class="box">
			<img
				src="https://upload.wikimedia.org/wikipedia/en/8/84/RobotRock.DaftPunk.single.jpg"
				alt=""
			/>
		</div>
		<div class="box">
			<img src="https://i1.sndcdn.com/artworks-000655973617-9rv0tb-t500x500.jpg" alt="" />
		</div>
	</div>
</section>

<style>
	.soso {
		position: relative;
		z-index: -1;
		padding: clamp(3em, 6vw, 5em);
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column-reverse;
		gap: 2em;
		background: radial-gradient(var(--body-bg), #000);
	}
	#img-container {
		height: 230px;
		width: 230px;
		perspective: 500px;
		transform-style: preserve-3d;
	}
	.box {
		height: 300px;
		width: 300px;
		position: absolute;
		top: 50%;
		border: 1px solid #bbb;
		border-radius: 50%;
		box-shadow: 0 0 8px hsla(0deg, 0%, 0%, 75%);
		transition: 800ms ease-in-out;
		overflow: hidden;
	}
	.box img {
		width: 100%;
		height: 100%;
	}
	.box:first-of-type {
		right: 15%; /* Changed left to right */
		opacity: 0;
		z-index: 5;
		transform: translate(50%, -50%) rotateY(10deg); /* Changed translate and rotate */
	}
	.box:nth-of-type(2) {
		right: 20%; /* Changed left to right */
		opacity: 1;
		z-index: 5;
		transform: translate(50%, -50%) rotateY(10deg); /* Changed translate and rotate */
	}
	.box:nth-of-type(3) {
		right: 25%; /* Changed left to right */
		opacity: 0.75;
		z-index: 10;
		transform: scale3d(0.5, 0.5, 0.5) translate(50%, -50%) rotateY(10deg) translateZ(-40px); /* Changed translate and rotate */
	}
	.box:nth-of-type(4) {
		right: 30%; /* Changed left to right */
		opacity: 0.5;
		z-index: 5;
		transform: scale3d(0.5, 0.5, 0.5) translate(50%, -50%) rotateY(10deg) translateZ(-100px); /* Changed translate and rotate */
		color: #eee;
	}

	@media (width>768px) {
		.soso {
			flex-direction: row;
		}
		.box {
			height: 400px;
			width: 400px;
		}
	}
</style>
