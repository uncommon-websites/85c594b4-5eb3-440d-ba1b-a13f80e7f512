<script>
	import { Play, Clock, FileCheck, Brain, Heart, Sparkles, Zap, RefreshCw, FileText, Check, X } from 'lucide-svelte';
	import Navbar from "$lib/components/Navbar.svelte";
	import Footer from "$lib/components/Footer.svelte";
	import TextEffect from "$lib/components/ui/TextEffect.svelte";
	import { onMount } from "svelte";

	let openFaq = $state(0);
	let activeFeature = $state(0);
	let activeTestimonial = $state(0);

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

	onMount(() => {
		const interval = setInterval(() => {
			activeTestimonial = (activeTestimonial + 1) % testimonials.length;
		}, 5000);

		return () => clearInterval(interval);
	});

	const benefits = [
		{
			icon: Clock,
			title: "Efficient Charting",
			description: "Charts are complete by the end of your shift, reducing the need to recall details after hours."
		},
		{
			icon: FileCheck,
			title: "Billing & Compliance",
			description: "High-quality notes, precision-trained to follow acute care coding standards and best practices."
		},
		{
			icon: Brain,
			title: "Cognitive Relief",
			description: "Feel confident no details slip, even when your focus is broken by multiple interruptions."
		},
		{
			icon: Heart,
			title: "Patient Satisfaction",
			description: "Naturally increase bedside time without adding to your workload."
		}
	];

	const features = [
		{
			number: "01",
			title: "Notes in exactly your style",
			description: "Personalized Macros & Custom Instructions so your notes read the way you would write them."
		},
		{
			number: "02",
			title: "Specialty-Specific",
			description: "Workflows thoughtfully designed for the needs of EM, Hospitalist, and other clinicians."
		},
		{
			number: "03",
			title: "EHR Integration",
			description: "Opportunities for deep EHR integration to drive leaner workflows and improved data flow."
		}
	];

	const advancedFeatures = [
		{
			number: "04",
			title: "Quick Start & Multi-Patient Management",
			description: "One click to start documenting. Seamlessly manage new and existing patients in a fast-paced environment."
		},
		{
			number: "05",
			title: "Time-Stamped Re-Evaluations",
			description: "Document the entire patient visit within one note, including new conversations, re-evaluations, and consults."
		},
		{
			number: "06",
			title: "Medical Decision-Making",
			description: "Precise, thorough MDM that changes dynamically as additional context is brought into the note."
		},
		{
			number: "07",
			title: "Supplemental Documents",
			description: "Handoff notes, progress notes, discharge summaries, and more, created in seconds and tailored to each patient's case."
		}
	];

	const comparisons = [
		{
			category: "Built for real-time, Ongoing Care",
			cleo: "Easily update notes with new information, re-evals, and consults. Cleo captures the full journey, from first contact to discharge.",
			standard: "New insights require manual edits or a new note entirely, frustrating clinicians and making it harder to reflect ED care."
		},
		{
			category: "Medical Decision-Making",
			cleo: "Granular MDM that changes dynamically as additional context is brought into the note.",
			standard: "Static and not optimized for billing, leaves clinicians to manually update or retro-fit into their notes."
		},
		{
			category: "Complexity & Chaos Tolerance",
			cleo: "Engineered for chaotic environments. Cleo captures layered histories, understands EMS context, and keeps pace with high-acuity events.",
			standard: "Designed for quiet rooms. Overlapping conversations, handoffs, and code-level chaos often lose or confuse critical context."
		},
		{
			category: "Context Awareness",
			cleo: "Instantly recognizes clinical cues, like intubation or chest tube, and inserts the correct macro without extra clicks.",
			standard: "Doesn't infer context automatically or requires manual triggers. Macros often go unused, or notes stay generic."
		}
	];

	const faqs = [
		{
			question: "How does Cleo handle multiple patients?",
			answer: "Cleo's multi-patient management lets you seamlessly switch between patients with one click. Each patient's context is preserved, so you can pick up exactly where you left off without losing any information."
		},
		{
			question: "Can I customize the note format?",
			answer: "Yes, Cleo offers personalized macros and custom instructions so your notes read exactly the way you would write them. You can set up templates for different encounter types and specialties."
		},
		{
			question: "Does Cleo work with my EHR?",
			answer: "Cleo integrates with major EHR systems including Epic, Cerner, and others. Our team can help set up deep integration to streamline your workflow and improve data flow."
		},
		{
			question: "Is my patient data secure?",
			answer: "Absolutely. Cleo is HIPAA-compliant and SOC 2 Type II certified. All data is encrypted in transit and at rest, and we never train our AI models on your patient data."
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
					Ambient Listening
				</div>

				<!-- Headline -->
				<h1 class="mb-6 text-6xl lg:text-7xl font-medium tracking-tight text-navy">
					AI-Powered Ambient Listening For Acute Care
				</h1>

				<!-- Subhead -->
				<p class="mb-10 max-w-xl text-lg leading-relaxed text-slate">
					Smart, seamless documentation that keeps pace with care delivery. <strong class="font-semibold text-navy">Save over 54 minutes per shift.</strong>
				</p>

				<!-- Buttons -->
				<div class="mb-16 flex flex-wrap items-center gap-4">
					<a href="https://app.cleohealth.io/signup" class="bg-primary-500 px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-primary-600 uppercase rounded">
						Try Cleo For Free
					</a>
					<a href="https://calendly.com/d/cr9g-6x9-xy8/cleo-health-introduction" target="_blank" class="border border-gray-200 bg-white px-6 py-3 text-[11px] font-bold tracking-widest text-navy transition-colors hover:bg-gray-50 uppercase rounded">
						Contact Us
					</a>
				</div>
			</div>

			<!-- Hero Visual - Dark Container with Grid BG -->
			<div class="relative rounded-2xl overflow-hidden bg-accent-dark shadow-2xl">
				<!-- Grid Pattern Background -->
				<div class="absolute inset-0 opacity-10" style="background-image: linear-gradient(#ffffff 1px, transparent 1px), linear-gradient(to right, #ffffff 1px, transparent 1px); background-size: 60px 60px; transform: perspective(500px) rotateX(60deg) translateY(-50px) scale(2);"></div>
				<div class="absolute inset-0 bg-gradient-to-b from-accent-dark via-transparent to-accent-dark"></div>

				<!-- Content -->
				<div class="relative p-8">
					<div class="flex gap-6" style="display: flex; flex-direction: row;">
						<!-- Left: Live Transcript Panel -->
						<div style="flex: 1; min-width: 0;" class="rounded-xl overflow-hidden bg-slate-900">
							<!-- Header -->
							<div style="display: flex; align-items: center; justify-content: space-between; padding: 16px 20px; border-bottom: 1px solid #334155;">
								<div style="display: flex; align-items: center; gap: 12px;">
									<div style="width: 32px; height: 32px; border-radius: 8px; background: #029eb5; display: flex; align-items: center; justify-content: center;">
										<svg style="width: 16px; height: 16px; color: white;" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M19 11a7 7 0 01-7 7m0 0a7 7 0 01-7-7m7 7v4m0 0H8m4 0h4m-4-8a3 3 0 01-3-3V5a3 3 0 116 0v6a3 3 0 01-3 3z"/></svg>
									</div>
									<div>
										<div style="font-size: 14px; font-weight: 600; color: white;">Live Transcript</div>
										<div style="font-size: 12px; color: #94a3b8;">Room 4 • ED Bay 2</div>
									</div>
								</div>
								<div style="display: flex; align-items: center; gap: 12px;">
									<div style="display: flex; align-items: center; gap: 2px; height: 20px;">
										{#each [4, 8, 12, 16, 12, 18, 14, 8, 10, 14, 8, 6] as height, i}
											<div style="width: 3px; border-radius: 9999px; background: #2dd4bf; height: {height}px; animation: wave 0.8s ease-in-out infinite; animation-delay: {i * 0.06}s;"></div>
										{/each}
									</div>
									<div style="display: flex; align-items: center; gap: 6px; padding: 6px 12px; border-radius: 9999px; background: rgba(16, 185, 129, 0.2);">
										<div style="width: 8px; height: 8px; border-radius: 9999px; background: #34d399;" class="animate-pulse"></div>
										<span style="font-size: 12px; font-weight: 600; color: #34d399;">03:42</span>
									</div>
								</div>
							</div>

							<!-- Transcript Content - Dark bubble style with text animations -->
							<div style="padding: 16px;">
								<div style="background: #0f172a; border-radius: 12px; padding: 16px; display: flex; flex-direction: column; gap: 12px;">
									<!-- Message 1 - Doctor -->
									<div class="transcript-msg" style="display: flex; gap: 10px; align-items: flex-start; animation: msgAppear 0.4s ease-out forwards; animation-delay: 0s;">
										<div style="flex-shrink: 0; width: 28px; height: 28px; border-radius: 8px; background: #029eb5; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 700; color: white;">DR</div>
										<div style="flex: 1;">
											<div style="background: #1e293b; border-radius: 12px; padding: 10px 14px;">
												<p style="font-size: 13px; color: #e2e8f0; line-height: 1.5; margin: 0;">
													<TextEffect preset="blur" per="word" delay={0.2} staggerDelay={0.04} text="Good morning Mr. Smith. I see you're here for chest pain. Can you tell me when it started?" />
												</p>
											</div>
											<span style="font-size: 10px; color: #64748b; margin-top: 4px; display: block;">00:12</span>
										</div>
									</div>

									<!-- Message 2 - Patient -->
									<div class="transcript-msg" style="display: flex; gap: 10px; align-items: flex-start; animation: msgAppear 0.4s ease-out forwards; animation-delay: 1.5s; opacity: 0;">
										<div style="flex-shrink: 0; width: 28px; height: 28px; border-radius: 8px; background: #0c2c52; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 700; color: white;">PT</div>
										<div style="flex: 1;">
											<div style="background: #1e293b; border-radius: 12px; padding: 10px 14px;">
												<p style="font-size: 13px; color: #e2e8f0; line-height: 1.5; margin: 0;">
													<TextEffect preset="blur" per="word" delay={1.7} staggerDelay={0.04} text="It started about two hours ago. I was just sitting watching TV and felt this pressure in my chest." />
												</p>
											</div>
											<span style="font-size: 10px; color: #64748b; margin-top: 4px; display: block;">00:24</span>
										</div>
									</div>

									<!-- Message 3 - Doctor -->
									<div class="transcript-msg" style="display: flex; gap: 10px; align-items: flex-start; animation: msgAppear 0.4s ease-out forwards; animation-delay: 3s; opacity: 0;">
										<div style="flex-shrink: 0; width: 28px; height: 28px; border-radius: 8px; background: #029eb5; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 700; color: white;">DR</div>
										<div style="flex: 1;">
											<div style="background: #1e293b; border-radius: 12px; padding: 10px 14px;">
												<p style="font-size: 13px; color: #e2e8f0; line-height: 1.5; margin: 0;">
													<TextEffect preset="blur" per="word" delay={3.2} staggerDelay={0.05} text="Does the pain radiate anywhere? Like your arm, jaw, or back?" />
												</p>
											</div>
											<span style="font-size: 10px; color: #64748b; margin-top: 4px; display: block;">00:45</span>
										</div>
									</div>

									<!-- Message 4 - Patient (active) -->
									<div class="transcript-msg" style="display: flex; gap: 10px; align-items: flex-start; animation: msgAppear 0.4s ease-out forwards; animation-delay: 4.5s; opacity: 0;">
										<div style="flex-shrink: 0; width: 28px; height: 28px; border-radius: 8px; background: #0c2c52; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 700; color: white;">PT</div>
										<div style="flex: 1;">
											<div style="background: #1e293b; border-radius: 12px; padding: 10px 14px; border: 1px solid #029eb5;">
												<p style="font-size: 13px; color: #ffffff; line-height: 1.5; margin: 0;">
													<TextEffect preset="blur" per="word" delay={4.7} staggerDelay={0.06} text="Yes, down my left arm. And I've been sweating" /><span style="display: inline-block; width: 2px; height: 14px; background: #2dd4bf; margin-left: 4px; vertical-align: middle;" class="animate-pulse"></span>
												</p>
											</div>
											<span style="font-size: 10px; color: #2dd4bf; margin-top: 4px; display: block;">Speaking...</span>
										</div>
									</div>
								</div>
							</div>
						</div>

						<!-- Right: AI-Generated Note Panel -->
						<div style="flex: 1; min-width: 0;" class="rounded-xl overflow-hidden bg-slate-900">
							<!-- Header -->
							<div style="display: flex; align-items: center; justify-content: space-between; padding: 16px 20px; border-bottom: 1px solid #334155;">
								<div style="display: flex; align-items: center; gap: 12px;">
									<div style="width: 32px; height: 32px; border-radius: 8px; background: #029eb5; display: flex; align-items: center; justify-content: center;">
										<Sparkles style="width: 16px; height: 16px; color: white;" />
									</div>
									<div>
										<div style="font-size: 14px; font-weight: 600; color: white;">AI-Generated Note</div>
										<div style="font-size: 12px; color: #94a3b8;">Auto-updating in real-time</div>
									</div>
								</div>
								<div style="display: flex; align-items: center; gap: 6px; padding: 6px 12px; border-radius: 9999px; background: rgba(245, 158, 11, 0.2);">
									<div style="width: 8px; height: 8px; border-radius: 9999px; background: #f59e0b;"></div>
									<span style="font-size: 11px; font-weight: 600; color: #fbbf24;">HIGH PRIORITY</span>
								</div>
							</div>

							<!-- Note Content - White card inside dark container -->
							<div style="padding: 16px;">
								<div style="background: white; border-radius: 12px; padding: 20px;">
									<!-- Patient Info -->
									<div style="margin-bottom: 20px; padding-bottom: 16px; border-bottom: 1px solid #f1f5f9;">
										<div style="font-size: 20px; font-weight: 700; color: #0f172a;">Smith, John</div>
										<div style="font-size: 13px; color: #64748b; margin-top: 4px;">62 y/o Male • MRN: 4782901 • DOB: 03/15/1962</div>
									</div>

									<!-- Chief Complaint -->
									<div style="margin-bottom: 20px;">
										<div style="font-size: 11px; font-weight: 700; color: #94a3b8; letter-spacing: 0.05em; margin-bottom: 8px;">CHIEF COMPLAINT</div>
										<p style="font-size: 14px; color: #1e293b; line-height: 1.6;">Chest pain with radiation to left arm, onset 2 hours PTA. Associated diaphoresis and dyspnea.</p>
									</div>

									<!-- Vitals - Using inline flex -->
									<div style="margin-bottom: 20px; display: flex; padding: 16px; border-radius: 12px; background: #f8fafc; border: 1px solid #f1f5f9;">
										<div style="flex: 1; text-align: center;">
											<div style="font-size: 11px; color: #94a3b8; font-weight: 500; margin-bottom: 4px;">BP</div>
											<div style="font-size: 16px; font-weight: 700; color: #0f172a;">145/92</div>
										</div>
										<div style="flex: 1; text-align: center; border-left: 1px solid #e2e8f0;">
											<div style="font-size: 11px; color: #94a3b8; font-weight: 500; margin-bottom: 4px;">HR</div>
											<div style="font-size: 16px; font-weight: 700; color: #0f172a;">98</div>
										</div>
										<div style="flex: 1; text-align: center; border-left: 1px solid #e2e8f0;">
											<div style="font-size: 11px; color: #94a3b8; font-weight: 500; margin-bottom: 4px;">SpO2</div>
											<div style="font-size: 16px; font-weight: 700; color: #0f172a;">96%</div>
										</div>
										<div style="flex: 1; text-align: center; border-left: 1px solid #e2e8f0;">
											<div style="font-size: 11px; color: #94a3b8; font-weight: 500; margin-bottom: 4px;">Temp</div>
											<div style="font-size: 16px; font-weight: 700; color: #0f172a;">98.6°F</div>
										</div>
									</div>

									<!-- HPI -->
									<div style="margin-bottom: 20px;">
										<div style="font-size: 11px; font-weight: 700; color: #94a3b8; letter-spacing: 0.05em; margin-bottom: 8px;">HPI</div>
										<p style="font-size: 14px; color: #1e293b; line-height: 1.6;">Patient is a 62-year-old male with PMH of HTN, HLD who presents with acute onset substernal chest pressure while at rest. Pain is described as 7/10, pressure-like, radiating to left arm. <span style="background: #ccfbf1; color: #0f766e; padding: 2px 4px; border-radius: 4px; font-weight: 500;">Associated symptoms include diaphoresis and mild dyspnea.</span> Denies nausea, vomiting, or syncope.</p>
									</div>

									<!-- ICD Codes -->
									<div style="display: flex; align-items: center; gap: 12px;">
										<div style="font-size: 11px; font-weight: 700; color: #94a3b8; letter-spacing: 0.05em;">SUGGESTED ICD-10</div>
										<div style="display: flex; gap: 8px;">
											<span style="padding: 6px 10px; border-radius: 8px; background: #ccfbf1; font-size: 12px; font-weight: 700; color: #0f766e;">I21.9</span>
											<span style="padding: 6px 10px; border-radius: 8px; background: #ccfbf1; font-size: 12px; font-weight: 700; color: #0f766e;">R07.9</span>
											<span style="padding: 6px 10px; border-radius: 8px; background: #f1f5f9; font-size: 12px; font-weight: 700; color: #64748b;">I10</span>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

			<style>
				@keyframes wave {
					0%, 100% { transform: scaleY(1); }
					50% { transform: scaleY(0.4); }
				}
				@keyframes msgAppear {
					0% {
						opacity: 0;
						transform: translateY(10px);
					}
					100% {
						opacity: 1;
						transform: translateY(0);
					}
				}
			</style>
		</div>
	</section>

	<!-- Testimonials Section -->
	<section class="border-t border-b border-gray-200 py-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-12 flex items-end justify-between">
				<div>
					<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[01] Testimonials</div>
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

	<!-- Benefits Section -->
	<section class="py-24 border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[01] Benefits</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy mb-4">Smarter Documentation, Better Outcomes</h2>
				<p class="text-lg text-slate max-w-2xl">
					Reduce documentation burden with AI that produces clinically accurate, high-quality notes in seconds.
				</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
				{#each benefits as benefit}
					<div class="group">
						<div class="mb-4 h-12 w-12 rounded-lg bg-primary-50 flex items-center justify-center text-primary-600 group-hover:bg-primary-500 group-hover:text-white transition-colors">
							<benefit.icon class="w-6 h-6" />
						</div>
						<h3 class="text-lg font-bold text-navy mb-2">{benefit.title}</h3>
						<p class="text-sm leading-relaxed text-slate">{benefit.description}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Features Section -->
	<section class="py-24 bg-bg-light border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[02] Features</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy mb-4">Designed For The Way You Work</h2>
				<p class="text-lg text-slate max-w-2xl">
					Reduce documentation burden with AI that produces clinically accurate, high-quality notes in seconds.
				</p>
			</div>

			<div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
				<!-- Feature List -->
				<div class="space-y-0">
					{#each features as feature, i}
						<button
							onclick={() => activeFeature = i}
							style="cursor: pointer;"
							class="w-full text-left p-6 border-l-2 transition-all {activeFeature === i ? 'border-primary-500 bg-white' : 'border-gray-200 hover:border-gray-300'}"
						>
							<div class="flex items-start gap-4">
								<span class="text-2xl font-bold {activeFeature === i ? 'text-primary-500' : 'text-gray-300'}">{feature.number}</span>
								<div>
									<h3 class="text-lg font-bold text-navy mb-1">{feature.title}</h3>
									<p class="text-sm text-slate">{feature.description}</p>
								</div>
							</div>
						</button>
					{/each}
				</div>

				<!-- Feature Visual -->
				<div class="relative rounded-2xl overflow-hidden bg-primary-500 p-8">
					<div class="absolute inset-0 opacity-10" style="background-image: radial-gradient(circle at 2px 2px, white 1px, transparent 0); background-size: 24px 24px;"></div>
					<div class="relative rounded-lg bg-white shadow-xl p-6">
						{#if activeFeature === 0}
							<div class="space-y-4">
								<div class="text-sm font-bold text-gray-900">Custom Macros</div>
								<div class="space-y-2">
									<div class="flex items-center gap-2 p-2 rounded bg-primary-50 text-sm">
										<Zap class="w-4 h-4 text-primary-500" />
										<span class="text-gray-700">/chest-pain - Chest pain workup template</span>
									</div>
									<div class="flex items-center gap-2 p-2 rounded bg-gray-50 text-sm">
										<Zap class="w-4 h-4 text-gray-400" />
										<span class="text-gray-700">/trauma - Trauma assessment</span>
									</div>
									<div class="flex items-center gap-2 p-2 rounded bg-gray-50 text-sm">
										<Zap class="w-4 h-4 text-gray-400" />
										<span class="text-gray-700">/discharge - Discharge summary</span>
									</div>
								</div>
							</div>
						{:else if activeFeature === 1}
							<div class="space-y-4">
								<div class="text-sm font-bold text-gray-900">Select Your Specialty</div>
								<div class="grid grid-cols-2 gap-2">
									<div class="p-3 rounded bg-primary-50 border-2 border-primary-500 text-sm font-medium text-primary-700">Emergency Medicine</div>
									<div class="p-3 rounded bg-gray-50 text-sm text-gray-600">Hospitalist</div>
									<div class="p-3 rounded bg-gray-50 text-sm text-gray-600">Critical Care</div>
									<div class="p-3 rounded bg-gray-50 text-sm text-gray-600">Urgent Care</div>
								</div>
							</div>
						{:else}
							<div class="space-y-4">
								<div class="text-sm font-bold text-gray-900">EHR Integration Status</div>
								<div class="space-y-3">
									<div class="flex items-center justify-between p-3 rounded bg-green-50">
										<span class="text-sm text-gray-700">Epic</span>
										<span class="text-xs font-medium text-green-600">Connected</span>
									</div>
									<div class="flex items-center justify-between p-3 rounded bg-gray-50">
										<span class="text-sm text-gray-700">Cerner</span>
										<span class="text-xs font-medium text-gray-500">Available</span>
									</div>
									<div class="flex items-center justify-between p-3 rounded bg-gray-50">
										<span class="text-sm text-gray-700">Meditech</span>
										<span class="text-xs font-medium text-gray-500">Available</span>
									</div>
								</div>
							</div>
						{/if}
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Workflow Features - Clean Grid -->
	<section class="py-24 border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[03] Workflow</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">Built For Acute Care Workflows</h2>
			</div>

			<!-- Bento Grid -->
			<div style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 24px;">
				<!-- Feature 01 - Quick Start -->
				<div style="grid-column: span 1; background: #f9fafb; border-radius: 16px; padding: 40px; display: flex; flex-direction: column;">
					<div style="display: flex; align-items: center; gap: 16px; margin-bottom: 20px;">
						<div style="width: 48px; height: 48px; border-radius: 12px; background: #029eb5; display: flex; align-items: center; justify-content: center;">
							<Zap style="width: 24px; height: 24px; color: white;" />
						</div>
						<span style="font-size: 48px; font-weight: 700; color: #cbd5e1;">01</span>
					</div>
					<h3 style="font-size: 22px; font-weight: 700; color: #0c2c52; margin-bottom: 12px;">Quick Start & Multi-Patient</h3>
					<p style="font-size: 15px; color: #4a5a70; line-height: 1.7; margin-bottom: 24px;">One click to start documenting. Seamlessly manage new and existing patients in a fast-paced environment.</p>
					<!-- Visual: Patient Census -->
					<div style="margin-top: auto; background: white; border-radius: 12px; border: 1px solid #e5e7eb; overflow: hidden;">
						<div style="padding: 12px 16px; border-bottom: 1px solid #f3f4f6; display: flex; justify-content: space-between; align-items: center;">
							<span style="font-size: 12px; font-weight: 600; color: #0c2c52;">Patient Census</span>
							<div style="background: #029eb5; color: white; font-size: 11px; font-weight: 600; padding: 4px 10px; border-radius: 6px; cursor: pointer;">+ New Patient</div>
						</div>
						<div style="padding: 8px;">
							<div style="display: flex; align-items: center; gap: 12px; padding: 10px 12px; background: #f0fdfa; border-radius: 8px; margin-bottom: 6px;">
								<div style="width: 32px; height: 32px; border-radius: 8px; background: #029eb5; display: flex; align-items: center; justify-content: center; font-size: 11px; font-weight: 700; color: white;">R4</div>
								<div style="flex: 1;">
									<div style="font-size: 13px; font-weight: 600; color: #0f172a;">Smith, John</div>
									<div style="font-size: 11px; color: #64748b;">Chest pain • 62M</div>
								</div>
								<div style="display: flex; align-items: center; gap: 4px;">
									<div style="width: 6px; height: 6px; border-radius: 9999px; background: #10b981; animation: pulse 2s infinite;"></div>
									<span style="font-size: 10px; font-weight: 600; color: #10b981;">LIVE</span>
								</div>
							</div>
							<div style="display: flex; align-items: center; gap: 12px; padding: 10px 12px; border-radius: 8px;">
								<div style="width: 32px; height: 32px; border-radius: 8px; background: #e5e7eb; display: flex; align-items: center; justify-content: center; font-size: 11px; font-weight: 700; color: #64748b;">R7</div>
								<div style="flex: 1;">
									<div style="font-size: 13px; font-weight: 600; color: #0f172a;">Johnson, Mary</div>
									<div style="font-size: 11px; color: #64748b;">Abdominal pain • 45F</div>
								</div>
								<span style="font-size: 10px; font-weight: 500; color: #64748b;">Ready</span>
							</div>
						</div>
					</div>
				</div>

				<!-- Feature 02 - Time-Stamped -->
				<div style="grid-column: span 1; background: #f9fafb; border-radius: 16px; padding: 40px; display: flex; flex-direction: column;">
					<div style="display: flex; align-items: center; gap: 16px; margin-bottom: 20px;">
						<div style="width: 48px; height: 48px; border-radius: 12px; background: #029eb5; display: flex; align-items: center; justify-content: center;">
							<Clock style="width: 24px; height: 24px; color: white;" />
						</div>
						<span style="font-size: 48px; font-weight: 700; color: #cbd5e1;">02</span>
					</div>
					<h3 style="font-size: 22px; font-weight: 700; color: #0c2c52; margin-bottom: 12px;">Time-Stamped Re-Evaluations</h3>
					<p style="font-size: 15px; color: #4a5a70; line-height: 1.7; margin-bottom: 24px;">Document the entire patient visit within one note, including new conversations and consults.</p>
					<!-- Visual: Timeline -->
					<div style="margin-top: auto; background: white; border-radius: 12px; border: 1px solid #e5e7eb; padding: 16px;">
						<div style="display: flex; flex-direction: column; gap: 0;">
							<div style="display: flex; gap: 12px; padding-bottom: 12px; border-left: 2px solid #029eb5; margin-left: 5px; padding-left: 16px; position: relative;">
								<div style="position: absolute; left: -5px; top: 0; width: 10px; height: 10px; border-radius: 9999px; background: #029eb5;"></div>
								<div>
									<div style="font-size: 10px; font-weight: 600; color: #029eb5; margin-bottom: 2px;">14:32 - INITIAL</div>
									<div style="font-size: 12px; color: #0f172a;">Chief complaint, vitals, history</div>
								</div>
							</div>
							<div style="display: flex; gap: 12px; padding-bottom: 12px; border-left: 2px solid #029eb5; margin-left: 5px; padding-left: 16px; position: relative;">
								<div style="position: absolute; left: -5px; top: 0; width: 10px; height: 10px; border-radius: 9999px; background: #029eb5;"></div>
								<div>
									<div style="font-size: 10px; font-weight: 600; color: #029eb5; margin-bottom: 2px;">15:10 - UPDATE</div>
									<div style="font-size: 12px; color: #0f172a;">Labs reviewed, EKG findings</div>
								</div>
							</div>
							<div style="display: flex; gap: 12px; margin-left: 5px; padding-left: 16px; position: relative;">
								<div style="position: absolute; left: -5px; top: 0; width: 10px; height: 10px; border-radius: 9999px; background: #10b981; border: 2px solid #d1fae5;"></div>
								<div>
									<div style="font-size: 10px; font-weight: 600; color: #10b981; margin-bottom: 2px;">15:47 - NOW</div>
									<div style="font-size: 12px; color: #0f172a; font-weight: 500;">Cardiology consult added</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Feature 03 - MDM -->
				<div style="grid-column: span 1; background: #f9fafb; border-radius: 16px; padding: 40px; display: flex; flex-direction: column;">
					<div style="display: flex; align-items: center; gap: 16px; margin-bottom: 20px;">
						<div style="width: 48px; height: 48px; border-radius: 12px; background: #029eb5; display: flex; align-items: center; justify-content: center;">
							<Brain style="width: 24px; height: 24px; color: white;" />
						</div>
						<span style="font-size: 48px; font-weight: 700; color: #cbd5e1;">03</span>
					</div>
					<h3 style="font-size: 22px; font-weight: 700; color: #0c2c52; margin-bottom: 12px;">Medical Decision-Making</h3>
					<p style="font-size: 15px; color: #4a5a70; line-height: 1.7; margin-bottom: 24px;">Precise, thorough MDM that changes dynamically as additional context is brought into the note.</p>
					<!-- Visual: MDM Breakdown -->
					<div style="margin-top: auto; background: white; border-radius: 12px; border: 1px solid #e5e7eb; padding: 16px;">
						<div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px;">
							<span style="font-size: 12px; font-weight: 600; color: #0c2c52;">MDM Level</span>
							<span style="font-size: 11px; font-weight: 700; color: white; background: #029eb5; padding: 4px 12px; border-radius: 6px;">HIGH COMPLEXITY</span>
						</div>
						<div style="display: flex; flex-direction: column; gap: 10px;">
							<div style="display: flex; justify-content: space-between; align-items: center;">
								<span style="font-size: 12px; color: #64748b;">Problems</span>
								<div style="display: flex; gap: 3px;">
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
								</div>
							</div>
							<div style="display: flex; justify-content: space-between; align-items: center;">
								<span style="font-size: 12px; color: #64748b;">Data</span>
								<div style="display: flex; gap: 3px;">
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #e5e7eb; border-radius: 2px;"></div>
								</div>
							</div>
							<div style="display: flex; justify-content: space-between; align-items: center;">
								<span style="font-size: 12px; color: #64748b;">Risk</span>
								<div style="display: flex; gap: 3px;">
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
									<div style="width: 24px; height: 6px; background: #029eb5; border-radius: 2px;"></div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Feature 04 - Supplemental -->
				<div style="grid-column: span 1; background: #f9fafb; border-radius: 16px; padding: 40px; display: flex; flex-direction: column;">
					<div style="display: flex; align-items: center; gap: 16px; margin-bottom: 20px;">
						<div style="width: 48px; height: 48px; border-radius: 12px; background: #029eb5; display: flex; align-items: center; justify-content: center;">
							<FileText style="width: 24px; height: 24px; color: white;" />
						</div>
						<span style="font-size: 48px; font-weight: 700; color: #cbd5e1;">04</span>
					</div>
					<h3 style="font-size: 22px; font-weight: 700; color: #0c2c52; margin-bottom: 12px;">Supplemental Documents</h3>
					<p style="font-size: 15px; color: #4a5a70; line-height: 1.7; margin-bottom: 24px;">Handoff notes, progress notes, discharge summaries created in seconds.</p>
					<!-- Visual: Document Generator -->
					<div style="margin-top: auto; background: white; border-radius: 12px; border: 1px solid #e5e7eb; padding: 16px;">
						<div style="font-size: 12px; font-weight: 600; color: #0c2c52; margin-bottom: 12px;">Quick Generate</div>
						<div style="display: flex; flex-direction: column; gap: 8px;">
							<div style="display: flex; align-items: center; justify-content: space-between; padding: 10px 12px; background: #f0fdfa; border: 1px solid #99f6e4; border-radius: 8px;">
								<div style="display: flex; align-items: center; gap: 10px;">
									<FileText style="width: 16px; height: 16px; color: #029eb5;" />
									<span style="font-size: 13px; font-weight: 500; color: #0f172a;">Discharge Summary</span>
								</div>
								<Check style="width: 16px; height: 16px; color: #10b981;" />
							</div>
							<div style="display: flex; align-items: center; justify-content: space-between; padding: 10px 12px; background: #f9fafb; border-radius: 8px;">
								<div style="display: flex; align-items: center; gap: 10px;">
									<FileText style="width: 16px; height: 16px; color: #94a3b8;" />
									<span style="font-size: 13px; font-weight: 500; color: #0f172a;">Handoff Note</span>
								</div>
								<span style="font-size: 11px; color: #029eb5; font-weight: 500;">Generate →</span>
							</div>
							<div style="display: flex; align-items: center; justify-content: space-between; padding: 10px 12px; background: #f9fafb; border-radius: 8px;">
								<div style="display: flex; align-items: center; gap: 10px;">
									<FileText style="width: 16px; height: 16px; color: #94a3b8;" />
									<span style="font-size: 13px; font-weight: 500; color: #0f172a;">Referral Letter</span>
								</div>
								<span style="font-size: 11px; color: #029eb5; font-weight: 500;">Generate →</span>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Comparison Section -->
	<section class="py-24 border-b border-gray-200">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[04] Comparison</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy mb-4">More Than Just Configurable,<br>Built For Acute Care</h2>
				<p class="text-lg text-slate max-w-2xl">
					With Cleo, acute care isn't just a use case, it is the use case. Engineered for the hospital environment.
				</p>
			</div>

			<!-- Clean Comparison Table -->
			<div style="border: 1px solid #e5e7eb; border-radius: 12px; overflow: hidden;">
				<!-- Header Row -->
				<div style="display: grid; grid-template-columns: 280px 1fr 1fr; border-bottom: 1px solid #e5e7eb;">
					<div style="padding: 24px 32px; background: #f9fafb;"></div>
					<div style="padding: 24px 32px; background: #029eb5; border-left: 1px solid #028a9e;">
						<div style="font-size: 11px; font-weight: 700; letter-spacing: 0.1em; color: white; text-transform: uppercase;">Cleo Health</div>
					</div>
					<div style="padding: 24px 32px; background: #f3f4f6; border-left: 1px solid #e5e7eb;">
						<div style="font-size: 11px; font-weight: 700; letter-spacing: 0.1em; color: #4a5a70; text-transform: uppercase;">Others</div>
					</div>
				</div>

				<!-- Comparison Rows -->
				{#each comparisons as comparison, i}
					<div style="display: grid; grid-template-columns: 280px 1fr 1fr; border-bottom: 1px solid #f3f4f6;">
						<div style="padding: 28px 32px; background: #f9fafb; border-right: 1px solid #f3f4f6;">
							<div style="font-size: 15px; font-weight: 700; color: #0c2c52;">{comparison.category}</div>
						</div>
						<div style="padding: 28px 32px; border-right: 1px solid #f3f4f6;">
							<div style="display: flex; align-items: flex-start; gap: 14px;">
								<div style="flex-shrink: 0; width: 24px; height: 24px; border-radius: 9999px; background: #e0f7fa; display: flex; align-items: center; justify-content: center; margin-top: 1px;">
									<Check style="width: 14px; height: 14px; color: #029eb5;" />
								</div>
								<p style="font-size: 15px; color: #374151; line-height: 1.7; margin: 0;">{comparison.cleo}</p>
							</div>
						</div>
						<div style="padding: 28px 32px; background: #fafafa;">
							<div style="display: flex; align-items: flex-start; gap: 14px;">
								<div style="flex-shrink: 0; width: 24px; height: 24px; border-radius: 9999px; background: #e5e7eb; display: flex; align-items: center; justify-content: center; margin-top: 1px;">
									<X style="width: 14px; height: 14px; color: #9ca3af;" />
								</div>
								<p style="font-size: 15px; color: #6b7280; line-height: 1.7; margin: 0;">{comparison.standard}</p>
							</div>
						</div>
					</div>
				{/each}
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
									class="flex w-full items-center justify-between py-6 text-left"
									style="cursor: pointer;"
									onclick={() => openFaq = openFaq === i ? -1 : i}
								>
									<span class="text-lg font-medium text-navy">{faq.question}</span>
									<span class="ml-4 flex h-6 w-6 items-center justify-center text-gray-400">
										{#if openFaq === i}
											<X class="w-4 h-4" />
										{:else}
											<span class="text-xl">+</span>
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
		ctaHeadline="Discover Smarter Documentation.<br>Explore Cleo Today."
		ctaSubtext="Join clinicians saving 54+ minutes per shift with AI-powered ambient documentation."
	/>
</main>
