<script>
	import Navbar from "$lib/components/Navbar.svelte";
	import Footer from "$lib/components/Footer.svelte";

	const teamMembers = [
		{
			name: "David Hidalgo-Gato",
			role: "Chief Executive Officer",
			image: "/team-member-3.webp"
		},
		{
			name: "Ben Rosand",
			role: "Chief Technology Officer",
			image: "/team-member-1.webp"
		},
		{
			name: "Blake Birkenfeld",
			role: "Chief Operating Officer",
			image: "/team-member-2.webp"
		},
		{
			name: "Jackson Pullman",
			role: "Chief Product Officer",
			image: "/team-member-4.webp"
		},
		{
			name: "Patrick Hunt",
			role: "Chief Medical Adviser",
			image: "/team-member-5.webp"
		}
	];
</script>

<main class="font-sans text-gray-900 antialiased selection:bg-primary-200 selection:text-primary-900">
	<Navbar />

	<!-- Hero Section -->
	<section class="relative overflow-hidden border-b border-gray-200 bg-bg-light pt-20 pb-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="max-w-3xl">
				<!-- Badge -->
				<div class="mb-8 inline-flex items-center gap-2 rounded-full border border-primary-200 bg-primary-50 px-3 py-1 text-[10px] font-bold tracking-widest text-primary-700 uppercase">
					<span class="text-primary-500">Team</span>
					Clinical AI Researchers from Yale
				</div>

				<!-- Headline -->
				<h1 class="mb-6 text-6xl font-medium tracking-tight text-navy">
					Meet the team behind Cleo Health
				</h1>

				<!-- Subhead -->
				<p class="mb-10 max-w-xl text-lg leading-relaxed text-slate">
					Our journey began as <strong class="font-semibold text-navy">Clinical AI researchers at Yale University</strong>. We've been surrounded by healthcare providers our entire lives — we see meaningful purpose in creating tools that make your lives easier.
				</p>
			</div>
		</div>
	</section>

	<!-- Mission Section -->
	<section class="py-24 border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="grid grid-cols-1 gap-16 lg:grid-cols-2">
				<!-- Left -->
				<div>
					<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[01] Our Mission</div>
					<h2 class="text-4xl font-medium tracking-tight text-navy">
						Revolutionizing Acute Care through AI
					</h2>
				</div>

				<!-- Right -->
				<div class="flex flex-col justify-center">
					<p class="text-lg leading-relaxed text-slate mb-8">
						Cleo Health's mission is to revolutionize the field of <strong class="text-navy">Acute Care</strong> through advanced AI documentation systems. We aim to enhance the efficiency and effectiveness of healthcare providers by automating the documentation process, thereby allowing them to dedicate more time to <strong class="text-navy">patient care</strong>.
					</p>
					<div class="border-l-2 border-primary-300 pl-6">
						<p class="text-sm leading-relaxed text-slate italic">
							"We see meaningful purpose in creating tools that make healthcare providers' lives easier."
						</p>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Team Grid Section -->
	<section class="py-24 bg-white">
		<div class="mx-auto max-w-[1400px] px-6">
			<!-- Section Header -->
			<div class="mb-16 text-center">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[02] Leadership</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">The people driving our vision</h2>
			</div>

			<!-- Team Grid - 3 columns -->
			<div class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-3">
				{#each teamMembers as member}
					<div class="group">
						<!-- Photo Container -->
						<div class="relative mb-6 overflow-hidden rounded-lg bg-bg-light aspect-[4/5]">
							<!-- Background Pattern -->
							<div class="absolute inset-0 opacity-30"
								style="background-image: radial-gradient(circle at 2px 2px, rgba(2, 158, 181, 0.2) 1px, transparent 0); background-size: 16px 16px;">
							</div>

							<!-- Image -->
							<img
								src={member.image}
								alt={member.name}
								class="relative z-10 h-full w-full object-cover object-top transition-transform duration-500 group-hover:scale-105"
							/>

							<!-- Hover Overlay -->
							<div class="absolute inset-0 z-20 bg-gradient-to-t from-accent-dark/80 via-transparent to-transparent opacity-0 transition-opacity duration-300 group-hover:opacity-100"></div>

							<!-- Role Badge on Hover -->
							<div class="absolute bottom-4 left-4 right-4 z-30 translate-y-4 opacity-0 transition-all duration-300 group-hover:translate-y-0 group-hover:opacity-100">
								<div class="inline-block rounded bg-primary-500 px-3 py-1 text-[10px] font-bold tracking-widest text-white uppercase">
									{member.role}
								</div>
							</div>
						</div>

						<!-- Info -->
						<div class="text-center">
							<h3 class="mb-1 text-xl font-medium text-navy">{member.name}</h3>
							<p class="text-sm text-slate">{member.role}</p>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Values Section -->
	<section class="py-24 bg-bg-light border-t border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-12 text-center">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[03] Our Values</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">What drives us every day</h2>
			</div>

			<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
				<!-- Value 1 -->
				<div class="rounded-lg border border-gray-200 bg-white p-8">
					<div class="mb-4 inline-block rounded bg-primary-100 px-2 py-1 text-[10px] font-bold tracking-widest text-primary-700 uppercase">
						Patient First
					</div>
					<h3 class="mb-3 text-lg font-bold text-navy">Focus on care, not paperwork</h3>
					<p class="text-sm leading-relaxed text-slate">
						Every feature we build is designed to give clinicians more time with patients. We believe documentation should support care, not distract from it.
					</p>
				</div>

				<!-- Value 2 -->
				<div class="rounded-lg border border-gray-200 bg-white p-8">
					<div class="mb-4 inline-block rounded bg-accent-light/30 px-2 py-1 text-[10px] font-bold tracking-widest text-primary-700 uppercase">
						Clinical Excellence
					</div>
					<h3 class="mb-3 text-lg font-bold text-navy">Built by healthcare experts</h3>
					<p class="text-sm leading-relaxed text-slate">
						Our team understands the nuances of acute care. We build with clinical accuracy and real-world workflow integration in mind.
					</p>
				</div>

				<!-- Value 3 -->
				<div class="rounded-lg border border-gray-200 bg-white p-8">
					<div class="mb-4 inline-block rounded bg-bg-box px-2 py-1 text-[10px] font-bold tracking-widest text-navy uppercase">
						Trust & Security
					</div>
					<h3 class="mb-3 text-lg font-bold text-navy">HIPAA-compliant by design</h3>
					<p class="text-sm leading-relaxed text-slate">
						Patient data security is non-negotiable. We maintain the highest standards of compliance and data protection in everything we do.
					</p>
				</div>
			</div>
		</div>
	</section>

	<Footer
		ctaHeadline="Join our mission to<br>transform acute care"
		ctaSubtext="We're building the future of healthcare documentation. Get in touch to learn more."
	/>
</main>
