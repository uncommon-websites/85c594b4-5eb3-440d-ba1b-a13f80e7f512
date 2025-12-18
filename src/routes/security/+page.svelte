<script>
	import Navbar from "$lib/components/Navbar.svelte";
	import Footer from "$lib/components/Footer.svelte";

	let openIndex = 0;

	const securityFeatures = [
		{
			title: "No training on your data",
			description: "Your sensitive documents and patient data are never used to train our AI models. Complete data isolation ensures your information stays yours.",
			icon: "file-lock"
		},
		{
			title: "Private data stays private",
			description: "Zero-trust architecture with role-based access controls ensures only authorized team members can access patient data. Confidentiality is our key operating principle.",
			icon: "shield-lock"
		},
		{
			title: "Up-to-date compliance",
			description: "Continuous monitoring and automated updates keep our platform aligned with evolving HIPAA, SOC2, and healthcare regulatory requirements.",
			icon: "refresh"
		},
		{
			title: "Modern security practices",
			description: "Enterprise-grade security infrastructure with automated threat detection, multi-factor authentication, and real-time monitoring protects your data.",
			icon: "server"
		},
		{
			title: "Encrypted everywhere",
			description: "End-to-end encryption protects your data in transit and at rest. AES-256 encryption ensures clinical documentation remains secure across all touchpoints.",
			icon: "lock"
		},
		{
			title: "Audited & tested",
			description: "Independent third-party security audits and penetration testing validate our defenses. Regular vulnerability assessments ensure institutional-grade protection.",
			icon: "check-badge"
		}
	];

	const faqs = [
		{
			question: "How does Cleo Health handle identity?",
			answer: "Cleo Health uses enterprise-grade identity management with multi-factor authentication (MFA), single sign-on (SSO) integration, and role-based access controls. We support SAML 2.0 and OAuth 2.0 for seamless integration with your existing identity providers."
		},
		{
			question: "How does Cleo Health protect PHI?",
			answer: "All Protected Health Information is encrypted using AES-256 encryption both at rest and in transit. We maintain strict access controls, comprehensive audit logging, and automatic data retention policies. Our infrastructure is hosted on HIPAA-compliant cloud services with BAAs in place."
		},
		{
			question: "Does Cleo Health offer security overviews?",
			answer: "Yes, we provide detailed security documentation and can arrange security review calls with our team. Visit our Trust Center for our SOC 2 Type 2 report, security policies, and compliance documentation. Enterprise customers can request additional security assessments."
		}
	];
</script>

