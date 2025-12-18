<script>
	import { Play } from 'lucide-svelte';
	import Navbar from "$lib/components/Navbar.svelte";
	import Footer from "$lib/components/Footer.svelte";

	let openFaq = $state(0);
	let activeTab = $state('standalone');
	let videoPlaying = $state(false);

	const steps = [
		{
			number: "01",
			title: "Create Your Account",
			description: "Chat with our team to start your free trial today. No credit card or payment information required."
		},
		{
			number: "02",
			title: "Swap Your Phone Number",
			description: "Follow a quick guided step-by-step to connect your existing clinic line."
		},
		{
			number: "03",
			title: "Start Taking Calls",
			description: "You're live! Cleo answers and triages patient calls automatically from day one."
		}
	];

	const standaloneFeatures = [
		{ title: "Appointment Requests", description: "Cleo notes the patient's preferred provider and availability, saving valuable time for staff." },
		{ title: "Symptom Changes", description: "Cleo captures symptom updates and alerts staff to potential high-risk concerns." },
		{ title: "Human Connection", description: "Cleo understands when it's time to hand off to a human, ensuring patients feel heard." }
	];

	const integrationFeatures = [
		{ title: "Prescription Needs", description: "Cleo gathers medication and refill details upfront to minimize back-and-forth for staff." },
		{ title: "Multilingual Conversation", description: "Cleo listens and responds in multiple languages to help patients communicate comfortably." },
		{ title: "Care Plan Education", description: "Cleo understands patient questions about their care plan and logs details for clinical teams." }
	];

	const faqs = [
		{
			question: "Can I send calls to a human?",
			answer: "Yes, Cleo intelligently routes calls that require human attention to your staff. It understands context and urgency, ensuring seamless handoffs when patients need to speak with a person."
		},
		{
			question: "Can it speak multiple languages?",
			answer: "Cleo supports multiple languages and can seamlessly switch between them during a conversation, helping patients communicate in their preferred language."
		},
		{
			question: "Is it secure?",
			answer: "Absolutely. Cleo is HIPAA-compliant and SOC 2 Type II certified. All data is encrypted in transit and at rest, and we provide BAAs for all customers."
		},
		{
			question: "Do you train on my data?",
			answer: "No. Your patient data is never used to train our AI models. Your data remains completely private and is only used to provide services to your practice."
		},
		{
			question: "What if my question isn't answered here?",
			answer: "Our team is happy to answer any questions you have. Book a call with us or reach out to support@cleo-ai.co and we'll get back to you promptly."
		}
	];
</script>

