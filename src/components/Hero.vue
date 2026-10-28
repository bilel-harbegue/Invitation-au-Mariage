<template>
  <!-- =========================================================
       HERO SECTION
       الصفحة الرئيسية للدعوة
  ========================================================== -->

  <section
    id="hero"
    ref="sectionRef"
    class="hero-section relative flex h-screen min-h-screen items-center justify-center overflow-hidden bg-[#e7dfd1] text-[#3d3025]"
    :class="{ 'hero-active': isVisible }"
  >

    <!-- =======================================================
         AMBIENT LIGHT
    ======================================================== -->

    <div class="pointer-events-none absolute inset-0 overflow-hidden">

      <div
        class="hero-light-main absolute left-1/2 top-1/2 h-[700px] w-[700px] -translate-x-1/2 -translate-y-1/2 rounded-full blur-[100px]"
      ></div>

      <div
        class="hero-light-top absolute left-1/2 top-[-25%] h-[500px] w-[650px] -translate-x-1/2 rounded-full blur-[100px]"
      ></div>

      <div
        class="hero-light-bottom absolute bottom-[-30%] left-1/2 h-[500px] w-[700px] -translate-x-1/2 rounded-full blur-[100px]"
      ></div>

    </div>


    <!-- =======================================================
         TUNISIAN BACKGROUND PATTERN
    ======================================================== -->

    <div
      class="tunisian-background-pattern pointer-events-none absolute inset-0"
    ></div>

    <div
      class="secondary-pattern pointer-events-none absolute inset-0"
    ></div>


    <!-- =======================================================
         FLOATING GEOMETRIC ORNAMENTS
    ======================================================== -->

    <div class="pointer-events-none absolute inset-0">

      <span
        class="floating-diamond diamond-1 absolute h-[11px] w-[11px] border border-[#7e5b2b]/35"
      ></span>

      <span
        class="floating-diamond diamond-2 absolute h-[7px] w-[7px] border border-[#7e5b2b]/35"
      ></span>

      <span
        class="floating-diamond diamond-3 absolute h-[8px] w-[8px] border border-[#7e5b2b]/35"
      ></span>

      <span
        class="floating-diamond diamond-4 absolute h-[12px] w-[12px] border border-[#7e5b2b]/35"
      ></span>

      <span
        class="floating-dot dot-1 absolute h-1 w-1 rounded-full bg-[#a9824a]/50"
      ></span>

      <span
        class="floating-dot dot-2 absolute h-1 w-1 rounded-full bg-[#a9824a]/50"
      ></span>

      <span
        class="floating-dot dot-3 absolute h-1 w-1 rounded-full bg-[#a9824a]/50"
      ></span>

      <span
        class="floating-dot dot-4 absolute h-1 w-1 rounded-full bg-[#a9824a]/50"
      ></span>

      <span
        class="floating-cross cross-1 absolute h-[18px] w-[18px]"
      ></span>

      <span
        class="floating-cross cross-2 absolute h-[18px] w-[18px]"
      ></span>

    </div>


    <!-- =======================================================
         CENTRAL ORNAMENT
    ======================================================== -->

    <div
      class="central-ornament pointer-events-none absolute left-1/2 top-1/2 h-[570px] w-[570px] -translate-x-1/2 -translate-y-1/2 sm:h-[650px] sm:w-[650px]"
    >

      <div
        class="ornament-diamond absolute inset-0 rotate-45 border border-[#7e5b2b]/25"
      ></div>

      <div
        class="ornament-diamond ornament-diamond-2 absolute inset-[55px] rotate-45 border border-[#7e5b2b]/20"
      ></div>

      <div
        class="ornament-diamond ornament-diamond-3 absolute inset-[110px] rotate-45 border border-[#7e5b2b]/15"
      ></div>

      <div
        class="central-circle absolute left-1/2 top-1/2 h-[310px] w-[310px] -translate-x-1/2 -translate-y-1/2 rounded-full border border-[#7e5b2b]/10"
      ></div>

      <div
        class="ornament-center absolute left-1/2 top-1/2 h-28 w-28 -translate-x-1/2 -translate-y-1/2 rotate-45 border border-[#7e5b2b]/20 sm:h-36 sm:w-36"
      ></div>

      <span
        class="ornament-mark ornament-mark-top absolute left-1/2 top-[-5px] h-[9px] w-[9px] border border-[#7e5b2b]/40 bg-[#f8f4ec]"
      ></span>

      <span
        class="ornament-mark ornament-mark-bottom absolute bottom-[-5px] left-1/2 h-[9px] w-[9px] border border-[#7e5b2b]/40 bg-[#f8f4ec]"
      ></span>

      <span
        class="ornament-mark ornament-mark-left absolute left-[-5px] top-1/2 h-[9px] w-[9px] border border-[#7e5b2b]/40 bg-[#f8f4ec]"
      ></span>

      <span
        class="ornament-mark ornament-mark-right absolute right-[-5px] top-1/2 h-[9px] w-[9px] border border-[#7e5b2b]/40 bg-[#f8f4ec]"
      ></span>

    </div>


    <!-- =======================================================
         SIDE ORNAMENTS
    ======================================================== -->

    <div
      class="side-ornament side-ornament-left pointer-events-none absolute left-[4%] top-1/2 h-[330px] w-[110px] -translate-y-1/2 opacity-45"
    >

      <div class="side-pattern absolute inset-0"></div>

      <div
        class="side-diamond absolute left-1/2 top-1/2 h-[38px] w-[38px] -translate-x-1/2 -translate-y-1/2 rotate-45 border border-[#7e5b2b]/25"
      ></div>

    </div>


    <div
      class="side-ornament side-ornament-right pointer-events-none absolute right-[4%] top-1/2 h-[330px] w-[110px] -translate-y-1/2 opacity-45"
    >

      <div class="side-pattern absolute inset-0"></div>

      <div
        class="side-diamond absolute left-1/2 top-1/2 h-[38px] w-[38px] -translate-x-1/2 -translate-y-1/2 rotate-45 border border-[#7e5b2b]/25"
      ></div>

    </div>


    <!-- =======================================================
         OUTER FRAME
    ======================================================== -->

    <div
      class="pointer-events-none absolute inset-5 sm:inset-8 lg:inset-12"
    >

      <div
        class="frame-line frame-top absolute left-[55px] right-[55px] top-0 h-px bg-[#7e5b2b]/30"
      ></div>

      <div
        class="frame-line frame-bottom absolute bottom-0 left-[55px] right-[55px] h-px bg-[#7e5b2b]/30"
      ></div>

      <div
        class="frame-line frame-left absolute bottom-[55px] left-0 top-[55px] w-px bg-[#7e5b2b]/30"
      ></div>

      <div
        class="frame-line frame-right absolute bottom-[55px] right-0 top-[55px] w-px bg-[#7e5b2b]/30"
      ></div>

      <div
        class="frame-glow frame-glow-top absolute left-[20%] top-0 h-px w-[120px]"
      ></div>

      <div
        class="frame-glow frame-glow-bottom absolute bottom-0 right-[20%] h-px w-[120px]"
      ></div>

      <div
        class="corner-decoration corner-top-left absolute -left-[5px] -top-[5px] h-[62px] w-[62px]"
      >
        <span></span>
        <span></span>
        <span></span>
      </div>

      <div
        class="corner-decoration corner-top-right absolute -right-[5px] -top-[5px] h-[62px] w-[62px]"
      >
        <span></span>
        <span></span>
        <span></span>
      </div>

      <div
        class="corner-decoration corner-bottom-left absolute -bottom-[5px] -left-[5px] h-[62px] w-[62px]"
      >
        <span></span>
        <span></span>
        <span></span>
      </div>

      <div
        class="corner-decoration corner-bottom-right absolute -bottom-[5px] -right-[5px] h-[62px] w-[62px]"
      >
        <span></span>
        <span></span>
        <span></span>
      </div>

    </div>


    <!-- =======================================================
         MAIN CONTENT
    ======================================================== -->

    <div
      class="relative z-20 mx-auto flex h-full w-full max-w-6xl items-center justify-center px-5 text-center sm:px-7"
    >

      <div
        class="flex w-full min-w-0 flex-col items-center"
      >

        <!-- TOP DECORATION -->

        <div
          class="hero-top-decoration mb-6 flex items-center gap-4 sm:mb-9 sm:gap-6"
        >

          <span
            class="h-px w-10 bg-[#9b753f]/55 sm:w-20"
          ></span>

          <div
            class="relative flex items-center justify-center"
          >

            <span
              class="hero-top-diamond h-2 w-2 rotate-45 border border-[#8e6937] bg-[#f8f4ec]"
            ></span>

            <span
              class="absolute h-[5px] w-[5px] rounded-full bg-[#a9824a]"
            ></span>

          </div>

          <span
            class="h-px w-10 bg-[#9b753f]/55 sm:w-20"
          ></span>

        </div>


        <!-- EYEBROW -->

        <div class="hero-eyebrow">

          <span
            class="text-[9px] font-bold tracking-[0.32em] text-[#705536] sm:text-[13px] sm:tracking-[0.48em]"
            :class="{
              'font-arabic text-sm tracking-normal sm:text-lg':
                props.language === 'ar'
            }"
          >
            {{ content.eyebrow }}
          </span>

        </div>


        <!-- INVITATION -->

        <p
          class="hero-invitation mt-4 max-w-2xl px-3 text-[9px] font-semibold uppercase leading-6 tracking-[0.14em] text-[#685545] sm:mt-6 sm:px-0 sm:text-[12px] sm:leading-7 sm:tracking-[0.28em] md:text-[13px]"
          :class="{
            'font-arabic text-sm leading-7 tracking-normal sm:text-lg':
              props.language === 'ar'
          }"
        >
          {{ content.invitation }}
        </p>


        <!-- NAMES -->

        <div
          class="hero-names relative mt-7 sm:mt-11"
        >

          <div class="names-glow"></div>

          <div
            class="name-decoration name-decoration-left"
          ></div>

          <div
            class="name-decoration name-decoration-right"
          ></div>

          <h1
            class="relative font-serif text-[clamp(4.3rem,14vw,10rem)] font-semibold leading-[0.76] tracking-[-0.06em] text-[#30241c]"
            :class="{
              'font-arabic tracking-normal':
                props.language === 'ar'
            }"
          >
            {{ content.groom }}
          </h1>


          <!-- Ampersand -->

          <div
            class="hero-ampersand relative z-10 my-4 font-serif text-4xl font-semibold italic leading-none text-[#a0783d] sm:my-6 sm:text-6xl"
            :class="{
              'font-arabic not-italic':
                props.language === 'ar'
            }"
          >
            &amp;
          </div>


          <h2
            class="relative font-serif text-[clamp(4.3rem,14vw,10rem)] font-semibold leading-[0.76] tracking-[-0.06em] text-[#8a642f]"
            :class="{
              'font-arabic tracking-normal':
                props.language === 'ar'
            }"
          >
            {{ content.bride }}
          </h2>

        </div>


        <!-- ===================================================
             DATE
             تم إصلاح overflow على الهاتف
        ==================================================== -->

        <div
          class="hero-date mt-7 flex w-full max-w-[min(100%,680px)] min-w-0 items-center justify-center gap-2 px-1 sm:mt-11 sm:gap-8 sm:px-0"
          :dir="props.language === 'ar' ? 'rtl' : 'ltr'"
        >

          <!-- DATE 1 -->

          <div
            class="hero-date-item flex min-w-0 flex-1 items-center justify-center gap-2 sm:gap-5"
          >

            <span
              class="hero-date-line h-px w-3 shrink-0 bg-[#9b753f]/50 sm:w-14"
            ></span>

            <span
              class="hero-date-text min-w-0 whitespace-nowrap font-serif text-[10px] font-semibold tracking-[0.05em] text-[#60482d] sm:text-xl sm:tracking-[0.18em] md:text-2xl"
              :class="{
                'font-arabic text-[11px] tracking-normal sm:text-lg md:text-xl':
                  props.language === 'ar'
              }"
            >
              {{ content.date1 }}
            </span>

            <span
              class="hero-date-line h-px w-3 shrink-0 bg-[#9b753f]/50 sm:w-14"
            ></span>

          </div>


          <!-- CENTRAL SEPARATOR -->

          <span
            class="hero-date-separator h-7 w-px shrink-0 bg-[#9b753f]/30 sm:h-10"
          ></span>


          <!-- DATE 2 -->

          <div
            class="hero-date-item flex min-w-0 flex-1 items-center justify-center gap-2 sm:gap-5"
          >

            <span
              class="hero-date-line h-px w-3 shrink-0 bg-[#9b753f]/50 sm:w-14"
            ></span>

            <span
              class="hero-date-text min-w-0 whitespace-nowrap font-serif text-[10px] font-semibold tracking-[0.05em] text-[#60482d] sm:text-xl sm:tracking-[0.18em] md:text-2xl"
              :class="{
                'font-arabic text-[11px] tracking-normal sm:text-lg md:text-xl':
                  props.language === 'ar'
              }"
            >
              {{ content.date2 }}
            </span>

            <span
              class="hero-date-line h-px w-3 shrink-0 bg-[#9b753f]/50 sm:w-14"
            ></span>

          </div>

        </div>


        <!-- MESSAGE -->

        <p
          class="hero-message mt-5 max-w-xl px-5 text-[9px] font-medium leading-6 tracking-[0.05em] text-[#786657] sm:mt-8 sm:px-0 sm:text-[12px] sm:leading-7 sm:tracking-[0.1em]"
          :class="{
            'font-arabic text-sm tracking-normal sm:text-lg':
              props.language === 'ar'
          }"
        >
          {{ content.message }}
        </p>


        <!-- DISCOVER BUTTON -->

        <div
          class="hero-discover mt-6 sm:mt-10"
        >

          <button
            type="button"
            class="group flex cursor-pointer flex-col items-center gap-3 border-0 bg-transparent"
            @click="scrollToInvitation"
          >

            <span
              class="discover-label text-[8px] font-bold tracking-[0.28em] text-[#806b56] transition-colors duration-300 group-hover:text-[#8e6937] sm:text-[9px] sm:tracking-[0.32em]"
              :class="{
                'font-arabic text-sm tracking-normal':
                  props.language === 'ar'
              }"
            >
              {{ content.discover }}
            </span>

            <span
              class="discover-arrow flex h-[40px] w-[40px] items-center justify-center rounded-full border border-[#9b753f]/40 bg-[#fffdf8]/55 text-[#8e6937] transition-all duration-300 group-hover:-translate-y-[3px] group-hover:bg-[#fffdf8]/90 group-hover:shadow-[0_10px_25px_rgba(91,65,35,0.1)] sm:h-[42px] sm:w-[42px]"
            >

              <svg
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.4"
                class="h-4 w-4"
              >
                <path
                  d="M12 5v14M6 13l6 6 6-6"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>

            </span>

          </button>

        </div>

      </div>

    </div>


    <!-- =======================================================
         BOTTOM ORNAMENT
    ======================================================== -->

    <div
      class="pointer-events-none absolute bottom-5 left-1/2 z-20 -translate-x-1/2 sm:bottom-8"
    >

      <div
        class="flex items-center gap-3 opacity-75"
      >

        <span
          class="h-px w-7 bg-[#9b753f]/35 sm:w-8"
        ></span>

        <svg
          viewBox="0 0 24 24"
          class="h-3.5 w-3.5 fill-none stroke-[#8e6937]/70"
          stroke-width="1.2"
        >
          <path
            d="M20.8 8.8c0 5.2-8.8 10.1-8.8 10.1S3.2 14 3.2 8.8A4.8 4.8 0 0 1 12 6.2a4.8 4.8 0 0 1 8.8 2.6Z"
          />
        </svg>

        <span
          class="h-px w-7 bg-[#9b753f]/35 sm:w-8"
        ></span>

      </div>

    </div>

  </section>
