<!--
@component Pricing

Please update features according to the company's product offering. Do not remove this comment.
-->
<script lang="ts">
	// Types
	type PricingTier = {
		name: string;
		monthlyPrice?: number | null;
		yearlyPrice?: number | null;
		description: string;
		features: string[];
		cta: {
			label: string;
			href: string;
		};
		highlight?: boolean;
	};

	type PricingFeature = {
		name: string;
		tiers: {
			[key: string]: boolean | string;
		};
	};

	// Components
	import Button from "$lib/components/ui/Button.svelte";
	import SectionHeader from "./SectionHeader.svelte";
	import IconCheck from "~icons/lucide/check";
	import IconX from "~icons/lucide/x";
	import NumberFlow from "@number-flow/svelte";
	import LogoScroller from "./LogoScroller.svelte";

	// Props
	const {
		title = "Precision dispatching. Real revenue growth.",
		subtitle = "Probook is the AI dispatching software built for home services companies. Assign smarter, run tighter routes, and boost close rates.",
		tierNames = ["Essentials", "Growth", "Enterprise"],
		features = [
			{
				name: "Technicians included",
				tiers: {
					Essentials: "Up to 8",
					Growth: "Up to 25",
					Enterprise: "25+"
				}
			},
			{
				name: "Dispatchers included",
				tiers: {
					Essentials: "1",
					Growth: "3",
					Enterprise: "Unlimited"
				}
			},
			{
				name: "Assignment engine",
				tiers: {
					Essentials: "Copilot",
					Growth: "Copilot + Autopilot",
					Enterprise: "Copilot + Autopilot + custom logic"
				}
			},
			{
				name: "ServiceTitan integration",
				tiers: {
					Essentials: "Live sync, 2-way booking",
					Growth: "Live sync, 2-way booking",
					Enterprise: "Advanced workflows + custom mapping"
				}
			},
			{
				name: "Dispatch analytics",
				tiers: {
					Essentials: "Technician utilization",
					Growth: "Flip rates, sales ranking, zones",
					Enterprise: "All metrics + custom reports"
				}
			},
			{
				name: "Customer service automations",
				tiers: {
					Essentials: "Proactive late alerts",
					Growth: "Late alerts + smart rescheduling",
					Enterprise: "Advanced queues, high-volume support"
				}
			},
			{
				name: "Support response time (median)",
				tiers: {
					Essentials: "8 minutes",
					Growth: "3 minutes",
					Enterprise: "Dedicated manager, SLA-backed"
				}
			},
			{
				name: "Onboarding",
				tiers: {
					Essentials: "Remote kickoff + 1:1 setup",
					Growth: "2-day in-person with founder",
					Enterprise: "Full rollout, onsite, multi-location support"
				}
			},
			{
				name: "Nexstar partnership",
				tiers: {
					Essentials: true,
					Growth: true,
					Enterprise: true
				}
			}
		],
		tiers = [
		{
			name: "Essentials",
			monthlyPrice: 399,
			yearlyPrice: 3990,
			description: "For small teams getting serious about dispatching. Cut guesswork, assign better, and run like a bigger shop—with just one dispatcher.",
			features: [
				"Copilot: AI-generated tech recommendations",
				"Up to 8 technicians, 1 dispatcher",
				"Full ServiceTitan integration (real-time synced board)",
				"Proactive late alerts",
				"Technician performance tracking",
				"Remote onboarding assistance",
				"Nexstar member integration and support",
				"Email + chat support (8-min avg response)"
			],
			cta: {
				label: "Book a demo",
				href: "/demo"
			}
		},
		{
			name: "Growth",
			monthlyPrice: 999,
			yearlyPrice: 9990,
			description: "Best for companies ready to scale fast. Grow your revenue without expanding your headcount—thanks to Autopilot and best-in-class analytics.",
			features: [
				"Copilot + Autopilot: full AI dispatch and board reshuffling",
				"Up to 25 technicians, 3 dispatchers",
				"Flip rate insights, geo-matching, and sales tracking",
				"Proactive reschedule recommendations",
				"Advanced board configuration with service zones",
				"2 full days of in-person launch with our CEO",
				"3-min average support response, 25-min resolution",
				"Official ServiceTitan and Nexstar support"
			],
			cta: {
				label: "Book a demo",
				href: "/demo"
			},
			highlight: true
		},
		{
			name: "Enterprise",
			monthlyPrice: null,
			yearlyPrice: null,
			description: "Dispatching at scale, no compromises. Full automation, advanced service logic, white-glove install, and a support team that actually answers the phone.",
			features: [
				"Copilot + Autopilot with full customization",
				"Unlimited technicians and dispatchers",
				"Custom decision logic for dispatching and rebalance triggers",
				"Multi-location and enterprise reporting",
				"Dedicated customer success manager",
				"Real-time concierge support with guaranteed SLA",
				"Custom Probook-ServiceTitan workflows included",
				"Full in-person rollout and training support"
			],
			cta: {
				label: "Contact sales",
				href: "/contact"
			}
		}
	]
	}: {
		title?: string;
		subtitle?: string;
		tiers?: PricingTier[];
		features?: PricingFeature[];
		tierNames?: string[];
		caption?: string;
	} = $props();

	// State
	let annual = $state(true);
</script>

