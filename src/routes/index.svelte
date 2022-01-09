<script>
	import Line from '$lib/Line.svelte';
	import H2 from '$lib/H2.svelte';
	import Contact from '$lib/Contact/Contact.svelte';
</script>

<svelte:head>
	<title>VOID Development - Custom Websites and Software Development</title>
	<meta
		name="description"
		content="VOID Development is a web development company based out of Lexington, KY."
	/>
</svelte:head>

<div class="flex flex-col gap-8 p-8 sm:py-16 sm:px-16 lg:px-32">
	<!-- Landing -->

	<section id="about" class="flex flex-col items-center gap-16">
		<h1 class="text-left text-6xl font-extrabold tracking-normal">
			<ol class="flex flex-col gap-8 list-none">
				<li>DESIGN</li>
				<li>DEVELOP</li>
				<li>UPDATE</li>
			</ol>
		</h1>
		<Line />
	</section>

	<!-- Design -->

	<section id="design" class="flex flex-col items-center gap-8">
		<div
			class="flex flex-col gap-8 justify-start items-center w-full md:flex-row md:justify-start md:self-start"
		>
			<!-- Icon -->
			<div class="md:absolute md:left-0 md:flex md:justify-center md:items-center md:w-full">
				<div class="w-14 h-14">
					<div id="design-icon" class="p-1 rounded-full shadow">
						<div class="p-3 bg-white rounded-full">
							<svg
								class="w-6 h-6"
								fill="none"
								stroke="currentColor"
								viewBox="0 0 24 24"
								xmlns="http://www.w3.org/2000/svg"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M15.232 5.232l3.536 3.536m-2.036-5.036a2.5 2.5 0 113.536 3.536L6.5 21.036H3v-3.572L16.732 3.732z"
								/>
							</svg>
						</div>
					</div>
				</div>
			</div>
			<!-- Header -->
			<H2><svelte:fragment>DESIGN</svelte:fragment></H2>
		</div>
		<!-- content -->
		<p class="w-full">
			Every home constructed starts with a blueprint, and every website that is developed starts
			with a design! With VOID Development we will personally work with you to achieve a design that
			you will be happy with. Whether you already have a ton of ideas in mind, or you don't know
			where to start, we will help get the job done and make sure that your own personal touch is in
			the design. We don't just buy a template off of the internet and apply it to your site and
			hope that it matches your vision close enough, we custom code our websites around
			<em class="not-italic font-bold">YOU</em>.
		</p>
		<p class="w-full">
			Minimalist, <span class="text-pink-600 italic">artsy</span>, or
			<span class="font-bold">bold</span>, no matter your style we can get it translated to a
			website that accurately represents you or your business.
		</p>
		<Line />
	</section>

	<!-- Develop -->

	<section id="develop" class="flex flex-col items-center gap-8">
		<div
			class="flex flex-col gap-8 justify-center items-center md:flex-row md:justify-start md:self-start"
		>
			<!-- Icon -->
			<div class="md:absolute md:left-0 md:flex md:justify-center md:items-center md:w-full">
				<div
					class="flex justify-center items-center w-14 h-14 bg-white border-4 border-black rounded-full shadow"
				>
					<svg
						class="w-6 h-6"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"
						/>
					</svg>
				</div>
			</div>
			<!-- Header -->
			<H2><svelte:fragment>DEVELOP</svelte:fragment></H2>
		</div>
		<p class="w-full">
			All of our websites are custom coded using best practices. We don't hack together messy
			unmaintainable code because we plan on the being the one to maintain the site! With
			traditional web development companies the faster and messier your site is developed, the
			better. Once it's built they can just charge you an hourly rate to fix it.
		</p>
		<p class="w-full">
			Another advantage for our approach to web development is speed. Our sites are <em
				class="italic font-bold">FAST</em
			>. A fast is website is important to your users, but it's also important for SEO (search
			engine optimization), helping you website get discovered by new clients. Search engines don't
			want to recommend a slow, bloated site to their users, it makes them look bad!
		</p>
		<p class="w-full">
			Accessibility is a top priority for us as well. We ensure that your website is accessible to
			everyone. People with 20/20 vision can easily read text by making text large enough and with
			appropriate contrast, and screen readers will know what they looking at due to our code being
			semantic and correctly structured.
		</p>
		<Line />
	</section>

	<!-- Update -->
	<section id="update" class="flex flex-col items-center gap-8">
		<div
			class="flex flex-col gap-8 justify-center items-center md:flex-row md:justify-start md:self-start"
		>
			<!-- Icon -->
			<div class="md:absolute md:left-0 md:flex md:justify-center md:items-center md:w-full">
				<div
					class="flex justify-center items-center w-14 h-14 bg-white border-4 border-black rounded-full shadow"
				>
					<svg
						class="w-6 h-6"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"
						/>
					</svg>
				</div>
			</div>
			<!-- Header -->
			<H2><svelte:fragment>UPDATE</svelte:fragment></H2>
		</div>
		<p class="w-full">
			Once your project is complete, it will be new and shiny! What about in a year or two? The web
			changes at breakneck speeds and what might look sleek and modern today, will look old and
			outdated within a few months. That's where regular updates come into play. Security patches,
			content updates and making sure your website stays modern are all important to your businesses
			reputation. If your website was built by VOID Development and you stay on our VOID plan, all
			of these services are included at no extra cost! No hourly rates, no negotiating, just a
			modern, up to date website, that stays that way.
		</p>
		<p>
			What if you change your mind on some design aspects or want to update some text on your
			website? As long as you are signed up for our VOID plan you don't have to worry about getting
			hit with an hourly rate for website updates, just send us the new content and we'll get it
			done!
		</p>
		<Line />
	</section>

	<!-- Contact -->
	<section id="contact" class="flex flex-col items-center gap-8 scroll-m-32">
		<!-- Icon -->
		<div
			class="flex justify-center items-center w-14 h-14 bg-white border-4  border-black rounded-full shadow"
		>
			<svg
				class="w-6 h-6"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
				/>
			</svg>
		</div>
		<!-- Header -->
		<H2><svelte:fragment>CONTACT</svelte:fragment></H2>
		<Contact companyPhone="859-795-7899" companyEmail="info@voiddev.io" />
	</section>
</div>

<style>
	#about {
		min-height: calc(100vh - 6rem);
	}

	#design-icon {
		background: rgb(0, 188, 255);
		background: linear-gradient(135deg, rgba(0, 188, 255, 1) 0%, rgba(253, 0, 255, 1) 100%);
	}
</style>