</template>


<script setup>
import {
  computed,
  onBeforeUnmount,
  onMounted,
  ref,
} from 'vue'


/* =========================================================
   PROPS
========================================================= */

const props = defineProps({
  language: {
    type: String,
    default: 'fr',
  },
})


/* =========================================================
   SECTION VISIBILITY
========================================================= */

const sectionRef = ref(null)

const isVisible = ref(true)

let observer = null


/* =========================================================
   CONTENT
========================================================= */

const content = computed(() => {

  if (props.language === 'ar') {

    return {
      eyebrow: 'زفافنا',

      invitation:
        'يسعدنا دعوتكم لمشاركتنا فرحة زفافنا',

      groom: 'العريس',

      bride: 'العروس',

      date1: '15 جويلية 2030',

      date2: '16 جويلية 2030',

      message:
        'نتمنى أن تكونوا بيننا لنحتفل معًا بهذه المناسبة السعيدة',

      discover:
        'اكتشفوا الدعوة',
    }
  }


  return {
    eyebrow: 'NOTRE MARIAGE',

    invitation:
      'ONT LE PLAISIR DE VOUS INVITER À LEUR MARIAGE',

    groom: 'Le marié',

    bride: 'La mariée',

    date1: '15 JUILLET 2030',

    date2: '16 JUILLET 2030',

    message:
      'POUR PARTAGER AVEC EUX CE JOUR SI PARTICULIER',

    discover:
      'DÉCOUVRIR LA SUITE',
  }
})


