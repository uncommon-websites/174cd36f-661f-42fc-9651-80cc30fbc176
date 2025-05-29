<script lang="ts">
	// Types
	import type { PageProps } from "./$types";

	// Components
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import Pricing from "$lib/components/layout/Pricing.svelte";

	// Props
	const { data }: PageProps = $props();
</script>

<Pricing />

<Testimonials
  testimonials={[
    {
      name: "Isabella Martinez",
      position: "Operations Manager",
      company: "Blue Skies HVAC",
      quote:
        "Probook paid for itself in the first month. Scheduling is easier, our close rate is up, and dispatchers feel confident taking on more techs.",
      image: "/generated/image-a-professional-headshot-of-a-hispanic-wo.webp"
    },
    {
      name: "Darius Carter",
      position: "Dispatch Lead",
      company: "Precision Plumbing Group",
      quote:
        "We saw a clear jump in sold work—Probook's AI matches techs to the right jobs. Rollout was fast and even the least tech-savvy dispatcher picked it up fast.",
      image: "/generated/image-a-professional-headshot-of-a-black-man-i.webp"
    },
    {
      name: "Lina Chen",
      position: "Service Director",
      company: "Family First Electrical",
      quote:
        "Probook made us more profitable right away. The onboarding was personal, and their support is super fast—I've never waited more than five minutes for help.",
      image: "/generated/image-a-professional-headshot-of-an-asian-woma.webp"
    }
  ]}
/>


<CallToAction
  title="Smarter dispatching. Higher revenue. Happier teams."
  subtitle="AI dispatching software built by dispatchers"
  description="Probook helps HVAC, plumbing, and electrical companies assign the right tech to the right call—automatically. Boost flip rate, support your team, and grow your business without adding headcount. Two-day launch on-site with our CEO. 3-minute median support response. Trusted by ServiceTitan and Nexstar leaders."
  imageSrc="/generated/image-a-cheerful-home-services-dispatcher-is-s.webp"
  callsToAction={[
    {
      href: '/demo',
      label: 'Start demo',
      variant: 'primary'
    },
    {
      href: '/contact',
      label: 'Talk to our founder',
      variant: 'secondary'
    }
  ]}
/>

