<script>
	import Navbar from "$lib/components/Navbar.svelte";
	import Footer from "$lib/components/Footer.svelte";
	import { onMount } from "svelte";

	let activeTestimonial = $state(0);
	let openFaqIndex = $state(0);

	onMount(() => {
		const interval = setInterval(() => {
			activeTestimonial = (activeTestimonial + 1) % 3;
		}, 5000);

		return () => clearInterval(interval);
	});

	const clinicianFaqs = [
		{
			question: "How does Cleo handle the chaos of acute care?",
			answer: "Cleo was built specifically for the unpredictable nature of emergency and acute care settings. Our ambient AI captures conversations even when you're moving between patients, handling interruptions, or managing multiple cases simultaneously. The system understands clinical context and organizes information chronologically, even when encounters are fragmented."
		},
		{
			question: "Will Cleo work with my documentation style?",
			answer: "Yes. Cleo learns your preferences through macros and custom instructions. You can specify your preferred note structure, terminology, and level of detail. The AI adapts to read as if you wrote it yourself, maintaining your clinical voice while saving you time."
		},
		{
			question: "How accurate is the medical decision-making documentation?",
			answer: "Cleo's MDM documentation is built on clinical frameworks and continuously validated by practicing physicians. The system captures your clinical reasoning in real-time and adjusts dynamically as new information emerges during the encounter. Many clinicians report that Cleo's MDM is more thorough than what they would document manually."
		},
		{
			question: "What happens if I see multiple patients at once?",
			answer: "Cleo handles multi-patient workflows seamlessly. You can switch between patients with one click, and the system maintains separate, accurate documentation for each encounter. This is essential for ED physicians and hospitalists managing high patient volumes."
		},
		{
			question: "Is my patient data secure?",
			answer: "Absolutely. Cleo is fully HIPAA compliant and SOC 2 Type II certified. Patient data is encrypted end-to-end and never used to train AI models. We maintain BAAs with all customers and undergo regular third-party security audits."
		},
		{
			question: "How long does it take to get started?",
			answer: "Most clinicians are up and running within a single shift. Cleo integrates with your existing EHR (Epic, Cerner, Athena) and requires minimal training. Our team provides hands-on onboarding to ensure you're comfortable before going live."
		}
	];

	const features = [
		{
			title: "Macros & Custom Instructions",
			description: "Easily instruct Cleo how to create notes that read as if you wrote them"
		},
		{
			title: "Specialty-Specific",
			description: "Workflows thoughtfully designed for the needs of EM, Hospitalist, and other clinicians"
		},
		{
			title: "Medical Decision-Making",
			description: "Thorough, precise MDM that changes dynamically as additional context is brought into the note"
		},
		{
			title: "Quick Start & Multi-Patient",
			description: "One click to start documenting. Easily manage new and existing patients in a fast-paced environment"
		},
		{
			title: "Time-Stamped Re-Evaluations",
			description: "Document the entire patient visit within one note, including new conversations, re-evaluations, and consults"
		},
		{
			title: "EHR Integration",
			description: "Opportunities for EHR integration to reduce steps in your workflow"
		}
	];

	const testimonials = [
		{
			quote: "Cleo is a game-changer. I have more quality time with my patients and spend less time charting during and after my shift.",
			role: "Emergency Medicine Physician",
			location: "Colorado",
			image: "/testimonial-1.png"
		},
		{
			quote: "Cleo transforms the most miserable part of the job, documentation, into the easiest part of the job.",
			role: "Emergency Medicine Physician",
			location: "Maryland",
			image: "/testimonial-2.png"
		},
		{
			quote: "Cleo instantly changed the way I practice just like the iPhone instantly changed the way I live.",
			role: "Emergency Medicine Physician",
			location: "Idaho",
			image: "/testimonial-3.png"
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
					<span class="text-primary-500">For Clinicians</span>
					Built by Acute Care Physicians
				</div>

				<!-- Headline -->
				<h1 class="mb-6 text-7xl font-medium tracking-tight text-navy">
					Documentation that works as hard as you do.
				</h1>

				<!-- Subhead -->
				<p class="mb-10 max-w-xl text-lg leading-relaxed text-slate">
					AI-powered documentation <strong class="font-semibold text-navy">tailored to your specialty</strong>, your pace, and the real-world demands of acute care. Spend less time charting and more time with patients.
				</p>

				<!-- Buttons -->
				<div class="mb-24 flex items-center gap-4">
					<a href="#" class="bg-primary-500 px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-primary-600 uppercase rounded">
						Try Cleo Free
					</a>
					<a href="#" class="border border-gray-200 bg-white px-6 py-3 text-[11px] font-bold tracking-widest text-navy transition-colors hover:bg-gray-50 uppercase rounded">
						Request Demo
					</a>
				</div>
			</div>

			<!-- Stats bar instead of logos -->
			<div class="flex flex-wrap items-center justify-between gap-8 border-t border-gray-200 pt-8">
				<div>
					<div class="text-3xl font-medium text-navy">40%</div>
					<div class="text-xs text-slate">Less documentation time</div>
				</div>
				<div>
					<div class="text-3xl font-medium text-navy">35%</div>
					<div class="text-xs text-slate">Reduced burnout</div>
				</div>
				<div>
					<div class="text-3xl font-medium text-navy">50%</div>
					<div class="text-xs text-slate">Better patient interactions</div>
				</div>
				<div>
					<div class="text-3xl font-medium text-navy">2hrs</div>
					<div class="text-xs text-slate">Saved per shift</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Built By Clinicians Section -->
	<section class="py-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="grid grid-cols-1 gap-16 lg:grid-cols-2">
				<!-- Left Content -->
				<div>
					<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[01] Built For You</div>
					<h2 class="mb-6 text-4xl font-medium tracking-tight text-navy">
						Crafted by Acute Care Clinicians, for Acute Care Clinicians
					</h2>
					<p class="mb-8 text-lg leading-relaxed text-slate">
						Built in partnership with practicing clinicians, Cleo is made to meet the pace and complexity of <strong class="text-navy">acute care</strong>. Every feature is designed with real clinical workflows in mind.
					</p>
					<div class="border-l-2 border-primary-300 pl-6">
						<p class="text-sm leading-relaxed text-slate italic">
							"Cleo is the only AI that can take the chaos of Emergency Medicine and turn it into a clear, chronologically accurate note and summary."
						</p>
						<p class="mt-2 text-xs font-semibold text-navy">Emergency Medicine Physician, Maryland</p>
					</div>
				</div>

				<!-- Right - Visual -->
				<div class="grid grid-cols-2 gap-4">
					<!-- Phone mockup -->
					<div class="rounded-lg bg-accent-dark p-4 flex items-center justify-center">
						<div class="w-32 rounded-2xl bg-white p-2 shadow-xl">
							<div class="aspect-[9/16] rounded-lg bg-gray-100 flex items-center justify-center">
								<div class="text-center">
									<div class="mx-auto mb-2 h-8 w-8 rounded-full bg-primary-100 flex items-center justify-center">
										<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="text-primary-600"><path d="M12 2a3 3 0 0 0-3 3v7a3 3 0 0 0 6 0V5a3 3 0 0 0-3-3Z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" x2="12" y1="19" y2="22"/></svg>
									</div>
									<div class="text-[8px] font-semibold text-slate">Recording...</div>
								</div>
							</div>
						</div>
					</div>

					<!-- Web app mockup -->
					<div class="rounded-lg bg-bg-light border border-gray-200 p-4">
						<div class="rounded bg-white shadow-sm p-3 h-full">
							<div class="text-[10px] font-semibold text-navy mb-2">Patient Chart</div>
							<div class="space-y-2">
								<div class="h-2 w-full rounded bg-gray-100"></div>
								<div class="h-2 w-3/4 rounded bg-gray-100"></div>
								<div class="h-2 w-5/6 rounded bg-gray-100"></div>
								<div class="mt-3 rounded bg-primary-50 p-2">
									<div class="h-2 w-1/2 rounded bg-primary-200 mb-1"></div>
									<div class="h-2 w-2/3 rounded bg-primary-100"></div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Features Section -->
	<section class="border-t border-gray-200 bg-bg-light py-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[02] Features</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">Features clinicians love</h2>
				<p class="mt-4 max-w-2xl text-lg text-slate">
					Thoughtful features designed to accelerate documentation while keeping your voice and preferences intact.
				</p>
			</div>

			<!-- Features Grid -->
			<div class="grid grid-cols-1 gap-px overflow-hidden rounded-lg border border-gray-200 bg-gray-200 md:grid-cols-2 lg:grid-cols-3">
				{#each features as feature}
					<div class="bg-white p-8">
						<h3 class="mb-3 text-lg font-bold text-navy">{feature.title}</h3>
						<p class="text-sm leading-relaxed text-slate">{feature.description}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Impact Section -->
	<section class="py-24 border-t border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[03] The Difference</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">
					Finish charting before you finish your shift
				</h2>
			</div>

			<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
				<div class="border-l-2 border-primary-500 pl-6">
					<div class="text-4xl font-medium text-primary-500 mb-4">01</div>
					<h3 class="text-lg font-bold text-navy mb-2">More time with patients</h3>
					<p class="text-sm leading-relaxed text-slate">Be fully present at the bedside without worrying about documentation. Cleo captures the conversation so you can focus on care.</p>
				</div>
				<div class="border-l-2 border-primary-500 pl-6">
					<div class="text-4xl font-medium text-primary-500 mb-4">02</div>
					<h3 class="text-lg font-bold text-navy mb-2">Less cognitive load</h3>
					<p class="text-sm leading-relaxed text-slate">Stop juggling patient details in your head. Cleo captures everything in real-time, so nothing falls through the cracks.</p>
				</div>
				<div class="border-l-2 border-primary-500 pl-6">
					<div class="text-4xl font-medium text-primary-500 mb-4">03</div>
					<h3 class="text-lg font-bold text-navy mb-2">Go home on time</h3>
					<p class="text-sm leading-relaxed text-slate">No more late nights catching up on charts. Your documentation is done when your shift ends, not hours after.</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Testimonials Section -->
	<section class="border-t border-b border-gray-200 py-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-12 flex items-end justify-between">
				<div>
					<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[04] Testimonials</div>
					<h2 class="text-4xl font-medium tracking-tight text-navy">What clinicians are saying</h2>
				</div>
				<div class="flex gap-2">
					<button
						onclick={() => activeTestimonial = activeTestimonial === 0 ? testimonials.length - 1 : activeTestimonial - 1}
						class="flex h-10 w-10 items-center justify-center border border-gray-200 bg-white hover:bg-gray-50 transition-colors"
					>
						<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m15 18-6-6 6-6"/></svg>
					</button>
					<button
						onclick={() => activeTestimonial = activeTestimonial === testimonials.length - 1 ? 0 : activeTestimonial + 1}
						class="flex h-10 w-10 items-center justify-center border border-gray-200 bg-white hover:bg-gray-50 transition-colors"
					>
						<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m9 18 6-6-6-6"/></svg>
					</button>
				</div>
			</div>

			<!-- Featured Testimonial -->
			<div class="grid grid-cols-1 lg:grid-cols-2 gap-0 border border-gray-200 bg-white">
				<!-- Image Side -->
				<div class="relative overflow-hidden aspect-[4/3] lg:aspect-auto">
					<img
						src={testimonials[activeTestimonial].image}
						alt={testimonials[activeTestimonial].role}
						class="h-full w-full object-cover"
					/>
					<!-- Overlay gradient -->
					<div class="absolute inset-0 bg-gradient-to-t from-accent-dark/60 via-transparent to-transparent"></div>
					<!-- Location badge -->
					<div class="absolute bottom-6 left-6 flex items-center gap-2">
						<div class="h-2 w-2 rounded-full bg-primary-500"></div>
						<span class="text-[10px] font-bold tracking-widest text-white uppercase">{testimonials[activeTestimonial].location}</span>
					</div>
				</div>

				<!-- Quote Side -->
				<div class="p-8 lg:p-12 flex flex-col justify-center">
					<!-- Quote mark -->
					<div class="mb-6 text-primary-200">
						<svg width="40" height="40" viewBox="0 0 24 24" fill="currentColor">
							<path d="M11.192 15.757c0-.88-.23-1.618-.69-2.217-.326-.412-.768-.683-1.327-.812-.55-.128-1.07-.137-1.54-.028-.16-.95.1-1.956.76-3.022.66-1.065 1.515-1.867 2.558-2.403L9.373 5c-.8.396-1.56.898-2.26 1.505-.71.607-1.34 1.305-1.9 2.094s-.98 1.68-1.25 2.69-.346 2.04-.217 3.1c.168 1.4.62 2.52 1.356 3.35.735.84 1.652 1.26 2.748 1.26.965 0 1.766-.29 2.4-.878.628-.576.94-1.365.94-2.368l.002.004zm9.124 0c0-.88-.23-1.618-.69-2.217-.326-.42-.768-.695-1.327-.825-.55-.13-1.07-.14-1.54-.03-.16-.94.09-1.95.75-3.02.66-1.06 1.514-1.86 2.557-2.4L18.49 5c-.8.396-1.555.898-2.26 1.505-.708.607-1.34 1.305-1.894 2.094-.556.79-.97 1.68-1.24 2.69-.273 1-.345 2.04-.217 3.1.165 1.4.615 2.52 1.35 3.35.732.833 1.646 1.25 2.742 1.25.967 0 1.768-.29 2.402-.876.627-.576.942-1.365.942-2.368v.012z"/>
						</svg>
					</div>

					<!-- Quote text -->
					<blockquote class="mb-8">
						<p class="text-2xl lg:text-3xl font-medium leading-snug tracking-tight text-navy">
							{testimonials[activeTestimonial].quote}
						</p>
					</blockquote>

					<!-- Attribution -->
					<div class="border-t border-gray-100 pt-6">
						<div class="text-sm font-semibold text-navy">{testimonials[activeTestimonial].role}</div>
						<div class="text-xs text-slate mt-1">{testimonials[activeTestimonial].location}</div>
					</div>

					<!-- Dots indicator -->
					<div class="flex items-center gap-2 mt-8">
						{#each testimonials as _, i}
							<button
								onclick={() => activeTestimonial = i}
								class="h-1.5 rounded-full transition-all duration-300 {activeTestimonial === i ? 'w-6 bg-primary-500' : 'w-1.5 bg-gray-200 hover:bg-gray-300'}"
								aria-label="View testimonial {i + 1}"
							></button>
						{/each}
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- FAQ Section -->
	<section class="py-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="grid grid-cols-1 gap-16 lg:grid-cols-12">
				<!-- Left Side -->
				<div class="lg:col-span-4">
					<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[05] FAQ</div>
					<h2 class="mb-6 text-4xl font-medium tracking-tight text-navy">Questions from clinicians</h2>
					<p class="mb-8 text-lg leading-relaxed text-slate">
						Still have questions? Our team includes practicing physicians who understand your workflow.
					</p>
					<a href="#" class="inline-block bg-primary-500 px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-primary-600 uppercase rounded">
						Talk to a Clinician
					</a>
				</div>

				<!-- Right Side (Accordion) -->
				<div class="lg:col-span-8">
					<div class="divide-y divide-gray-200 border-t border-b border-gray-200">
						{#each clinicianFaqs as faq, i}
							<div class="group">
								<button
									class="flex w-full items-center justify-between py-6 text-left focus:outline-none"
									onclick={() => openFaqIndex = openFaqIndex === i ? -1 : i}
								>
									<span class="text-lg font-medium text-navy">{faq.question}</span>
									<span class="ml-4 flex h-6 w-6 items-center justify-center text-gray-400">
										{#if openFaqIndex === i}
											<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 6L6 18M6 6l12 12"/></svg>
										{:else}
											<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
										{/if}
									</span>
								</button>
								{#if openFaqIndex === i}
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
		ctaHeadline="Ready to transform<br>your practice?"
		ctaSubtext="Join thousands of clinicians who spend less time charting and more time with patients."
	/>
</main>