<main class="font-sans text-gray-900 antialiased selection:bg-primary-200 selection:text-primary-900">
	<Navbar />

	<!-- Hero Section -->
	<section class="relative overflow-hidden border-b border-gray-200 bg-bg-light pt-20 pb-16">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="max-w-3xl">
				<!-- Badge -->
				<div class="mb-8 inline-flex items-center gap-2 rounded-full border border-primary-200 bg-primary-50 px-3 py-1 text-[10px] font-bold tracking-widest text-primary-700 uppercase">
					<span class="text-primary-500">Product</span>
					AI Call Center
				</div>

				<!-- Headline -->
				<h1 class="mb-6 text-6xl font-medium tracking-tight text-navy lg:text-7xl">
					Modernize Patient Access with Cleo
				</h1>

				<!-- Subhead -->
				<p class="mb-10 max-w-xl text-lg leading-relaxed text-slate">
					Automate your phone lines with AI that triages every conversation — <strong class="font-semibold text-navy">no wait times, no missed connections, no phone tag.</strong>
				</p>

				<!-- Buttons -->
				<div class="mb-24 flex items-center gap-4">
					<a href="https://app.cleohealth.io/signup" class="bg-primary-500 px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-primary-600 uppercase rounded">
						Start Now
					</a>
					<a href="#features" class="border border-gray-200 bg-white px-6 py-3 text-[11px] font-bold tracking-widest text-navy transition-colors hover:bg-gray-50 uppercase rounded">
						Learn More
					</a>
				</div>
			</div>

			<!-- Stats bar -->
			<div class="flex flex-wrap items-center justify-between gap-8 border-t border-gray-200 pt-8">
				<div>
					<div class="text-3xl font-medium text-navy">0 min</div>
					<div class="text-xs text-slate">Average wait time</div>
				</div>
				<div>
					<div class="text-3xl font-medium text-navy">100%</div>
					<div class="text-xs text-slate">Call answer rate</div>
				</div>
				<div>
					<div class="text-3xl font-medium text-navy">60%</div>
					<div class="text-xs text-slate">Less front desk workload</div>
				</div>
				<div>
					<div class="text-3xl font-medium text-navy">24/7</div>
					<div class="text-xs text-slate">Always available</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Value Proposition + Video -->
	<section class="py-24 border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[01] Why Cleo</div>
			<div class="flex flex-col lg:flex-row lg:items-end lg:justify-between gap-8 mb-16">
				<h2 class="text-5xl lg:text-6xl font-medium tracking-tight text-navy leading-[1.1] max-w-2xl">
					Stay 5 Steps Ahead,<br>
					<span class="text-primary-500">Not 5 Calls Behind.</span>
				</h2>
				<p class="text-lg leading-relaxed text-slate max-w-md">
					Cleo manages your call volume in real-time, keeping your phone line moving, schedules full, and patients connected to care.
				</p>
			</div>

			<!-- Video -->
			<div class="relative aspect-video rounded-2xl overflow-hidden shadow-2xl">
				{#if !videoPlaying}
					<!-- Custom Thumbnail -->
					<button
						onclick={() => videoPlaying = true}
						style="cursor: pointer;"
						class="absolute inset-0 w-full h-full group bg-accent-dark"
					>
						<!-- Geometric Pattern Background -->
						<div class="absolute inset-0 opacity-10 group-hover:opacity-15 transition-opacity duration-500"
							style="background-image: linear-gradient(#ffffff 1px, transparent 1px), linear-gradient(to right, #ffffff 1px, transparent 1px); background-size: 80px 80px; transform: perspective(500px) rotateX(60deg) translateY(-50px) scale(2);">
						</div>
						<div class="absolute inset-0 bg-gradient-to-b from-accent-dark via-transparent to-accent-dark"></div>

						<!-- Play button -->
						<div class="absolute inset-0 flex items-center justify-center z-10">
							<div class="flex items-center gap-3 px-6 py-3 rounded-lg bg-black/40 backdrop-blur-sm group-hover:bg-black/60 transition-all duration-300">
								<Play class="w-5 h-5 text-white" fill="currentColor" />
								<span class="text-white text-sm font-medium">Watch Video</span>
							</div>
						</div>
					</button>
				{:else}
					<!-- YouTube Embed -->
					<iframe
						src="https://www.youtube.com/embed/dWUxuTZzhsc?autoplay=1&rel=0"
						title="Cleo AI Call Center Demo"
						frameborder="0"
						allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
						allowfullscreen
						class="absolute inset-0 w-full h-full"
					></iframe>
				{/if}
			</div>
		</div>
	</section>

	<!-- Get Started Steps -->
	<section id="features" class="py-24 bg-bg-light border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[02] Get Started</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">Get Started Today</h2>
				<p class="mt-4 text-lg text-slate max-w-2xl">
					Cleo's call center is fully self-serve, so you can launch in three simple steps and start taking patient calls today.
				</p>
			</div>

			<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
				{#each steps as step}
					<div class="border-l-2 border-primary-500 pl-6">
						<div class="text-4xl font-medium text-primary-500 mb-4">{step.number}</div>
						<h3 class="text-lg font-bold text-navy mb-2">{step.title}</h3>
						<p class="text-sm leading-relaxed text-slate">{step.description}</p>
					</div>
				{/each}
			</div>

			<div class="mt-12">
				<a href="https://calendly.com/d/cr9g-6x9-xy8/cleo-health-introduction" target="_blank" class="inline-flex items-center gap-2 text-[11px] font-bold tracking-widest text-primary-600 hover:text-primary-700 uppercase">
					Talk To Sales
					<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
				</a>
			</div>
		</div>
	</section>

	<!-- Features Tabs -->
	<section class="py-24 border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-12">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[03] Features</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">Instant Setup, Seamless Integration</h2>
			</div>

			<!-- Tabs -->
			<div class="mb-12 flex border-b border-gray-200">
				<button
					onclick={() => activeTab = 'standalone'}
					class="cursor-pointer border-b-2 px-6 py-4 text-[11px] font-bold tracking-widest uppercase transition-all {activeTab === 'standalone' ? 'border-primary-500 text-navy' : 'border-transparent text-slate hover:text-navy'}"
				>
					<span class="mr-2 {activeTab === 'standalone' ? 'text-primary-500' : 'text-gray-300'}">01</span> Stand-alone
				</button>
				<button
					onclick={() => activeTab = 'integration'}
					class="cursor-pointer border-b-2 px-6 py-4 text-[11px] font-bold tracking-widest uppercase transition-all {activeTab === 'integration' ? 'border-primary-500 text-navy' : 'border-transparent text-slate hover:text-navy'}"
				>
					<span class="mr-2 {activeTab === 'integration' ? 'text-primary-500' : 'text-gray-300'}">02</span> With Integration
				</button>
			</div>

			<!-- Tab Content Container -->
			<div class="min-h-[520px]">
			<!-- Stand-alone Content -->
			{#if activeTab === 'standalone'}
			<div class="grid grid-cols-1 gap-16 lg:grid-cols-2">
				<!-- Visual Mockup -->
				<div class="relative overflow-hidden rounded-lg bg-primary-500 p-8">
					<div class="rounded-lg bg-white shadow-xl">
						<!-- Header -->
						<div class="border-b border-gray-100 p-4 flex items-center justify-between">
							<div class="flex items-center gap-3">
								<div class="h-8 w-8 rounded-full bg-primary-100 flex items-center justify-center">
									<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="text-primary-600"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
								</div>
								<div>
									<div class="text-xs font-semibold text-gray-900">Incoming Call</div>
									<div class="text-[10px] text-gray-500">+1 (555) 234-5678</div>
								</div>
							</div>
							<div class="flex items-center gap-1">
								<div class="h-2 w-2 rounded-full bg-green-500 animate-pulse"></div>
								<span class="text-[10px] text-green-600 font-medium">Live</span>
							</div>
						</div>
						<!-- Conversation -->
						<div class="p-4 space-y-3">
							<div class="flex gap-3">
								<div class="h-6 w-6 rounded-full bg-gray-100 flex items-center justify-center text-[10px] font-bold text-gray-500">P</div>
								<div class="flex-1 rounded-lg bg-gray-50 p-3 text-xs text-gray-700">
									Hi, I'd like to schedule an appointment with Dr. Martinez for next week if possible.
								</div>
							</div>
							<div class="flex gap-3">
								<div class="h-6 w-6 rounded-full bg-primary-500 flex items-center justify-center">
									<svg width="12" height="12" viewBox="0 0 24 24" fill="white"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
								</div>
								<div class="flex-1 rounded-lg bg-primary-50 p-3 text-xs text-primary-900">
									I'd be happy to help you schedule an appointment with Dr. Martinez. I see availability on Tuesday at 2pm and Thursday at 10am. Which works better for you?
								</div>
							</div>
						</div>
						<!-- Status Bar -->
						<div class="border-t border-gray-100 p-3 bg-gray-50">
							<div class="flex items-center justify-between text-[10px]">
								<span class="text-gray-500">Appointment Request Detected</span>
								<span class="text-primary-600 font-semibold">Auto-logging to queue</span>
							</div>
						</div>
					</div>
					<!-- Background Pattern -->
					<div class="absolute inset-0 z-[-1]" style="background-image: radial-gradient(circle at 2px 2px, rgba(255,255,255,0.15) 1px, transparent 0); background-size: 20px 20px;"></div>
				</div>

				<!-- Content -->
				<div class="flex flex-col justify-center">
					<p class="mb-8 text-lg leading-relaxed text-slate">
						Cleo works independently from day one. No EHR integration required to start taking calls and improving patient access.
					</p>
					<div class="space-y-6">
						{#each standaloneFeatures as feature}
							<div class="border-l-2 border-primary-500 pl-6">
								<h3 class="mb-1 text-lg font-bold text-navy">{feature.title}</h3>
								<p class="text-sm leading-relaxed text-slate">{feature.description}</p>
							</div>
						{/each}
					</div>
					<div class="mt-10">
						<a href="https://app.cleohealth.io/signup" class="bg-primary-500 px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-primary-600 uppercase rounded">
							Start Free Trial
						</a>
					</div>
				</div>
			</div>
			{/if}

			<!-- Integration Content -->
			{#if activeTab === 'integration'}
			<div class="grid grid-cols-1 gap-16 lg:grid-cols-2">
				<!-- Visual Mockup -->
				<div class="relative overflow-hidden rounded-lg bg-accent-dark p-8">
					<div class="rounded-lg bg-white shadow-xl">
						<!-- Header -->
						<div class="border-b border-gray-100 p-4 flex items-center justify-between">
							<div class="text-xs font-semibold text-gray-900">EHR Integration Active</div>
							<div class="flex items-center gap-2">
								<div class="h-5 px-2 rounded bg-green-100 text-[10px] text-green-700 font-medium flex items-center">Connected</div>
							</div>
						</div>
						<!-- Content -->
						<div class="p-4 space-y-3">
							<div class="rounded border border-gray-100 p-3">
								<div class="flex items-center justify-between mb-2">
									<span class="text-[10px] font-semibold text-gray-500">PRESCRIPTION REFILL</span>
									<span class="text-[10px] text-primary-600">Auto-routed</span>
								</div>
								<div class="text-xs text-gray-900">Lisinopril 10mg - Patient: Sarah Johnson</div>
								<div class="mt-2 flex gap-2">
									<span class="px-2 py-0.5 rounded bg-primary-100 text-[10px] text-primary-700">Verified in EHR</span>
									<span class="px-2 py-0.5 rounded bg-gray-100 text-[10px] text-gray-600">Sent to pharmacy</span>
								</div>
							</div>
							<div class="rounded border border-primary-200 bg-primary-50 p-3">
								<div class="flex items-center justify-between mb-2">
									<span class="text-[10px] font-semibold text-primary-700">MULTILINGUAL CALL</span>
									<span class="text-[10px] text-primary-600">Spanish</span>
								</div>
								<div class="text-xs text-gray-900">Care plan question - Auto-translated and logged</div>
							</div>
							<div class="rounded border border-gray-100 p-3">
								<div class="flex items-center justify-between mb-2">
									<span class="text-[10px] font-semibold text-gray-500">CARE PLAN INQUIRY</span>
									<span class="text-[10px] text-green-600">Resolved</span>
								</div>
								<div class="text-xs text-gray-900">Post-discharge instructions clarified via AI</div>
							</div>
						</div>
						<!-- Footer -->
						<div class="border-t border-gray-100 p-3 bg-gray-50">
							<div class="flex items-center justify-between text-[10px]">
								<span class="text-gray-500">Today: 47 calls processed</span>
								<span class="text-green-600 font-semibold">100% logged to EHR</span>
							</div>
						</div>
					</div>
					<!-- Background Pattern -->
					<div class="absolute inset-0 z-[-1]" style="background-image: linear-gradient(45deg, rgba(255,255,255,0.05) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.05) 50%, rgba(255,255,255,0.05) 75%, transparent 75%, transparent); background-size: 40px 40px;"></div>
				</div>

				<!-- Content -->
				<div class="flex flex-col justify-center">
					<p class="mb-8 text-lg leading-relaxed text-slate">
						Integrate with your EHR to unlock deeper automation — prescriptions, care plans, and multilingual support all flow directly into your clinical workflows.
					</p>
					<div class="space-y-6">
						{#each integrationFeatures as feature}
							<div class="border-l-2 border-accent-dark pl-6">
								<h3 class="mb-1 text-lg font-bold text-navy">{feature.title}</h3>
								<p class="text-sm leading-relaxed text-slate">{feature.description}</p>
							</div>
						{/each}
					</div>
					<div class="mt-10">
						<a href="https://calendly.com/d/cr9g-6x9-xy8/cleo-health-introduction" target="_blank" class="bg-accent-dark px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-navy uppercase rounded">
							Talk to Sales About Integration
						</a>
					</div>
				</div>
			</div>
			{/if}
			</div>
		</div>
	</section>

	<!-- Integrations -->
	<section class="py-24 bg-bg-light border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-12 text-center">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[04] Integrations</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">Cleo Works Wherever Your Data Lives</h2>
			</div>

			<!-- Logo placeholders -->
			<div class="flex flex-wrap items-center justify-center gap-8 opacity-60">
				{#each ['Epic', 'Cerner', 'athenahealth', 'NextGen', 'eClinicalWorks', 'Greenway'] as logo}
					<div class="px-6 py-3 text-lg font-semibold text-slate">{logo}</div>
				{/each}
			</div>

			<div class="mt-12 text-center">
				<a href="https://calendly.com/d/cr9g-6x9-xy8/cleo-health-introduction" target="_blank" class="inline-flex items-center gap-2 text-[11px] font-bold tracking-widest text-primary-600 hover:text-primary-700 uppercase">
					Talk To Our Team About Integration
					<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
				</a>
			</div>
		</div>
	</section>

	<!-- Results -->
	<section class="py-24 border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[05] Results</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">Results You Can See And Patients Can Feel</h2>
				<p class="mt-4 text-lg text-slate">Drive meaningful, measurable results for your staff and patients.</p>
			</div>

			<div class="grid grid-cols-2 gap-6 md:grid-cols-4">
				<div class="text-center">
					<div class="text-4xl font-bold text-navy mb-2">0<span class="text-2xl text-primary-500">min</span></div>
					<div class="text-sm text-slate">Average Wait Time</div>
				</div>
				<div class="text-center">
					<div class="text-4xl font-bold text-navy mb-2">60<span class="text-2xl text-primary-500">%</span></div>
					<div class="text-sm text-slate">Less Front Desk Work</div>
				</div>
				<div class="text-center">
					<div class="text-4xl font-bold text-navy mb-2">35<span class="text-2xl text-primary-500">%</span></div>
					<div class="text-sm text-slate">Fewer No-Shows</div>
				</div>
				<div class="text-center">
					<div class="text-4xl font-bold text-navy mb-2">100<span class="text-2xl text-primary-500">%</span></div>
					<div class="text-sm text-slate">Call Answer Rate</div>
				</div>
			</div>
		</div>
	</section>

	<!-- FAQ -->
	<section class="py-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="grid grid-cols-1 gap-16 lg:grid-cols-12">
				<!-- Left Side -->
				<div class="lg:col-span-4">
					<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[06] FAQ</div>
					<h2 class="mb-6 text-4xl font-medium tracking-tight text-navy">Frequently Asked Questions</h2>
					<p class="mb-8 text-lg leading-relaxed text-slate">
						Have more questions? Our team is here to help.
					</p>
					<a href="https://calendly.com/d/cr9g-6x9-xy8/cleo-health-introduction" target="_blank" class="inline-block bg-primary-500 px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-primary-600 uppercase rounded">
						Book a Call
					</a>
				</div>

				<!-- Right Side (Accordion) -->
				<div class="lg:col-span-8">
					<div class="divide-y divide-gray-200 border-t border-b border-gray-200">
						{#each faqs as faq, i}
							<div class="group">
								<button
									class="flex w-full items-center justify-between py-6 text-left focus:outline-none"
									onclick={() => openFaq = openFaq === i ? -1 : i}
								>
									<span class="text-lg font-medium text-navy">{faq.question}</span>
									<span class="ml-4 flex h-6 w-6 items-center justify-center text-gray-400">
										{#if openFaq === i}
											<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 6L6 18M6 6l12 12"/></svg>
										{:else}
											<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
										{/if}
									</span>
								</button>
								{#if openFaq === i}
									<div class="pb-6 text-slate leading-relaxed">
										{faq.answer}
									</div>
								{/if}
							</div>
						{/each}
					</div>
				</div>
			</div>
		</div>
	</section>

	<Footer
		ctaHeadline="Power a Modern<br>Patient Experience"
		ctaSubtext="Join the next-generation of practices powered by Cleo's AI Call Center."
	/>
</main>