<section class="section-py section-px container mx-auto">
	<div class="flex flex-col items-baseline justify-between lg:flex-row">
		<SectionHeader {title} {subtitle} />

		<div class="mb-8 flex justify-center">
			<div class="inline-flex items-center rounded-full bg-gray-100 p-0.5 dark:bg-gray-800">
				<Button
					variant="ghost"
					size="sm"
					class=" {!annual ? 'bg-white shadow-sm dark:bg-gray-700' : ''}"
					onclick={() => (annual = false)}
				>
					Monthly
				</Button>
				<Button
					variant="ghost"
					size="sm"
					rounded
					class={annual ? "bg-white shadow-sm dark:bg-gray-700" : ""}
					onclick={() => (annual = true)}
				>
					Annual <span class="text-primary-600 dark:text-primary-400 text-footnote">Save 20%</span>
				</Button>
			</div>
		</div>
	</div>

	<div class="bb grid gap-6 md:grid-cols-2 lg:grid-cols-3">
		{#each tiers as tier}
			<div
				class="flex flex-col rounded-xl bg-white p-6 ring ring-gray-200 transition-all duration-300 dark:bg-gray-800 dark:ring-gray-700"
				class:ring-2={tier.highlight}
				class:ring-primary={tier.highlight}
				class:dark:ring-primary-700={tier.highlight}
				class:translate-y-[-4px]={tier.highlight}
			>
				<div class="mb-8">
					<h3 class="text-title3 mb-4 dark:text-white">{tier.name}</h3>
					<div class="mt-2 flex items-baseline">
						{#if tier.monthlyPrice === null && tier.yearlyPrice === null}
							<span class="text-title2 dark:text-white">Custom</span>
						{:else}
							<NumberFlow
								class="text-title2 [&::part\(suffix\)]:text-caption dark:text-white"
								format={{
									style: "currency",
									currency: "USD",
									trailingZeroDisplay: "stripIfInteger"
								}}
								value={annual ? tier.yearlyPrice : tier.monthlyPrice}
								suffix="/month"
							/>
						{/if}
					</div>
					<p class="text-callout text-emphasis-medium mt-3 dark:text-gray-300">
						{tier.description}
					</p>
				</div>

				<div class="mb-8 flex-grow">
					<ul class="space-y-3">
						{#each tier.features as feature}
							<li class="flex items-center gap-2">
								<IconCheck class="text-primary-600 dark:text-primary-400 size-5 flex-shrink-0" />
								<span class="text-body text-emphasis-medium dark:text-gray-300">{feature}</span>
							</li>
						{/each}
					</ul>
				</div>

				<div class="mt-auto">
					<Button
						href={tier.cta.href}
						variant={tier.highlight ? "primary" : "secondary"}
						class="w-full"
					>
						{tier.cta.label}
					</Button>
				</div>
			</div>
		{/each}
	</div>
	<div class="mt-32">
		<!-- Responsive table wrapper with horizontal scroll on mobile -->
		<!-- <div class=" hidden overflow-x-auto px-4 sm:mx-0 sm:block sm:px-0">
			<table
				class="w-full min-w-full border-separate border-spacing-0 border-gray-200 text-left dark:border-gray-700"
			>
				<thead>
					<tr>
						<th
							class="sticky left-0 min-w-[120px] border-b border-gray-200 bg-white dark:border-gray-700 dark:bg-gray-900"
						>
							<span class="sr-only">Feature</span>
						</th>
						{#each tierNames as tierName}
							<th
								class="text-headline min-w-[100px] border-b border-gray-200 p-4 text-start font-normal dark:border-gray-700"
							>
								{tierName}
							</th>
						{/each}
					</tr>
				</thead>
				<tbody>
					{#each features as feature}
						<tr>
							<td class="text-caption">
								{feature.name}
							</td>
							{#each tierNames as tierName}
								<td
									class="min-w-[100px] border-b border-gray-200 p-4 text-start text-gray-600 dark:border-gray-700 dark:text-gray-300"
								>
									{#if typeof feature.tiers[tierName] === "boolean"}
										{#if feature.tiers[tierName]}
											<IconCheck
												class="text-primary-600 dark:text-primary-400 mx-auto size-5 sm:mx-0"
											/>
										{:else}
											<IconX class="mx-auto size-5 text-gray-400 sm:mx-0" />
										{/if}
									{:else}
										{feature.tiers[tierName]}
									{/if}
								</td>
							{/each}
						</tr>
					{/each}
				</tbody>
			</table>
		</div> -->

		<!-- Mobile feature comparison (alternative view for very small screens) -->
		<div>
			<!-- Universal pricing comparison for mobile -->
			<div class="overflow-x-auto">
				<table class="w-full border-collapse">
					<!-- Sticky header with tier names -->
					<thead class="border-border sticky top-0 z-10 border-b">
						<tr>
							<th class="min-w-[120px] py-3 text-left">
								<span class="sr-only">Feature</span>
							</th>
							{#each tierNames as tierName, i}
								<th class="text-caption min-w-[100px] py-3 text-left dark:text-white">
									{tierName}
								</th>
							{/each}
						</tr>
					</thead>
					<tbody class="divide-border divide-y">
						{#each features as feature}
							<tr>
								<td class="text-body py-3 pr-8 font-medium lg:pr-0 dark:text-white">
									{feature.name}
								</td>
								{#each tierNames as tierName, i}
									<td class="py-3">
										{#if typeof feature.tiers[tierName] === "boolean"}
											{#if feature.tiers[tierName]}
												<IconCheck class="text-primary-900 dark:text-primary-400 size-5" />
											{:else}
												<IconX class="size-5 text-gray-400" />
											{/if}
										{:else}
											<span class="text-callout font-medium text-gray-700 dark:text-gray-300">
												{feature.tiers[tierName]}
											</span>
										{/if}
									</td>
								{/each}
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</div>
	</div>
	<LogoScroller />
</section>

<style lang="postcss">
	@reference '../../../app.css';

	:global(number-flow-svelte)::part(suffix) {
		@apply text-sm text-gray-400 dark:text-gray-500;
	}
</style>
