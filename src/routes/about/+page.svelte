<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
  {
    title: "Built by dispatchers, for dispatchers",
    description: "Every workflow is shaped by real dispatchers and service teams. We design with your board and your stress in mind."
  },
  {
    title: "Measurable results—always",
    description: "We track everything. If it doesn’t drive sales, efficiency, or customer satisfaction, it doesn’t stay."
  },
  {
    title: "Every customer matters",
    description: "Support is direct, personal, and fast—every time. Most answers in 3 minutes or less, with 100% post-resolution satisfaction."
  },
  {
    title: "Move fast, support each other",
    description: "We build quickly, respond quickly, and always help our customers and teammates win."
  },
  {
    title: "Always personal, never generic",
    description: "From onboarding to daily use, you work with our real team—often our CEO. We care about your numbers as much as you do."
  }
];
</script>

<SecondaryHero
	title="AI dispatching for home services"
	subtitle="Smarter assignments. Better performance."
	imageSrc="/mockups/airport-screen-1748549410322.png"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"Probook was created by dispatchers who saw firsthand how stressful and unpredictable managing service calls could be. Too often, the right tech didn't get sent to the right call, and sales—and customers—suffered. We started Probook to fix this for good.",
		"We built Probook to make dispatching both easier and smarter. It uses real-time AI to recommend or automatically assign technicians, so companies boost sales, improve efficiency, and keep service levels high. Everything fits right into ServiceTitan, and our hands-on approach means owners and dispatchers get personal support from day one.",
		"Our mission is simple: help home services teams get better results with less stress. We back it up with industry partnerships, lightning-fast support, and onboarding led by our founder. Today, Probook clients see higher revenue, happier customers, and more confident dispatchers on every shift."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
  stakeholderType="team"
  title="Our founder."
  subtitle="Hands-on leadership. Real results."
  stakeholders={[
    {
      name: "George Eliadis",
      position: "Founder & CEO",
      bio: "George leads every implementation personally, working side-by-side with your team to ensure success from day one.",
      image: "/generated/image-a-headshot-of-a-smiling-business-founder.webp"
    }
  ]}
/>




<!-- CTA Section -->
<CallToAction
  title="Talk dispatch with our CEO"
  subtitle="See if Probook fits your workflow"
  description="See what AI-powered dispatch can do for your team. Book a quick call with our founder—no hard sell, just answers and a real plan. Get launched in two days with hands-on support and instant results."
  callsToAction={[
    { href: '/contact', label: 'Book a call', variant: 'primary' },
    { href: '/learn-more', label: 'Learn more', variant: 'secondary' }
  ]}
/>
