<script lang="ts">
	// Types

	// Components
	import SectionHeader from "$lib/components/layout/SectionHeader.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Card from "$lib/components/ui/Card.svelte";
	import JobList, { type JobOpening } from "./JobList.svelte";

	// Icons
	import IconBriefcase from "~icons/lucide/briefcase";
	import IconUsers from "~icons/lucide/users";
	import IconHeart from "~icons/lucide/heart";
	import IconGlobe from "~icons/lucide/globe";

	// Constants
	const SECTION_BASE_CLASSES = "section-py section-px container mx-auto";
	const GRADIENT_BG_CLASSES =
		"bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800";
	const ICON_CONTAINER_CLASSES =
		"bg-primary-50 text-primary-600 dark:bg-primary-950 dark:text-primary-400 flex items-center justify-center rounded-full";

	const benefits = [
		{
			title: "Flexible Work",
			description: "Remote-first with flexible hours that respect work-life balance.",
			icon: IconBriefcase
		},
		{
			title: "Growth Opportunities",
			description: "Continuous learning with mentorship and education stipends.",
			icon: IconUsers
		},
		{
			title: "Comprehensive Benefits",
			description: "Health coverage, retirement plans, and generous paid time off.",
			icon: IconHeart
		}
	];

	const openings: JobOpening[] = [
		// Engineering
		{
			title: "Senior Frontend Developer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Backend Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Design Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Design
		{
			title: "UX/UI Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Product Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Product
		{
			title: "Product Manager",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Product Analyst",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Marketing
		{
			title: "Marketing Specialist",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Content Strategist",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Social Media Manager",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		}
	];

	const employeeTestimonials = [
  {
    name: "Rosa Martinez",
    position: "Customer Support Manager",
    company: "Customer Success Team",
    quote:
      "What I love most is how everyone lifts each other up. We celebrate wins together and help each other learn from the tough days. It truly feels like a family here.",
    image:
      "/generated/image-a-latina-woman-customer-support-manager-.webp"
  },
  {
    name: "David Kim",
    position: "Junior Software Engineer",
    company: "Engineering Team",
    quote:
      "From day one, my ideas were heard. The mentorship and growth opportunities are incredible—you get real projects and support to keep improving. I couldn't ask for a better place to start my career.",
    image:
      "/generated/image-a-korean-american-young-male-software-en.webp"
  },
  {
    name: "Alexis Carter",
    position: "Operations Specialist",
    company: "Operations Team",
    quote:
      "I've always felt comfortable bringing my whole self to work. The inclusive culture means you don’t just fit in—you belong. Teamwork and respect are the norm here.",
    image:
      "/generated/image-a-black-nonbinary-operations-specialist-.webp"
  }
];

	const processSteps = [
		{
			step: 1,
			title: "Apply",
			description:
				"Submit your application through our careers portal with your resume and portfolio."
		},
		{
			step: 2,
			title: "Interview",
			description: "Meet with our team to discuss your experience, skills, and career aspirations."
		},
		{
			step: 3,
			title: "Welcome aboard",
			description: "Join our team and start your journey building the future with us."
		}
	];

	const values = [
  {
    icon: IconHeart,
    title: "Customer obsessed",
    description: "Everything starts and ends with real dispatcher problems. If it won’t make their day, we don’t build it."
  },
  {
    icon: IconUsers,
    title: "No egos, just outcomes",
    description: "The best ideas win — from anyone, for anything. We care about what works, not who said it."
  },
  {
    icon: IconGlobe,
    title: "Learn fast",
    description: "Every project is a feedback loop. If teams or customers have a better answer, we try it immediately — and course-correct, fast."
  },
  {
    icon: IconBriefcase,
    title: "Direct access",
    description: "Our CEO works hand-in-hand with every team member and visits customers in person. No silos, lots of transparency."
  }
];
</script>

<!-- Hero Section -->

<SecondaryHero
	title="AI that helps real people"
	subtitle="Join a team that builds together, grows fast, and transforms home services from the inside out."
	imageSrc="/generated/image-a-cheerful-and-diverse-office-team-engag.webp"
/>

<!-- Why Join Us Section -->
<section class={SECTION_BASE_CLASSES}>
	<SectionHeader title="Why join us?" subtitle="Build your career while making an impact" />

	<div class="mt-16 grid gap-4 md:grid-cols-3">
		{#each benefits as benefit}
			<Card {...benefit} />
		{/each}
	</div>
</section>

<!-- Culture Section -->
<Culture {values} />

<Testimonials testimonials={employeeTestimonials} />

<!-- Application Process -->
<section class={SECTION_BASE_CLASSES}>
	<div class="mx-auto">
		<h2 class="text-title1 mb-16">Our application process</h2>

		<div class="grid gap-12 md:grid-cols-3">
			{#each processSteps as { step, title, description }, i}
				<div class="flex flex-col">
					<div class="{ICON_CONTAINER_CLASSES} mb-6 size-11">
						<span class="text-headline">{step}</span>
					</div>
					<h3 class="text-headline mb-3">{title}</h3>
					<p class="text-body text-emphasis-low">{description}</p>
				</div>
			{/each}
		</div>
	</div>
</section>
<!-- Current Openings Section -->
<section class={GRADIENT_BG_CLASSES}>
	<div class="section-px section-py container mx-auto grid w-full items-start lg:grid-cols-2">
		<SectionHeader title="Current openings" subtitle="Find your perfect role" />

		<JobList {openings} />
	</div>
</section>