/* =========================================================
   SCROLL TO INVITATION
========================================================= */

const scrollToInvitation = () => {

  const invitation =
    document.getElementById('invitation')

  if (!invitation) return

  invitation.scrollIntoView({
    behavior: 'smooth',
    block: 'start',
  })
}


/* =========================================================
   INTERSECTION OBSERVER
========================================================= */

onMounted(() => {

  if (!sectionRef.value) return

  observer = new IntersectionObserver(
    ([entry]) => {

      if (!entry) return

      isVisible.value =
        entry.isIntersecting
    },
    {
      threshold: 0.2,
    },
  )

  observer.observe(sectionRef.value)
})


/* =========================================================
   CLEANUP
========================================================= */

onBeforeUnmount(() => {

  observer?.disconnect()
})
</script>


<style scoped>

/* =========================================================
   AMBIENT LIGHT
========================================================= */

.hero-light-main {
  background:
    radial-gradient(
      circle,
      rgba(214, 180, 112, 0.15),
      rgba(214, 180, 112, 0.05) 40%,
      transparent 72%
    );

  animation:
    mainLightMove
    9s
    ease-in-out
    infinite;
}


.hero-light-top {
  background:
    rgba(234, 223, 201, 0.55);

  animation:
    topLightMove
    12s
    ease-in-out
    infinite;
}


