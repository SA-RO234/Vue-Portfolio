<script setup>
import { defineAsyncComponent } from "vue";
import LoadingSpinner from "./components/LoadingSpinner.vue";

const Serviceselection = defineAsyncComponent(() =>
  import("./components/Serviceselection.vue")
);
const AboutSection = defineAsyncComponent(() =>
  import("./components/AboutSection.vue")
);
const ExperienceAndSkills = defineAsyncComponent(() =>
  import("./components/ExperienceAndSkills.vue")
);
const LatestProjSection = defineAsyncComponent(() =>
  import("./components/LatestProjSection.vue")
);
const TestimonialSection = defineAsyncComponent(() =>
  import("./components/TestimonialsSection.vue")
);
const ContactSection = defineAsyncComponent(() =>
  import("./components/ContactSection.vue")
);
const Navbar = defineAsyncComponent(() => import("@/components/navbar.vue"));
const Herosection = defineAsyncComponent(() =>
  import("@/components/heroSection.vue")
);
const Fooster = defineAsyncComponent(() => import("@/components/Fooater.vue"));
const BackToTop = defineAsyncComponent(() =>
  import("@/components/BackToTop.vue")
);

</script>

<template>
  <div class="bg-[#111827] min-h-screen">
    <!--  Wrap component is Suspense to handle loading -->
    <Suspense>
      <template #default>
        <div>
        <Navbar />
        <Herosection />
        <Serviceselection />
        <AboutSection />
        <ExperienceAndSkills />
        <LatestProjSection />
        <ContactSection />
        <TestimonialSection />
        <Fooster />
        <BackToTop />
      </div>
      </template>
      <template #fallback>
        <div class="flex justify-center items-center min-h-screen">
           <LoadingSpinner/>
        </div>
      </template>
    </Suspense>
  </div>
</template>

<style>
 *{
  scrollbar-width: thin;
  scrollbar-color: #111827 #f1f1f1;
}
</style>