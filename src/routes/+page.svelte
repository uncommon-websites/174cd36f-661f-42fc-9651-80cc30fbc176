<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CustomerCardHero from "$lib/components/layout/hero-sections/CustomerCardHero.svelte";
</script>

<CustomerCardHero
  centered={true}
  title="Right tech. Right time. Every time."
  subtitle="Probook helps busy home service companies assign the best tech to every job—faster, smarter, and without the guesswork."
  customers={[
    {
      name: "Dani Dascher",
      position: "HVAC dispatcher",
      imageSrc: "/generated/image-a-friendly-female-hvac-dispatcher-in-an-.webp"
    },
    {
      name: "Chris Holleran",
      position: "Plumbing company manager",
      imageSrc: "/generated/image-a-confident-male-manager-of-a-plumbing-c.webp"
    },
    {
      name: "Monica Ramos",
      position: "Electrical dispatcher",
      imageSrc: "/generated/image-a-happy-female-dispatcher-for-an-electri.webp"
    },
    {
      name: "Ryan Laske",
      position: "HVAC technician",
      imageSrc: "/generated/image-a-reliable-male-hvac-technician-wearing-.webp"
    },
    {
      name: "Andrea Williams",
      position: "Plumbing dispatcher",
      imageSrc: "/generated/image-a-cheerful-female-dispatcher-for-a-plumb.webp"
    }
  ]}
/>
<LogoScroller
  label="Trusted by leading home service companies"
  logoUrls={[
    'https://logo.clearbit.com/ars.com',
    'https://logo.clearbit.com/apollohome.com',
    'https://logo.clearbit.com/tdindustries.com'
  ]}
/>

<Summary
	title="What we do"
	text="Probook provides AI-powered dispatching for home services companies. Optimize every technician assignment, increase sales, and run your board with less stress—all fully integrated with ServiceTitan. Exceptional support is just a call away."
/>

<Testimonials
	testimonials={[
		{
			name: "Harrison Mendez",
			position: "HVAC dispatcher",
			company: "AirWorks Heating & Cooling",
			quote: "With Probook, I can assign every job in a fraction of the time. What used to take hours now takes minutes, and I have fewer mistakes on the board. Our whole team is running smoother.",
			image: "/generated/image-a-male-hvac-dispatcher-in-a-bustling-off.webp"
		},
		{
			name: "Margot Leclair",
			position: "Owner",
			company: "Blue Pipe Plumbing",
			quote: "Before Probook, keeping track of revenue leaks was a constant worry. Now, jobs close faster and our monthly sales are up by 20%. It paid for itself in the first month.",
			image: "/generated/image-a-confident-female-plumbing-company-owne.webp"
		},
		{
			name: "Calvin Petrov",
			position: "Lead technician",
			company: "Bright Current Electrical",
			quote: "Probook matches me to jobs where I do my best work—and I don’t get sent across town needlessly. Less time wasted, less risk of missed calls, and happier customers.",
			image: "/generated/image-a-friendly-male-electrical-technician-st.webp"
		}
	]}
/>

<Features
	title="Smarter dispatching. Better results."
	subtitle="AI-powered scheduling that grows sales, saves time, and keeps customers happy."
	features={[
		{
			title: "Advanced AI job-matching",
			description: "Assigns the best technician to every job for more sales, higher flip rates, and better first-time fixes."
		},
		{
			title: "Rapid dispatcher efficiency",
			description: "Copilot suggests assignments instantly, while Autopilot reshuffles the full board so one dispatcher can manage 20+ techs."
		},
		{
			title: "ServiceTitan integration",
			description: "Probook syncs in real time with ServiceTitan, keeping jobs and technician data always up to date."
		},
		{
			title: "Responsive, human support",
			description: "Get industry-leading help with a 3-minute median response and 100% satisfaction from real people."
		},
		{
			title: "White-glove onboarding",
			description: "Be fully live in just 2 days with onsite training and setup from our CEO."
		},
		{
			title: "Proven by the best",
			description: "Top home service companies—big and small—use Probook to run more efficient, profitable teams."
		}
	]}
/>

<UseCases
	title="Use Cases"
	subtitle="Real-world applications for your business needs"
	useCases={[
		{
			title: "Fill your best techs’ day with high-revenue calls",
			description: "Probook automatically matches your strongest closers to high-value jobs—so they spend less time on low-priority calls and more time generating revenue.",
			image: "/generated/image-a-seasoned-hvac-technician-entering-a-su.webp",
			link: {
				href: "/use-cases/high-value-techs",
				label: "Learn more"
			}
		},
		{
			title: "Handle 25+ techs with one dispatcher",
			description: "Autopilot dynamically reshuffles the board for you—so one dispatcher can manage more techs across more calls, without cracking under pressure.",
			image: "/generated/image-a-busy-dispatcher-in-an-office-environme.webp",
			link: {
				href: "/use-cases/manage-more-techs",
				label: "Learn more"
			}
		},
		{
			title: "Keep customers happy—even when you're running behind",
			description: "Probook sends real-time alerts and recommends reschedules for late or running-over jobs—before the customer has to call in wondering where their tech is.",
			image: "/generated/image-a-dispatcher-in-a-modern-office-engaged-.webp",
			link: {
				href: "/use-cases/proactive-notifications",
				label: "Learn more"
			}
		}
	]}
/>

<AboutTeaser />
<CallToAction
  title="Dispatch smarter. Close more jobs."
  subtitle="Book a demo and see how much more efficient your team can be."
  description="Probook uses AI to match the right technician to the right job—boosting sales, improving efficiency, and easing the load on dispatchers. Built by dispatchers, for dispatchers, we help you move faster, make stronger decisions, and turn your board into a sales engine. Launch in just 2 days—with in-person help from our CEO—and experience customer support that actually responds."
  imageSrc="/generated/image-a-cheerful-home-service-dispatcher-in-a-.webp"
  callsToAction={[
    {
      href: '/demo',
      label: 'Book a demo',
      variant: 'primary'
    },
    {
      href: '/contact',
      label: 'Talk to sales',
      variant: 'secondary'
    }
  ]}
/>