.hero-light-bottom {
  background:
    rgba(231, 215, 186, 0.35);

  animation:
    bottomLightMove
    14s
    ease-in-out
    infinite;
}


/* =========================================================
   BACKGROUND PATTERN
========================================================= */

.tunisian-background-pattern {
  opacity: 0.085;

  background-image:
    linear-gradient(
      45deg,
      transparent 43%,
      rgba(111, 79, 40, 0.8) 44%,
      rgba(111, 79, 40, 0.8) 46%,
      transparent 47%
    ),
    linear-gradient(
      -45deg,
      transparent 43%,
      rgba(111, 79, 40, 0.8) 44%,
      rgba(111, 79, 40, 0.8) 46%,
      transparent 47%
    );

  background-size:
    130px 130px;

  animation:
    patternDrift
    35s
    linear
    infinite;
}


.secondary-pattern {
  opacity: 0.04;

  background-image:
    radial-gradient(
      circle,
      rgba(142, 105, 55, 0.7) 1px,
      transparent 1px
    );

  background-size:
    42px 42px;

  animation:
    dotsDrift
    24s
    linear
    infinite;
}


/* =========================================================
   FLOATING DIAMONDS
========================================================= */

.floating-diamond {
  transform: rotate(45deg);

  animation:
    floatingDiamond
    8s
    ease-in-out
    infinite;
}


