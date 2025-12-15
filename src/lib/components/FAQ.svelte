<script>
	let openIndex = 0;
	const faqs = [
		{
			question: "Who can use Cleo Health?",
			answer: "Cleo Health is built for acute care clinicians and hospital administrators. If you're struggling with documentation burden in emergency departments or inpatient settings, Cleo is designed for you. We work with health systems of all sizes — from community hospitals to large academic medical centers."
		},
		{
			question: "How does Cleo integrate with our existing EHR?",
			answer: "Cleo seamlessly integrates with major EHR systems including Epic, Cerner, and Athena. Our implementation team works closely with your IT department to ensure smooth integration without disrupting clinical workflows."
		},
		{
			question: "Is Cleo HIPAA compliant?",
			answer: "Absolutely. Cleo Health is fully HIPAA compliant and follows all healthcare data security standards. Patient privacy and data security are our top priorities."
		},
		{
			question: "How long does it take to implement Cleo Health?",
			answer: "Most implementations take 2-4 weeks depending on your EHR system and organizational needs. Our team handles the technical setup while providing comprehensive training for your clinical staff."
		},
		{
			question: "Does Cleo work in real-time during patient encounters?",
			answer: "Yes! Cleo's ambient AI captures clinical encounters in real-time, transforming conversations into structured documentation without interrupting patient care."
		},
		{
			question: "What kind of ROI can we expect from Cleo Health?",
			answer: "Our customers typically see 30-40% reduction in documentation time, significant improvements in charge capture, and enhanced clinical documentation integrity. Many health systems report ROI within the first 6 months."
		}
	];
</script>

<section class="py-24">
	<div class="mx-auto max-w-[1400px] px-6">
		<div class="grid grid-cols-1 gap-16 lg:grid-cols-12">
			<!-- Left Side -->
			<div class="lg:col-span-4">
				<div class="mb-4 text-[10px] font-bold tracking-widest text-gray-500 uppercase">[06] FAQ</div>
				<h2 class="mb-6 text-4xl font-medium tracking-tight text-gray-900">Your questions, answered</h2>
				<p class="mb-8 text-lg leading-relaxed text-gray-600">
					We're here to help. Reach out to our team for guidance on how to integrate Cleo Health into your acute care workflow.
				</p>
				<a href="#" class="inline-block bg-gray-900 px-6 py-3 text-[11px] font-bold tracking-widest text-white transition-colors hover:bg-gray-800 uppercase">
					Request Demo
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
								<span class="text-lg font-medium text-gray-900">{faq.question}</span>
								<span class="ml-4 flex h-6 w-6 items-center justify-center text-gray-400">
									{#if openIndex === i}
										<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 6L6 18M6 6l12 12"/></svg>
									{:else}
										<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
									{/if}
								</span>
							</button>
							{#if openIndex === i}
								<div class="pb-6 text-gray-600 leading-relaxed">
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