<main class="font-sans text-gray-900 antialiased selection:bg-primary-200 selection:text-primary-900">
	<Navbar />

	<!-- Hero Section -->
	<section class="border-b border-gray-200 bg-bg-light pt-20 pb-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<div class="max-w-3xl">
				<!-- Badge -->
				<div class="mb-8 inline-flex items-center gap-2 rounded-full border border-primary-200 bg-primary-50 px-4 py-1.5 text-[10px] font-bold tracking-widest text-primary-700 uppercase">
					<span class="text-primary-500">Certified</span>
					SOC 2 Type 2 Compliant
				</div>

				<!-- Headline -->
				<h1 class="mb-6 text-6xl font-medium tracking-tight text-navy">
					Safe, Secure & Private
				</h1>

				<!-- Subhead -->
				<p class="mb-10 max-w-xl text-lg leading-relaxed text-slate">
					Cleo Health protects your patients and your data with enterprise-grade security and compliance. Our commitment to HIPAA underscores our dedication to maintaining the highest standards of privacy and trust.
				</p>

				<!-- Single CTA -->
				<a href="https://app.secureframe.com/ext/trust-center/cleo-technologies/" target="_blank" class="inline-flex items-center gap-2 bg-accent-dark px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-navy uppercase rounded">
					Visit Trust Center
					<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
				</a>
			</div>
		</div>
	</section>

	<!-- Security Features Grid -->
	<section class="py-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<!-- Section Header -->
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[01] Security Features</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">Data security is our<br>number one priority</h2>
			</div>

			<!-- Features Grid with borders -->
			<div class="grid grid-cols-1 border-t border-l border-gray-200 md:grid-cols-2 lg:grid-cols-3">
				{#each securityFeatures as feature}
					<div class="border-r border-b border-gray-200 bg-white p-8 lg:p-10">
						<!-- Icon -->
						<div class="mb-6 flex h-11 w-11 items-center justify-center rounded bg-gray-100 text-slate">
							{#if feature.icon === 'file-lock'}
								<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M15 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7Z"/><path d="M14 2v4a2 2 0 0 0 2 2h4"/><rect x="8" y="12" width="8" height="6" rx="1"/><path d="M10 12v-2a2 2 0 1 1 4 0v2"/></svg>
							{:else if feature.icon === 'shield-lock'}
								<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/><rect x="9" y="9" width="6" height="5" rx="1"/><path d="M10 9V7a2 2 0 1 1 4 0v2"/></svg>
							{:else if feature.icon === 'refresh'}
								<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 0 1 9-9 9.75 9.75 0 0 1 6.74 2.74L21 8"/><path d="M21 3v5h-5"/><path d="M21 12a9 9 0 0 1-9 9 9.75 9.75 0 0 1-6.74-2.74L3 16"/><path d="M8 16H3v5"/></svg>
							{:else if feature.icon === 'server'}
								<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="8" x="2" y="2" rx="2" ry="2"/><rect width="20" height="8" x="2" y="14" rx="2" ry="2"/><line x1="6" x2="6.01" y1="6" y2="6"/><line x1="6" x2="6.01" y1="18" y2="18"/></svg>
							{:else if feature.icon === 'lock'}
								<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect width="18" height="11" x="3" y="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/><circle cx="12" cy="16" r="1"/></svg>
							{:else if feature.icon === 'check-badge'}
								<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M3.85 8.62a4 4 0 0 1 4.78-4.77 4 4 0 0 1 6.74 0 4 4 0 0 1 4.78 4.78 4 4 0 0 1 0 6.74 4 4 0 0 1-4.77 4.78 4 4 0 0 1-6.75 0 4 4 0 0 1-4.78-4.77 4 4 0 0 1 0-6.76Z"/><path d="m9 12 2 2 4-4"/></svg>
							{/if}
						</div>

						<h3 class="mb-3 text-lg font-bold text-navy">{feature.title}</h3>
						<p class="text-sm leading-relaxed text-slate">{feature.description}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Compliance Standards Section -->
	<section class="border-t border-b border-gray-200 bg-bg-light py-24">
		<div class="mx-auto max-w-[1400px] px-6">
			<!-- Section Header -->
			<div class="mb-16">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[02] Compliance</div>
				<h2 class="text-4xl font-medium tracking-tight text-navy">Compliant with industry standards</h2>
			</div>

			<!-- Compliance Cards -->
			<div class="grid grid-cols-1 gap-px overflow-hidden rounded-lg border border-gray-200 bg-gray-200 md:grid-cols-3">
				<!-- SOC 2 -->
				<div class="flex flex-col items-center bg-white p-10 text-center">
					<div class="mb-6">
						<img src="/soc2-badge-icon.png" alt="SOC 2 Type II" class="h-20 w-auto" />
					</div>
					<h3 class="mb-2 text-lg font-bold text-navy">SOC 2 Type II</h3>
					<a href="https://app.secureframe.com/ext/trust-center/cleo-technologies/" target="_blank" class="inline-flex items-center gap-1 text-xs font-semibold text-primary-600 hover:text-primary-700">
						Details
						<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m9 18 6-6-6-6"/></svg>
					</a>
				</div>

				<!-- HIPAA -->
				<div class="flex flex-col items-center bg-white p-10 text-center">
					<div class="mb-6 flex h-20 items-center justify-center rounded-lg bg-accent-dark px-4">
						<img src="/hipaa-compliant-icon.svg" alt="HIPAA Compliant" class="h-10 w-auto" />
					</div>
					<h3 class="mb-2 text-lg font-bold text-navy">HIPAA</h3>
					<a href="#" class="inline-flex items-center gap-1 text-xs font-semibold text-primary-600 hover:text-primary-700">
						Details
						<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m9 18 6-6-6-6"/></svg>
					</a>
				</div>

				<!-- BAA -->
				<div class="flex flex-col items-center bg-white p-10 text-center">
					<div class="mb-6 flex h-20 w-20 items-center justify-center rounded-lg border-2 border-gray-200">
						<svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" class="text-slate"><path d="M15 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7Z"/><path d="M14 2v4a2 2 0 0 0 2 2h4"/><path d="m9 15 2 2 4-4"/></svg>
					</div>
					<h3 class="mb-2 text-lg font-bold text-navy">BAA Ready</h3>
					<a href="#" class="inline-flex items-center gap-1 text-xs font-semibold text-primary-600 hover:text-primary-700">
						Details
						<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m9 18 6-6-6-6"/></svg>
					</a>
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
					<div class="mb-4 text-[10px] font-bold tracking-widest text-slate uppercase">[03] FAQ</div>
					<h2 class="mb-6 text-4xl font-medium tracking-tight text-navy">Security questions, answered</h2>
					<p class="mb-8 text-lg leading-relaxed text-slate">
						Have more questions about our security practices? Our team is here to help.
					</p>
					<a href="#" class="inline-block bg-primary-500 px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-primary-600 uppercase rounded">
						Contact Security Team
					</a>
				</div>

				<!-- Right Side (Accordion) -->
				<div class="lg:col-span-8">
					<div class="divide-y divide-gray-200 border-t border-b border-gray-200">
						{#each faqs as faq, i}
							<div class="group">
								<button
									class="flex w-full items-center justify-between py-6 text-left focus:outline-none"
									onclick={() => openIndex = openIndex === i ? -1 : i}
								>
									<span class="text-lg font-medium text-navy">{faq.question}</span>
									<span class="ml-4 flex h-6 w-6 items-center justify-center text-gray-400">
										{#if openIndex === i}
											<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 6L6 18M6 6l12 12"/></svg>
										{:else}
											<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
										{/if}
									</span>
								</button>
								{#if openIndex === i}
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
		ctaHeadline="Security you can trust,<br>AI you'll love"
		ctaSubtext="See how Cleo protects your data while transforming documentation."
	/>
</main>