.diamond-1 {
  top: 18%;
  left: 14%;
}


.diamond-2 {
  top: 28%;
  right: 13%;
  animation-delay: -2s;
}


.diamond-3 {
  bottom: 19%;
  left: 17%;
  animation-delay: -4s;
}


.diamond-4 {
  bottom: 25%;
  right: 17%;
  animation-delay: -6s;
}


/* =========================================================
   FLOATING DOTS
========================================================= */

.floating-dot {
  animation:
    floatingDot
    6s
    ease-in-out
    infinite;
}


.dot-1 {
  top: 31%;
  left: 22%;
}


.dot-2 {
  top: 20%;
  right: 24%;
  animation-delay: -2s;
}


.dot-3 {
  bottom: 28%;
  left: 25%;
  animation-delay: -4s;
}


.dot-4 {
  bottom: 20%;
  right: 23%;
  animation-delay: -1s;
}


/* =========================================================
   FLOATING CROSSES
========================================================= */

.floating-cross {
  opacity: 0.25;

  animation:
    floatingCross
    9s
    ease-in-out
    infinite;
}


.floating-cross::before,
.floating-cross::after {
  content: '';

  position: absolute;

  left: 50%;
  top: 50%;

  width: 100%;
  height: 1px;

  background:
    rgba(126, 91, 43, 0.6);

  transform:
    translate(-50%, -50%);
}


.floating-cross::after {
  width: 1px;
  height: 100%;
}


.cross-1 {
  top: 15%;
  right: 29%;
}


.cross-2 {
  bottom: 16%;
  left: 30%;
  animation-delay: -4s;
}


/* =========================================================
   CENTRAL ORNAMENT
========================================================= */

.central-ornament {
  opacity: 0.75;

  transition:
    opacity 1s ease,
    transform 1.2s cubic-bezier(
      0.22,
      1,
      0.36,
      1
    );

  animation:
    ornamentFloat
    11s
    ease-in-out
    infinite;
}


.ornament-diamond {
  animation:
    diamondBreathing
    7s
    ease-in-out
    infinite;
}


.ornament-diamond-2 {
  animation-delay: -2s;
}


.ornament-diamond-3 {
  animation-delay: -4s;
}


.central-circle {
  animation:
    circleBreathing
    9s
    ease-in-out
    infinite;
}


.ornament-center {
  animation:
    centerRotate
    14s
    linear
    infinite;
}


.ornament-center::before,
.ornament-center::after {
  content: '';

  position: absolute;

  left: 50%;
  top: 50%;

  background:
    rgba(126, 91, 43, 0.3);

  transform:
    translate(-50%, -50%);
}


.ornament-center::before {
  width: 42px;
  height: 1px;
}


.ornament-center::after {
  width: 1px;
  height: 42px;
}


.ornament-mark {
  animation:
    markPulse
    4s
    ease-in-out
    infinite;
}


.ornament-mark-top {
  transform:
    translateX(-50%)
    rotate(45deg);
}


.ornament-mark-bottom {
  transform:
    translateX(-50%)
    rotate(45deg);

  animation-delay: -2s;
}


.ornament-mark-left {
  transform:
    translateY(-50%)
    rotate(45deg);

  animation-delay: -1s;
}


.ornament-mark-right {
  animation-delay: -3s;

  transform:
    translateY(-50%)
    rotate(45deg);
}


/* =========================================================
   SIDE PATTERN
========================================================= */

.side-pattern {
  background-image:
    linear-gradient(
      45deg,
      transparent 46%,
      rgba(126, 91, 43, 0.35) 47%,
      rgba(126, 91, 43, 0.35) 53%,
      transparent 54%
    ),
    linear-gradient(
      -45deg,
      transparent 46%,
      rgba(126, 91, 43, 0.35) 47%,
      rgba(126, 91, 43, 0.35) 53%,
      transparent 54%
    );

  background-size:
    55px 55px;

  mask-image:
    linear-gradient(
      to bottom,
      transparent,
      black 15%,
      black 85%,
      transparent
    );

  animation:
    sidePatternMove
    14s
    linear
    infinite;
}


