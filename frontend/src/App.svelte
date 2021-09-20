<script>
	import Skills from "./Skills.svelte";
	import NavBar from "./NavBar.svelte";
	
	const name = "DAVID KIM";
	const job = "Software Engineer";
	const yearsExperience = new Date().getFullYear() - 2019;
</script>

<style>
	#intro {
		margin-left: auto;
		margin-right: auto;
		align-content: center;
		width: 500px;
	}

	#title {
		margin-left: auto;
		margin-right: auto;
		text-align: center;
		width: 500px;
	}
	#contact-info {
		margin: auto;
		padding-left: 15px;
	}

	.contact-images {
		width: 30px;
		height: 30px;
	}
	.contact-images:hover {
		transform: scale(1.5);
	}

	#heading {
		text-align: center;
		width: 500px;
	}
	#short-intro{
		margin-top: 30px;
		margin-bottom: 30px;
	}
	.name {
		margin-bottom: 0;
	}
	img {
		border-radius: 50%;
		max-width: 50%;
		height: auto;
		margin-left: auto;
		margin-right: auto;
		width: 500px;
	}
</style>

<div id="intro">
	<div id="title">
		<img
			src="./img/me_halloween_2014.jpg"
			alt="Me on Halloween 2014"
			width="250"
			height="250" />
	</div>

	<div id="heading">
		<h1 class="name">{name}</h1>
		<div id="contact-info">
			<a href="https://www.linkedin.com/in/dkim827/">
				<img
					class="contact-images"
					src="./img/linkedin.jpg"
					alt="My LinkedIn Page" />
			</a>
			<a
				href="mailto:davidkim827@gmail.com?subject=We Want to Hire YOU, David!">
				<img
					class="contact-images"
					src="./img/mail icon.png"
					alt="Email me!" />
			</a>
			<a href="https://github.com/davidkim827"><img
					class="contact-images"
					src="./img/github.png"
					alt="My Github Link!" /></a>
			<a
				href="https://www.google.com/maps/place/Brooklyn,+NY/@40.6451594,-74.0850816,11z/data=!3m1!4b1!4m5!3m4!1s0x89c24416947c2109:0x82765c7404007886!8m2!3d40.6781784!4d-73.9441579"><img
					class="contact-images"
					src="./img/location.jpeg"
					alt="Brooklyn is the best borough!" /></a>
		</div>
		<div id="short-intro">
			<p>{job} with {yearsExperience} years in Security</p>
		</div>
	</div>
</div>

<Skills />

<NavBar />
