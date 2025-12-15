<section class="py-24 bg-gray-50 border-t border-b border-gray-200">
	<div class="mx-auto max-w-[1400px] px-6">
		<div class="mb-12 text-center">
			<div class="mb-4 text-[10px] font-bold tracking-widest text-gray-500 uppercase">[02] AI-Powered Workflows</div>
			<h2 class="text-4xl font-medium tracking-tight text-gray-900">AI that works alongside your clinical team</h2>
		</div>

		<!-- Diagram Area -->
		<div class="relative mb-16 overflow-hidden rounded-xl bg-primary-700 p-12 min-h-[500px] flex items-center justify-center">
			<!-- Background Grid -->
			<div class="absolute inset-0 opacity-20" 
				style="background-image: linear-gradient(#ffffff 1px, transparent 1px), linear-gradient(to right, #ffffff 1px, transparent 1px); background-size: 50px 50px;">
			</div>
			
			<div class="relative z-10 w-full max-w-4xl">
				<!-- Central UI -->
				<div class="relative mx-auto max-w-2xl rounded-lg bg-white shadow-2xl overflow-hidden">
					<div class="border-b border-gray-100 bg-gray-50 px-4 py-2 flex justify-between items-center">
						<div class="text-xs font-semibold text-gray-600">Patient Follow-ups (12)</div>
					</div>
					<div class="p-4 space-y-3">
						<!-- List Items -->
						{#each ['Smith, John - ED Discharge', 'Johnson, Mary - Post-Op', 'Williams, Robert - Cardiology', 'Davis, Sarah - Observation'] as name, i}
							<div class="flex items-center justify-between p-2 hover:bg-gray-50 rounded border border-transparent hover:border-gray-100">
								<div class="flex items-center gap-3">
									<div class="h-6 w-6 rounded-full bg-primary-100 flex items-center justify-center text-primary-600 text-xs font-bold">{i + 1}</div>
									<div class="text-xs font-medium">{name}</div>
								</div>
								<div class="text-[10px] text-gray-400">Due Today</div>
								<div class="text-[10px] text-green-600 font-bold">Ready</div>
							</div>
						{/each}
					</div>
					
					<!-- Chat Overlay -->
					<div class="absolute bottom-4 left-4 right-4 rounded-lg bg-white shadow-lg border border-gray-200 p-4">
						<div class="mb-2 text-xs text-gray-500">AI-generated follow-up call script ready</div>
						<div class="flex gap-2">
							<div class="h-8 flex-1 rounded bg-gray-100 p-2 text-xs text-gray-400">Mr. Smith, this is Cleo Health calling to check on your recovery...</div>
							<button class="h-8 w-8 rounded border border-gray-200 flex items-center justify-center text-primary-600 hover:bg-primary-50">
								<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
							</button>
							<button class="h-8 w-8 rounded border border-gray-200 flex items-center justify-center text-gray-600 hover:bg-gray-50">
								<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M11 4H4a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-7"/><path d="M18.5 2.5a2.121 2.121 0 0 1 3 3L12 15l-4 1 1-4 9.5-9.5z"/></svg>
							</button>
						</div>
					</div>
				</div>

				<!-- Floating Agents -->
				<!-- Documentation Agent -->
				<div class="absolute top-10 -left-12 bg-white rounded-lg shadow-lg p-3 flex items-center gap-3 animate-bounce" style="animation-duration: 3s;">
					<div class="h-8 w-8 rounded bg-primary-100 flex items-center justify-center text-primary-600">
						<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>
					</div>
					<div>
						<div class="text-xs font-bold text-primary-600">Documentation AI</div>
						<div class="text-[10px] text-gray-500">12 notes captured today</div>
					</div>
				</div>

				<!-- Charge Capture Agent -->
				<div class="absolute -top-6 right-12 bg-white rounded-lg shadow-lg p-3 flex items-center gap-3 animate-bounce" style="animation-duration: 4s;">
					<div class="h-8 w-8 rounded bg-green-100 flex items-center justify-center text-green-600">
						<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="5" width="20" height="14" rx="2"/><line x1="2" y1="10" x2="22" y2="10"/></svg>
					</div>
					<div>
						<div class="text-xs font-bold text-green-600">Charge Capture AI</div>
						<div class="text-[10px] text-gray-500">Running 24/7 in background</div>
					</div>
				</div>

				<!-- Patient Follow-up Agent -->
				<div class="absolute bottom-20 -right-8 bg-white rounded-lg shadow-lg p-3 flex items-center gap-3 animate-bounce" style="animation-duration: 3.5s;">
					<div class="h-8 w-8 rounded bg-blue-100 flex items-center justify-center text-blue-600">
						<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
					</div>
					<div>
						<div class="text-xs font-bold text-blue-600">Follow-up AI</div>
						<div class="text-[10px] text-gray-500">12 calls scheduled</div>
					</div>
				</div>
			</div>
		</div>

		<!-- Features Grid -->
		<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
			<!-- Col 1 -->
			<div class="rounded-lg border border-gray-200 bg-white p-6">
				<div class="mb-4 inline-block rounded bg-primary-100 px-2 py-1 text-[10px] font-bold tracking-widest text-primary-700 uppercase">
					Real-Time Capture
				</div>
				<h3 class="mb-3 text-lg font-bold text-gray-900">Documentation that keeps pace</h3>
				<p class="text-sm leading-relaxed text-gray-600">
					Cleo's <strong class="text-gray-900">ambient AI</strong> captures clinical encounters in real-time, transforming chaotic ED workflows into structured, accurate documentation without disrupting patient care.
				</p>
			</div>

			<!-- Col 2 -->
			<div class="rounded-lg border border-gray-200 bg-white p-6">
				<div class="mb-4 inline-block rounded bg-green-100 px-2 py-1 text-[10px] font-bold tracking-widest text-green-700 uppercase">
					EHR Integration
				</div>
				<h3 class="mb-3 text-lg font-bold text-gray-900">Seamless EHR sync</h3>
				<p class="text-sm leading-relaxed text-gray-600">
					Integrated with <strong class="text-gray-900">Epic, Cerner, and Athena</strong>, Cleo syncs directly with your existing systems, ensuring documentation flows seamlessly into your clinical workflow.
				</p>
			</div>

			<!-- Col 3 -->
			<div class="rounded-lg border border-gray-200 bg-white p-6">
				<div class="mb-4 inline-block rounded bg-blue-100 px-2 py-1 text-[10px] font-bold tracking-widest text-blue-700 uppercase">
					Patient Continuity
				</div>
				<h3 class="mb-3 text-lg font-bold text-gray-900">Complete care cycle</h3>
				<p class="text-sm leading-relaxed text-gray-600">
					From <strong class="text-gray-900">entry to follow-up</strong>, Cleo supports patients throughout their entire acute care journey with AI-powered follow-up calls and continuity management.
				</p>
			</div>
		</div>
	</div>
</section>