.side-pattern::before,
.side-pattern::after {
  content: '';

  position: absolute;

  left: 50%;

  width: 1px;
  height: 100%;

  background:
    rgba(126, 91, 43, 0.25);

  transform:
    translateX(-50%);
}


.side-pattern::after {
  width: 100%;
  height: 1px;
  top: 50%;
}


.side-diamond {
  animation:
    sideDiamond
    8s
    ease-in-out
    infinite;
}


/* =========================================================
   FRAME
========================================================= */

.frame-line {
  animation:
    framePulse
    5s
    ease-in-out
    infinite;
}


.frame-bottom {
  animation-delay: -2.5s;
}


.frame-right {
  animation-delay: -1.5s;
}


.frame-glow {
  background:
    linear-gradient(
      90deg,
      transparent,
      rgba(169, 130, 74, 0.5),
      transparent
    );

  filter:
    blur(1px);

  animation:
    frameGlowMove
    7s
    linear
    infinite;
}


.frame-glow-bottom {
  animation-delay: -3.5s;
}


/* =========================================================
   CORNERS
========================================================= */

.corner-decoration span {
  position: absolute;

  display: block;

  border:
    1px solid
    rgba(126, 91, 43, 0.35);

  transform:
    rotate(45deg);

  animation:
    cornerPulse
    6s
    ease-in-out
    infinite;
}


.corner-decoration span:nth-child(1) {
  width: 22px;
  height: 22px;
}


.corner-decoration span:nth-child(2) {
  width: 13px;
  height: 13px;
  animation-delay: -2s;
}


.corner-decoration span:nth-child(3) {
  width: 6px;
  height: 6px;

  background:
    rgba(126, 91, 43, 0.16);

  animation-delay: -4s;
}


.corner-top-left span:nth-child(1) {
  top: 12px;
  left: 12px;
}


.corner-top-left span:nth-child(2) {
  top: 30px;
  left: 30px;
}


.corner-top-left span:nth-child(3) {
  top: 42px;
  left: 42px;
}


.corner-top-right span:nth-child(1) {
  top: 12px;
  right: 12px;
}


.corner-top-right span:nth-child(2) {
  top: 30px;
  right: 30px;
}


.corner-top-right span:nth-child(3) {
  top: 42px;
  right: 42px;
}


.corner-bottom-left span:nth-child(1) {
  bottom: 12px;
  left: 12px;
}


.corner-bottom-left span:nth-child(2) {
  bottom: 30px;
  left: 30px;
}


.corner-bottom-left span:nth-child(3) {
  bottom: 42px;
  left: 42px;
}


.corner-bottom-right span:nth-child(1) {
  right: 12px;
  bottom: 12px;
}


.corner-bottom-right span:nth-child(2) {
  right: 30px;
  bottom: 30px;
}


.corner-bottom-right span:nth-child(3) {
  right: 42px;
  bottom: 42px;
}


/* =========================================================
   CONTENT INITIAL STATE
========================================================= */

.hero-top-decoration,
.hero-eyebrow,
.hero-invitation,
.hero-names,
.hero-date,
.hero-message,
.hero-discover {
  opacity: 0;

  filter:
    blur(7px);

  transition:
    opacity 1s cubic-bezier(
      0.22,
      1,
      0.36,
      1
    ),
    transform 1s cubic-bezier(
      0.22,
      1,
      0.36,
      1
    ),
    filter 1s ease;
}


/* =========================================================
   HERO ACTIVE
========================================================= */

.hero-active .hero-top-decoration {
  opacity: 1;
  filter: blur(0);
  transform: translateY(0);
  transition-delay: 0.05s;
}


.hero-active .hero-eyebrow {
  opacity: 1;
  filter: blur(0);
  transform: translateY(0);
  transition-delay: 0.16s;
}


.hero-active .hero-invitation {
  opacity: 1;
  filter: blur(0);
  transform: translateY(0);
  transition-delay: 0.28s;
}


.hero-active .hero-names {
  opacity: 1;
  filter: blur(0);

  transform:
    translateY(0)
    scale(1);

  transition-delay: 0.42s;
}


.hero-active .hero-date {
  opacity: 1;
  filter: blur(0);
  transform: translateY(0);
  transition-delay: 0.62s;
}


.hero-active .hero-message {
  opacity: 1;
  filter: blur(0);
  transform: translateY(0);
  transition-delay: 0.75s;
}


.hero-active .hero-discover {
  opacity: 1;
  filter: blur(0);
  transform: translateY(0);
  transition-delay: 0.9s;
}


/* =========================================================
   INITIAL TRANSFORMS
========================================================= */

.hero-top-decoration {
  transform:
    translateY(-30px);
}


.hero-eyebrow {
  transform:
    translateY(-25px);
}


.hero-invitation {
  transform:
    translateY(30px);
}


.hero-names {
  transform:
    translateY(50px)
    scale(0.94);
}


.hero-date {
  transform:
    translateY(35px);
}


.hero-message {
  transform:
    translateY(35px);
}


.hero-discover {
  transform:
    translateY(30px);
}


/* =========================================================
   NAMES GLOW
========================================================= */

.names-glow {
  position: absolute;

  left: 50%;
  top: 50%;

  width: 340px;
  height: 340px;

  border-radius: 999px;

  background:
    radial-gradient(
      circle,
      rgba(196, 154, 91, 0.12),
      rgba(196, 154, 91, 0.04) 45%,
      transparent 70%
    );

  transform:
    translate(-50%, -50%);

  animation:
    namesGlow
    6s
    ease-in-out
    infinite;
}


/* =========================================================
   NAME DECORATIONS
========================================================= */

.name-decoration {
  position: absolute;

  top: 50%;

  width: 38px;
  height: 38px;

  border:
    1px solid
    rgba(142, 105, 55, 0.24);

  transform:
    translateY(-50%)
    rotate(45deg);

  opacity: 0.65;

  animation:
    nameDecoration
    6s
    ease-in-out
    infinite;
}


.name-decoration-left {
  left: -55px;
}


.name-decoration-right {
  right: -55px;
  animation-delay: -3s;
}


/* =========================================================
   AMPERSAND
========================================================= */

.hero-ampersand {
  animation:
    ampersandGlow
    4s
    ease-in-out
    infinite;
}


/* =========================================================
   DISCOVER ARROW
========================================================= */

.discover-arrow {
  animation:
    arrowBounce
    2.4s
    ease-in-out
    infinite;
}


/* =========================================================
   KEYFRAMES
========================================================= */

@keyframes mainLightMove {

  0%,
  100% {
    opacity: 0.65;

    transform:
      translate(-50%, -50%)
      scale(0.95);
  }

  50% {
    opacity: 1;

    transform:
      translate(-50%, -50%)
      scale(1.08);
  }
}


@keyframes topLightMove {

  0%,
  100% {
    transform:
      translateX(-50%)
      translateY(0);
  }

  50% {
    transform:
      translateX(-50%)
      translateY(30px);
  }
}


@keyframes bottomLightMove {

  0%,
  100% {
    transform:
      translateX(-50%)
      translateY(0);
  }

  50% {
    transform:
      translateX(-50%)
      translateY(-25px);
  }
}


@keyframes patternDrift {

  from {
    background-position:
      0 0;
  }

  to {
    background-position:
      130px 130px;
  }
}


@keyframes dotsDrift {

  from {
    background-position:
      0 0;
  }

  to {
    background-position:
      42px -42px;
  }
}


@keyframes floatingDiamond {

  0%,
  100% {
    transform:
      translateY(0)
      rotate(45deg);

    opacity: 0.35;
  }

  50% {
    transform:
      translateY(-18px)
      rotate(135deg);

    opacity: 0.8;
  }
}


@keyframes floatingDot {

  0%,
  100% {
    transform:
      translateY(0)
      scale(1);

    opacity: 0.3;
  }

  50% {
    transform:
      translateY(-14px)
      scale(1.6);

    opacity: 0.8;
  }
}


@keyframes floatingCross {

  0%,
  100% {
    transform:
      rotate(0deg)
      scale(1);

    opacity: 0.2;
  }

  50% {
    transform:
      rotate(90deg)
      scale(1.15);

    opacity: 0.45;
  }
}


@keyframes ornamentFloat {

  0%,
  100% {
    transform:
      translate(-50%, -50%)
      scale(1);
  }

  50% {
    transform:
      translate(-50%, -50%)
      scale(1.018);
  }
}


@keyframes diamondBreathing {

  0%,
  100% {
    opacity: 0.45;
  }

  50% {
    opacity: 1;
  }
}


@keyframes circleBreathing {

  0%,
  100% {
    transform:
      translate(-50%, -50%)
      scale(0.96);
  }

  50% {
    transform:
      translate(-50%, -50%)
      scale(1.04);
  }
}


@keyframes centerRotate {

  from {
    transform:
      translate(-50%, -50%)
      rotate(45deg);
  }

  to {
    transform:
      translate(-50%, -50%)
      rotate(405deg);
  }
}


@keyframes markPulse {

  0%,
  100% {
    opacity: 0.45;
  }

  50% {
    opacity: 1;
  }
}


@keyframes sidePatternMove {

  from {
    background-position:
      0 0;
  }

  to {
    background-position:
      55px 55px;
  }
}


@keyframes sideDiamond {

  0%,
  100% {
    transform:
      translate(-50%, -50%)
      rotate(45deg)
      scale(0.9);
  }

  50% {
    transform:
      translate(-50%, -50%)
      rotate(135deg)
      scale(1.08);
  }
}


@keyframes framePulse {

  0%,
  100% {
    opacity: 0.55;
  }

  50% {
    opacity: 1;
  }
}


@keyframes frameGlowMove {

  0% {
    transform:
      translateX(-150px);

    opacity: 0;
  }

  25% {
    opacity: 1;
  }

  75% {
    opacity: 1;
  }

  100% {
    transform:
      translateX(650px);

    opacity: 0;
  }
}


@keyframes cornerPulse {

  0%,
  100% {
    opacity: 0.45;
  }

  50% {
    opacity: 1;
  }
}


@keyframes namesGlow {

  0%,
  100% {
    opacity: 0.55;

    transform:
      translate(-50%, -50%)
      scale(0.94);
  }

  50% {
    opacity: 1;

    transform:
      translate(-50%, -50%)
      scale(1.06);
  }
}


@keyframes nameDecoration {

  0%,
  100% {
    transform:
      translateY(-50%)
      rotate(45deg)
      scale(0.9);
  }

  50% {
    transform:
      translateY(-50%)
      rotate(135deg)
      scale(1.08);
  }
}


@keyframes ampersandGlow {

  0%,
  100% {
    opacity: 0.7;

    text-shadow:
      0 0 0
      rgba(169, 130, 74, 0);
  }

  50% {
    opacity: 1;

    text-shadow:
      0 0 25px
      rgba(169, 130, 74, 0.25);
  }
}


@keyframes arrowBounce {

  0%,
  100% {
    transform:
      translateY(0);
  }

  50% {
    transform:
      translateY(7px);
  }
}


/* =========================================================
   TABLET
========================================================= */

@media (max-width: 900px) {

  .side-ornament {
    display: none;
  }

  .floating-diamond,
  .floating-cross {
    opacity: 0.5;
  }
}


/* =========================================================
   MOBILE
========================================================= */

@media (max-width: 640px) {

  .tunisian-background-pattern {
    background-size:
      75px 75px;
  }


  .central-ornament {
    width: 430px;
    height: 430px;
  }


  .ornament-diamond-2 {
    inset: 40px;
  }


  .ornament-diamond-3 {
    inset: 80px;
  }


  .central-circle {
    width: 220px;
    height: 220px;
  }


  .ornament-center {
    width: 90px;
    height: 90px;
  }


  .frame-top,
  .frame-bottom {
    left: 25px;
    right: 25px;
  }


  .frame-left,
  .frame-right {
    top: 25px;
    bottom: 25px;
  }


  .name-decoration {
    display: none;
  }


  .names-glow {
    width: 260px;
    height: 260px;
  }


  .floating-diamond {
    width: 7px;
    height: 7px;
  }


  .floating-dot {
    width: 3px;
    height: 3px;
  }


  /* =======================================================
     DATE FIX
     منع التاريخ من الخروج خارج الشاشة
  ======================================================== */

  .hero-date {
    gap: 5px;
    padding-inline: 2px;
  }


  .hero-date-item {
    gap: 5px;
  }


  .hero-date-line {
    width: 7px;
  }


  .hero-date-text {
    font-size: 9px;
    letter-spacing: 0.02em;
  }


  .hero-date-separator {
    height: 28px;
  }

}


/* =========================================================
   VERY SMALL PHONES
   390px وما دون
========================================================= */

@media (max-width: 390px) {

  .hero-section {
    min-height: 100svh;
    height: 100svh;
  }


  .hero-date {
    max-width: 100%;
    gap: 4px;
  }


  .hero-date-item {
    gap: 3px;
  }


  .hero-date-line {
    width: 4px;
  }


  .hero-date-text {
    font-size: 8px;
    letter-spacing: 0;
  }


  .hero-date-separator {
    height: 25px;
  }


  .hero-message {
    margin-top: 16px;
  }


  .hero-discover {
    margin-top: 18px;
  }

}


/* =========================================================
   EXTRA SMALL PHONES
   350px وما دون
========================================================= */

@media (max-width: 350px) {

  .hero-date {
    gap: 3px;
  }


  .hero-date-item {
    gap: 2px;
  }


  .hero-date-line {
    display: none;
  }


  .hero-date-text {
    font-size: 8px;
  }


  .hero-date-separator {
    height: 22px;
  }

}


/* =========================================================
   REDUCED MOTION
========================================================= */

@media (prefers-reduced-motion: reduce) {

  .hero-light-main,
  .hero-light-top,
  .hero-light-bottom,
  .tunisian-background-pattern,
  .secondary-pattern,
  .floating-diamond,
  .floating-dot,
  .floating-cross,
  .central-ornament,
  .ornament-diamond,
  .central-circle,
  .ornament-center,
  .ornament-mark,
  .side-pattern,
  .side-diamond,
  .frame-line,
  .frame-glow,
  .corner-decoration span,
  .names-glow,
  .name-decoration,
  .hero-ampersand,
  .discover-arrow {
    animation: none !important;
  }

}

</style>