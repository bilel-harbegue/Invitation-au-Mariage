<template>
  <!-- =========================================================
       LOADING SCREEN
       شاشة البداية والتحميل
  ========================================================== -->

  <section
    class="loading-screen fixed inset-0 z-[9999] flex min-h-screen items-center justify-center overflow-hidden bg-[#e7dfd1] text-[#3d3025]"
    :class="{ 'is-opening': isOpening }"
  >

    <!-- =======================================================
         AMBIENT BACKGROUND
         الإضاءات الخلفية الناعمة
    ======================================================== -->

    <div class="pointer-events-none absolute inset-0 overflow-hidden">

      <!-- الضوء الرئيسي -->
      <div
        class="ambient-main absolute left-1/2 top-1/2 h-[700px] w-[700px] -translate-x-1/2 -translate-y-1/2 rounded-full blur-[100px]"
      ></div>

      <!-- الضوء العلوي -->
      <div
        class="ambient-top absolute left-1/2 top-[-25%] h-[480px] w-[680px] -translate-x-1/2 rounded-full blur-[100px]"
      ></div>

      <!-- الضوء السفلي -->
      <div
        class="ambient-bottom absolute bottom-[-30%] left-1/2 h-[450px] w-[620px] -translate-x-1/2 rounded-full blur-[100px]"
      ></div>

      <!-- الضوء الأيسر -->
      <div
        class="ambient-side absolute left-[-18%] top-1/2 h-[420px] w-[420px] -translate-y-1/2 rounded-full blur-[100px]"
      ></div>

      <!-- الضوء الأيمن -->
      <div
        class="ambient-side ambient-right absolute right-[-18%] top-1/2 h-[420px] w-[420px] -translate-y-1/2 rounded-full blur-[100px]"
      ></div>

    </div>


    <!-- =======================================================
         SUBTLE TUNISIAN PATTERN
         زخرفة تونسية هندسية خفيفة في الخلفية
    ======================================================== -->

    <div class="pointer-events-none absolute inset-0 opacity-[0.075]">
      <div class="tunisian-pattern absolute inset-0"></div>
    </div>


    <!-- =======================================================
         CENTRAL GEOMETRIC ORNAMENT
         الزخرفة الهندسية المركزية
    ======================================================== -->

    <div
      class="central-ornament pointer-events-none absolute left-1/2 top-1/2 h-[560px] w-[560px] -translate-x-1/2 -translate-y-1/2"
    >

      <!-- المربعات الهندسية -->
      <div
        class="ornament-square absolute inset-0 rotate-45 border border-[#7e5b2b]/70"
      ></div>

      <div
        class="ornament-square absolute inset-[80px] rotate-45 border border-[#7e5b2b]/70"
      ></div>

      <div
        class="ornament-square absolute inset-[160px] rotate-45 border border-[#7e5b2b]/70"
      ></div>

      <!-- الدوائر المركزية -->
      <div
        class="absolute left-1/2 top-1/2 h-[360px] w-[360px] -translate-x-1/2 -translate-y-1/2 rounded-full border border-[#7e5b2b]/45"
      ></div>

      <div
        class="absolute left-1/2 top-1/2 h-[450px] w-[450px] -translate-x-1/2 -translate-y-1/2 rounded-full border border-[#7e5b2b]/45"
      ></div>

    </div>


    <!-- =======================================================
         OUTER FRAME
         الإطار الزخرفي الخارجي
    ======================================================== -->

    <div
      class="loading-frame pointer-events-none absolute inset-5 sm:inset-8 lg:inset-12"
    >

      <!-- الزاوية العلوية اليسرى -->
      <span
        class="corner absolute left-0 top-0 h-[46px] w-[46px] border-l border-t border-[#7e5b2b]/35"
      ></span>

      <!-- الزاوية العلوية اليمنى -->
      <span
        class="corner absolute right-0 top-0 h-[46px] w-[46px] border-r border-t border-[#7e5b2b]/35"
      ></span>

      <!-- الزاوية السفلية اليسرى -->
      <span
        class="corner absolute bottom-0 left-0 h-[46px] w-[46px] border-b border-l border-[#7e5b2b]/35"
      ></span>

      <!-- الزاوية السفلية اليمنى -->
      <span
        class="corner absolute bottom-0 right-0 h-[46px] w-[46px] border-b border-r border-[#7e5b2b]/35"
      ></span>

    </div>


    <!-- =======================================================
         FLOATING GOLD PARTICLES
         الجزيئات الذهبية المتحركة
    ======================================================== -->

    <div class="pointer-events-none absolute inset-0">

      <span
        class="particle particle-1 absolute left-[15%] top-[18%] h-[3px] w-[3px] rounded-full bg-[#7e5b2b]/40 shadow-[0_0_10px_rgba(181,139,82,0.25)]"
      ></span>

      <span
        class="particle particle-2 absolute right-[16%] top-[25%] h-[3px] w-[3px] rounded-full bg-[#7e5b2b]/40 shadow-[0_0_10px_rgba(181,139,82,0.25)]"
      ></span>

      <span
        class="particle particle-3 absolute left-[11%] top-[60%] h-[3px] w-[3px] rounded-full bg-[#7e5b2b]/40 shadow-[0_0_10px_rgba(181,139,82,0.25)]"
      ></span>

      <span
        class="particle particle-4 absolute right-[12%] top-[72%] h-[3px] w-[3px] rounded-full bg-[#7e5b2b]/40 shadow-[0_0_10px_rgba(181,139,82,0.25)]"
      ></span>

      <span
        class="particle particle-5 absolute left-[48%] top-[12%] h-[3px] w-[3px] rounded-full bg-[#7e5b2b]/40 shadow-[0_0_10px_rgba(181,139,82,0.25)]"
      ></span>

      <span
        class="particle particle-6 absolute bottom-[17%] left-[40%] h-[3px] w-[3px] rounded-full bg-[#7e5b2b]/40 shadow-[0_0_10px_rgba(181,139,82,0.25)]"
      ></span>

      <span
        class="particle particle-7 absolute left-[7%] top-[43%] h-[3px] w-[3px] rounded-full bg-[#7e5b2b]/40 shadow-[0_0_10px_rgba(181,139,82,0.25)]"
      ></span>

      <span
        class="particle particle-8 absolute right-[7%] top-[48%] h-[3px] w-[3px] rounded-full bg-[#7e5b2b]/40 shadow-[0_0_10px_rgba(181,139,82,0.25)]"
      ></span>

    </div>


    <!-- =======================================================
         MAIN CONTENT
         المحتوى الرئيسي لشاشة البداية
    ======================================================== -->

    <div
      class="loading-content relative z-10 flex w-full max-w-5xl flex-col items-center px-6 text-center"
    >

      <!-- -----------------------------------------------------
           EYEBROW
           العنوان الصغير
      ------------------------------------------------------ -->

      <div class="loading-reveal mb-8 sm:mb-10">

        <div class="flex items-center gap-4 sm:gap-6">

          <span
            class="h-px w-10 bg-[#9b753f]/55 sm:w-20"
          ></span>

          <span
            class="loading-eyebrow text-[10px] font-semibold tracking-[0.38em] text-[#634a2c] sm:text-[13px] sm:tracking-[0.45em]"
            :class="{
              'font-arabic text-sm tracking-normal sm:text-base':
                language === 'ar'
            }"
          >
            {{ content.eyebrow }}
          </span>

          <span
            class="h-px w-10 bg-[#9b753f]/55 sm:w-20"
          ></span>

        </div>

      </div>


      <!-- -----------------------------------------------------
           MONOGRAM
           الشعار Y & R
      ------------------------------------------------------ -->

      <div class="logo-reveal relative mb-8 sm:mb-10">

        <!-- توهج خلف الشعار -->
        <div
          class="logo-glow absolute inset-[-20px] rounded-full"
        ></div>

        <!-- دائرة الشعار -->
        <div
          class="monogram relative flex h-[92px] w-[92px] items-center justify-center rounded-full border border-[#a9824a]/45 bg-[#fffdf8]/80 shadow-[0_15px_50px_rgba(130,95,45,0.12)] backdrop-blur-sm sm:h-[108px] sm:w-[108px]"
        >

          <!-- الإطار الداخلي -->
          <div
            class="absolute inset-[7px] rounded-full border border-[#b58b52]/30"
          ></div>

          <!-- الماسة العلوية -->
          <div
            class="absolute left-1/2 top-[9px] h-2 w-2 -translate-x-1/2 rotate-45 border border-[#a9824a]/60 bg-[#fffdf8]"
          ></div>

          <!-- حرف Y -->
          <span
            class="relative -translate-y-[2px] font-serif text-[30px] italic leading-none text-[#8e6937] sm:text-[36px]"
          >
            Y
          </span>

          <!-- & -->
          <span
            class="absolute bottom-[15px] left-1/2 -translate-x-1/2 font-serif text-[9px] italic text-[#9b753f] sm:bottom-[18px]"
          >
            &amp;
          </span>

          <!-- حرف R -->
          <span
            class="absolute right-[22px] top-[14px] font-serif text-[12px] italic text-[#9b753f]/80 sm:right-[26px] sm:top-[16px]"
          >
            R
          </span>

        </div>

      </div>


      <!-- -----------------------------------------------------
           NAMES
           أسماء العروسين
      ------------------------------------------------------ -->

      <div class="names-reveal">

        <!-- اسم العريس -->
        <h1
          class="loading-name-groom font-serif text-[clamp(4.3rem,14vw,10rem)] font-medium leading-[0.8] tracking-[-0.055em] text-[#30241c]"
          :class="{
            'font-arabic tracking-normal':
              language === 'ar'
          }"
        >
          {{ content.groom }}
        </h1>

        <!-- الفاصل بين الاسمين -->
        <div
          class="ampersand my-4 font-serif text-3xl font-medium italic text-[#a67b3e] sm:my-5 sm:text-4xl"
        >
          &amp;
        </div>

        <!-- اسم العروس -->
        <h2
          class="loading-name-bride font-serif text-[clamp(4.3rem,14vw,10rem)] font-medium leading-[0.8] tracking-[-0.055em] text-[#8a642f]"
          :class="{
            'font-arabic tracking-normal':
              language === 'ar'
          }"
        >
          {{ content.bride }}
        </h2>

      </div>


      <!-- -----------------------------------------------------
           SUBTITLE
           النص التعريفي
      ------------------------------------------------------ -->

      <div class="subtitle-reveal mt-8 sm:mt-10">

        <p
          class="loading-subtitle text-[10px] font-semibold tracking-[0.28em] text-[#4d3d30]/90 sm:text-[13px] sm:tracking-[0.4em]"
          :class="{
            'font-arabic text-sm leading-8 tracking-normal sm:text-base':
              language === 'ar'
          }"
        >
          {{ content.subtitle }}
        </p>

      </div>


      <!-- -----------------------------------------------------
           LOADING BAR
           شريط التحميل
      ------------------------------------------------------ -->

      <div
        class="loading-bar-reveal mt-12 w-full max-w-[280px] sm:mt-14 sm:max-w-[330px]"
      >

        <div class="mb-2.5 flex items-center justify-between">

          <!-- نص التحميل -->
          <span
            class="loading-label text-[9px] font-medium tracking-[0.22em] text-[#574638]/75 sm:text-[10px]"
            :class="{
              'font-arabic text-xs tracking-normal':
                language === 'ar'
            }"
          >
            {{ content.loading }}
          </span>

          <!-- نسبة التحميل -->
          <span
            class="text-[9px] font-semibold tracking-[0.18em] text-[#8e6937] sm:text-[10px]"
          >
            100%
          </span>

        </div>

        <!-- شريط التقدم -->
        <div
          class="h-[2px] w-full overflow-hidden rounded-full bg-[#a9824a]/15"
        >
          <div class="loading-progress h-full"></div>
        </div>

      </div>

    </div>


    <!-- =======================================================
         BOTTOM ORNAMENT
         الزخرفة السفلية
    ======================================================== -->

    <div
      class="bottom-decoration pointer-events-none absolute bottom-7 left-1/2 -translate-x-1/2 sm:bottom-9"
    >

      <div class="flex items-center gap-3">

        <span
          class="h-px w-8 bg-[#a9824a]/30 sm:w-10"
        ></span>

        <span
          class="bottom-diamond h-2 w-2 rotate-45 border border-[#8e6937]/55"
        ></span>

        <span
          class="h-px w-8 bg-[#a9824a]/30 sm:w-10"
        ></span>

      </div>

    </div>


    <!-- =======================================================
         INVITATION COVER
         الصفحة نفسها تتحول إلى غلاف الدعوة
    ======================================================== -->

    <div
      class="invitation-cover pointer-events-none absolute inset-0 z-[50]"
      :class="{ 'is-opening': isOpening }"
      aria-hidden="true"
    >

      <!-- ظل وإضاءة الغلاف -->
      <div class="invitation-cover-glow"></div>


      <!-- -----------------------------------------------------
           TRIANGULAR COVER
           المثلث الكبير الذي يمثل غلاف الدعوة
      ------------------------------------------------------ -->

      <div class="invitation-flap bg-[#e7dfd1] text-[#3d3025]">

        <!-- الحافة الذهبية الداخلية -->
        <div class="invitation-flap-border"></div>


        <!-- الزخرفة الهندسية المركزية -->
        <div class="invitation-flap-ornament">

          <span></span>

          <div class="invitation-flap-diamond">
            <span></span>
          </div>

          <span></span>

        </div>


        <!-- الخط العمودي المركزي -->
        <div class="invitation-flap-center-line"></div>


        <!-- النقطة الزخرفية -->
        <div class="invitation-flap-dot"></div>

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


// =========================================================
// PROPS
// استقبال اللغة من المكون الأب
// =========================================================

const props = defineProps({
  language: {
    type: String,
    default: 'fr',
  },
})


// =========================================================
// EVENTS
// إرسال حدث عند انتهاء شاشة التحميل
// =========================================================

const emit = defineEmits([
  'finished',
])


// =========================================================
// STATE
// حالة فتح غلاف الدعوة
// =========================================================

const isOpening = ref(false)


// =========================================================
// CONTENT
// النصوص حسب اللغة المختارة
// =========================================================

const content = computed(() => {

  // -----------------------------
  // Arabic
  // -----------------------------

  if (props.language === 'ar') {

    return {
      eyebrow: 'زفافنا',
      groom: 'فولان',
      bride: 'فلتانة',
      subtitle: 'دعوتكم لمشاركتنا فرحتنا',
      loading: 'جاري فتح الدعوة',
    }

  }


  // -----------------------------
  // French
  // -----------------------------

  return {
    eyebrow: 'NOTRE MARIAGE',
    groom: 'foulen',
    bride: 'faltena',
    subtitle: 'NOTRE INVITATION',
    loading: 'OUVERTURE DE VOTRE INVITATION',
  }

})


// =========================================================
// TIMERS
// التحكم في توقيت فتح الغلاف وإنهاء شاشة البداية
// =========================================================

let openTimer = null
let finishTimer = null


// =========================================================
// MOUNT
// بدء شاشة التحميل عند ظهور المكون
// =========================================================

onMounted(() => {

  /*
   * 4 ثوانٍ لشاشة التحميل.
   *
   * بعد ذلك يبدأ فتح غلاف الدعوة.
   */

  openTimer = window.setTimeout(() => {

    isOpening.value = true


    /*
     * بعد بدء حركة الفتح مباشرة يتم إنهاء شاشة البداية.
     */

    finishTimer = window.setTimeout(() => {

      emit('finished')

    }, 150)

  }, 4000)

})


// =========================================================
// UNMOUNT
// تنظيف المؤقتات عند إزالة المكون
// =========================================================

onBeforeUnmount(() => {

  if (openTimer) {
    window.clearTimeout(openTimer)
  }

  if (finishTimer) {
    window.clearTimeout(finishTimer)
  }

})
</script>


<style scoped>

/* =========================================================
   BACKGROUND
   الإضاءات والحركة الخلفية
========================================================= */

.ambient-main {
  background:
    radial-gradient(
      circle,
      rgba(212, 175, 106, 0.13) 0%,
      rgba(212, 175, 106, 0.055) 38%,
      transparent 72%
    );

  animation:
    ambientMain 8s ease-in-out infinite;
}


.ambient-top {
  background:
    rgba(231, 213, 181, 0.38);

  animation:
    ambientTop 10s ease-in-out infinite;
}


.ambient-bottom {
  background:
    rgba(212, 175, 106, 0.12);

  animation:
    ambientBottom 12s ease-in-out infinite;
}


.ambient-side {
  background:
    rgba(234, 223, 201, 0.55);

  animation:
    ambientSide 9s ease-in-out infinite;
}


.ambient-right {
  animation-delay: -4s;
}


/* =========================================================
   TUNISIAN PATTERN
   النمط الهندسي التونسي
========================================================= */

.tunisian-pattern {
  width: 100%;
  height: 100%;

  background-image:
    linear-gradient(
      45deg,
      transparent 42%,
      rgba(126, 91, 43, 0.75) 43%,
      rgba(126, 91, 43, 0.75) 44%,
      transparent 45%
    ),
    linear-gradient(
      -45deg,
      transparent 42%,
      rgba(126, 91, 43, 0.75) 43%,
      rgba(126, 91, 43, 0.75) 44%,
      transparent 45%
    );

  background-size:
    100px 100px;

  animation:
    patternMove 28s linear infinite;
}


/* =========================================================
   CENTRAL ORNAMENT
   الزخرفة الهندسية المركزية
========================================================= */

.central-ornament {
  opacity: 0.055;

  animation:
    centralFloat 12s ease-in-out infinite;
}


/* =========================================================
   LOGO
   توهج الشعار وحركة الـ Ampersand
========================================================= */

.logo-glow {
  background:
    radial-gradient(
      circle,
      rgba(212, 175, 106, 0.22),
      transparent 68%
    );

  filter: blur(18px);

  animation:
    logoGlow 3.8s ease-in-out infinite;
}


.ampersand {
  animation:
    ampersandGlow 3s ease-in-out infinite;
}


/* =========================================================
   LOADING
   شريط التحميل
========================================================= */

.loading-progress {
  width: 100%;

  transform-origin:
    left center;

  background:
    linear-gradient(
      90deg,
      #9b753f 0%,
      #c49a5b 35%,
      #ead09a 65%,
      #b58b52 100%
    );

  animation:
    progress
    4s
    cubic-bezier(0.65, 0, 0.35, 1)
    forwards;

  box-shadow:
    0 0 10px
    rgba(181, 139, 82, 0.22);
}


/* =========================================================
   PARTICLES
   الجزيئات الذهبية
========================================================= */

.particle {
  animation:
    particleFloat 6s ease-in-out infinite;
}


.particle-2 {
  animation-duration: 8s;
  animation-delay: 1s;
}


.particle-3 {
  animation-duration: 7s;
  animation-delay: 0.5s;
}


.particle-4 {
  animation-duration: 9s;
  animation-delay: 1.5s;
}


.particle-5 {
  animation-duration: 7s;
  animation-delay: 2s;
}


.particle-6 {
  animation-duration: 8s;
  animation-delay: 0.8s;
}


.particle-7 {
  animation-duration: 6s;
  animation-delay: 1.2s;
}


.particle-8 {
  animation-duration: 7s;
  animation-delay: 2.2s;
}


/* =========================================================
   CONTENT REVEALS
   ظهور عناصر المحتوى تدريجيًا
========================================================= */

.loading-reveal {
  animation:
    fadeDown
    0.9s
    0.15s
    both
    cubic-bezier(0.22, 1, 0.36, 1);
}


.logo-reveal {
  animation:
    logoReveal
    1s
    0.3s
    both
    cubic-bezier(0.22, 1, 0.36, 1);
}


.names-reveal {
  animation:
    namesReveal
    1.15s
    0.55s
    both
    cubic-bezier(0.22, 1, 0.36, 1);
}


.subtitle-reveal {
  animation:
    fadeUp
    0.9s
    0.9s
    both
    cubic-bezier(0.22, 1, 0.36, 1);
}


.date-reveal {
  animation:
    fadeUp
    0.9s
    1.05s
    both
    cubic-bezier(0.22, 1, 0.36, 1);
}


.loading-bar-reveal {
  animation:
    fadeUp
    0.9s
    1.2s
    both
    cubic-bezier(0.22, 1, 0.36, 1);
}


.bottom-decoration {
  animation:
    fadeUp
    0.9s
    1.35s
    both
    cubic-bezier(0.22, 1, 0.36, 1);
}


.bottom-diamond {
  animation:
    diamondPulse
    2.8s
    ease-in-out
    infinite;
}


/* =========================================================
   ORIGINAL CONTENT DURING OPENING
   اختفاء المحتوى عند فتح الغلاف
========================================================= */

.loading-content {
  transition:
    opacity 0.8s ease,
    transform 1s cubic-bezier(0.22, 1, 0.36, 1),
    filter 0.8s ease;
}


.loading-screen.is-opening
.loading-content {
  opacity: 0;

  transform:
    translateY(-18px)
    scale(0.985);

  filter:
    blur(3px);
}


/* =========================================================
   COVER
   ظهور غلاف الدعوة
========================================================= */

.invitation-cover {
  opacity: 0;

  visibility: hidden;

  transition:
    opacity 0.5s ease,
    visibility 0s linear 0.5s;
}


.loading-screen.is-opening
.invitation-cover {
  opacity: 1;

  visibility: visible;

  transition:
    opacity 0.5s ease,
    visibility 0s;
}


/* =========================================================
   COVER LIGHT
   الإضاءة خلف المثلث
========================================================= */

.invitation-cover-glow {
  position: absolute;

  left: 50%;

  bottom: -20%;

  width: min(1100px, 130vw);

  height: min(700px, 80vh);

  transform:
    translateX(-50%);

  border-radius: 50%;

  background:
    radial-gradient(
      ellipse at center,
      rgba(190, 150, 85, 0.15) 0%,
      rgba(190, 150, 85, 0.07) 32%,
      transparent 72%
    );

  filter:
    blur(28px);

  opacity: 0;

  transition:
    opacity 1.8s ease 0.15s;
}


.loading-screen.is-opening
.invitation-cover-glow {
  opacity: 1;
}


/* =========================================================
   MAIN TRIANGULAR COVER
   المثلث الرئيسي — غلاف الدعوة
========================================================= */

.invitation-flap {
  position: absolute;

  left: 50%;

  bottom: -1%;

  width: 100%;

  height: 92vh;

  min-height: 600px;

  transform:
    translateX(-50%)
    translateY(12px);

  clip-path:
    polygon(
      0 100%,
      50% 0,
      100% 100%
    );

  background: #e7dfd1;

  color: #3d3025;

  box-shadow:
    0 -20px 55px
    rgba(91, 65, 35, 0.07),

    inset 0 3px 0
    rgba(255, 255, 255, 0.55),

    inset 0 -60px 90px
    rgba(111, 78, 39, 0.05);

  opacity: 0;

  transition:
    opacity 0.6s ease 0.1s,
    transform 2.2s
      cubic-bezier(
        0.16,
        1,
        0.3,
        1
      );
}


/* =========================================================
   OPEN
   حركة صعود المثلث إلى الأعلى
========================================================= */

.loading-screen.is-opening
.invitation-flap {
  opacity: 1;

  transform:
    translateX(-50%)
    translateY(-108%);
}


/* =========================================================
   INNER GOLD BORDER
   الحافة الداخلية الذهبية
========================================================= */

.invitation-flap-border {
  position: absolute;

  left: 4%;

  right: 4%;

  top: 5%;

  bottom: 4%;

  clip-path:
    polygon(
      0 100%,
      50% 0,
      100% 100%
    );

  border:
    1px solid
    rgba(142, 105, 55, 0.22);

  opacity: 0.85;
}


/* =========================================================
   CENTRAL GEOMETRIC ORNAMENT
   الزخرفة المركزية للمثلث
========================================================= */

.invitation-flap-ornament {
  position: absolute;

  left: 50%;

  top: 43%;

  display: flex;

  align-items: center;

  justify-content: center;

  gap: 18px;

  transform:
    translate(-50%, -50%);

  opacity: 0.58;

  transition:
    opacity 0.8s ease,
    transform 1.2s
      cubic-bezier(
        0.16,
        1,
        0.3,
        1
      );
}


.loading-screen.is-opening
.invitation-flap-ornament {
  opacity: 0;

  transform:
    translate(-50%, -42%)
    scale(0.82);
}


/* =========================================================
   ORNAMENT LINES
   الخطوط الجانبية للزخرفة
========================================================= */

.invitation-flap-ornament > span {
  display: block;

  width: 65px;

  height: 1px;

  background:
    linear-gradient(
      90deg,
      transparent,
      rgba(151, 112, 58, 0.55)
    );
}


.invitation-flap-ornament > span:last-child {
  background:
    linear-gradient(
      90deg,
      rgba(151, 112, 58, 0.55),
      transparent
    );
}


/* =========================================================
   ORNAMENT DIAMOND
   الماسة المركزية
========================================================= */

.invitation-flap-diamond {
  position: relative;

  display: flex;

  width: 48px;

  height: 48px;

  align-items: center;

  justify-content: center;

  border:
    1px solid
    rgba(151, 112, 58, 0.55);

  transform:
    rotate(45deg);
}


.invitation-flap-diamond::before {
  position: absolute;

  inset: 7px;

  border:
    1px solid
    rgba(151, 112, 58, 0.32);

  content: "";
}


.invitation-flap-diamond span {
  width: 14px;

  height: 14px;

  border:
    1px solid
    rgba(151, 112, 58, 0.45);
}


/* =========================================================
   CENTER VERTICAL LINE
   الخط العمودي المركزي
========================================================= */

.invitation-flap-center-line {
  position: absolute;

  left: 50%;

  top: 57%;

  width: 1px;

  height: 95px;

  transform:
    translateX(-50%);

  background:
    linear-gradient(
      to bottom,
      rgba(151, 112, 58, 0.42),
      rgba(151, 112, 58, 0)
    );

  opacity: 0.65;

  transition:
    opacity 0.7s ease;
}


.loading-screen.is-opening
.invitation-flap-center-line {
  opacity: 0;
}


/* =========================================================
   CENTER DOT
   النقطة الزخرفية المركزية
========================================================= */

.invitation-flap-dot {
  position: absolute;

  left: 50%;

  top: 57%;

  width: 6px;

  height: 6px;

  transform:
    translate(-50%, -50%)
    rotate(45deg);

  border:
    1px solid
    rgba(151, 112, 58, 0.55);

  background:
    #e7dfd1;

  transition:
    opacity 0.7s ease,
    transform 0.8s ease;
}


.loading-screen.is-opening
.invitation-flap-dot {
  opacity: 0;

  transform:
    translate(-50%, -50%)
    rotate(45deg)
    scale(0.5);
}


/* =========================================================
   OPENING EDGE
   الحافة السفلية للمثلث
========================================================= */

.invitation-flap::after {
  position: absolute;

  left: 0;

  bottom: 0;

  width: 100%;

  height: 1px;

  background:
    linear-gradient(
      90deg,
      transparent 0%,
      rgba(142, 105, 55, 0.35) 20%,
      rgba(142, 105, 55, 0.55) 50%,
      rgba(142, 105, 55, 0.35) 80%,
      transparent 100%
    );

  content: "";
}


/* =========================================================
   KEYFRAMES
   جميع الحركات والأنيميشن
========================================================= */

@keyframes ambientMain {

  0%,
  100% {
    opacity: 0.7;

    transform:
      scale(0.95);
  }

  50% {
    opacity: 1;

    transform:
      scale(1.08);
  }

}


@keyframes ambientTop {

  0%,
  100% {
    transform:
      translate(-50%, 0);
  }

  50% {
    transform:
      translate(-50%, 30px);
  }

}


@keyframes ambientBottom {

  0%,
  100% {
    transform:
      translate(-50%, 0);
  }

  50% {
    transform:
      translate(-50%, -25px);
  }

}


@keyframes ambientSide {

  0%,
  100% {
    opacity: 0.45;

    transform:
      translateY(-50%)
      scale(0.95);
  }

  50% {
    opacity: 0.7;

    transform:
      translateY(-50%)
      scale(1.08);
  }

}


@keyframes patternMove {

  from {
    background-position:
      0 0;
  }

  to {
    background-position:
      100px 100px;
  }

}


@keyframes centralFloat {

  0%,
  100% {
    transform:
      translate(-50%, -50%)
      rotate(0deg)
      scale(0.98);
  }

  50% {
    transform:
      translate(-50%, -50%)
      rotate(2deg)
      scale(1.02);
  }

}


@keyframes logoGlow {

  0%,
  100% {
    opacity: 0.35;

    transform:
      scale(0.95);
  }

  50% {
    opacity: 0.75;

    transform:
      scale(1.08);
  }

}


@keyframes ampersandGlow {

  0%,
  100% {
    opacity: 0.65;

    text-shadow:
      0 0 0
      rgba(181, 139, 82, 0);
  }

  50% {
    opacity: 1;

    text-shadow:
      0 0 18px
      rgba(181, 139, 82, 0.32);
  }

}


@keyframes progress {

  from {
    transform:
      scaleX(0);
  }

  to {
    transform:
      scaleX(1);
  }

}


@keyframes fadeDown {

  from {
    opacity: 0;

    transform:
      translateY(-16px);
  }

  to {
    opacity: 1;

    transform:
      translateY(0);
  }

}


@keyframes fadeUp {

  from {
    opacity: 0;

    transform:
      translateY(16px);
  }

  to {
    opacity: 1;

    transform:
      translateY(0);
  }

}


@keyframes logoReveal {

  from {
    opacity: 0;

    transform:
      scale(0.72)
      rotate(-7deg);
  }

  to {
    opacity: 1;

    transform:
      scale(1)
      rotate(0);
  }

}


@keyframes namesReveal {

  from {
    opacity: 0;

    transform:
      translateY(28px);

    letter-spacing:
      0.04em;
  }

  to {
    opacity: 1;

    transform:
      translateY(0);

    letter-spacing:
      -0.055em;
  }

}


@keyframes particleFloat {

  0%,
  100% {
    opacity: 0.18;

    transform:
      translateY(0)
      scale(0.8);
  }

  50% {
    opacity: 0.75;

    transform:
      translateY(-16px)
      scale(1.15);
  }

}


@keyframes diamondPulse {

  0%,
  100% {
    opacity: 0.4;

    transform:
      rotate(45deg)
      scale(0.85);
  }

  50% {
    opacity: 0.9;

    transform:
      rotate(45deg)
      scale(1.15);
  }

}


/* =========================================================
   MOBILE
   تحسين العرض على الهاتف
========================================================= */

@media (max-width: 640px) {

  .loading-content {
    padding-left: 20px;
    padding-right: 20px;
  }


  .tunisian-pattern {
    background-size:
      65px 65px;
  }


  .central-ornament {
    width: 400px;

    height: 400px;

    opacity: 0.045;
  }


  .central-ornament
  .ornament-square:nth-child(2) {
    inset: 58px;
  }


  .central-ornament
  .ornament-square:nth-child(3) {
    inset: 116px;
  }


  .central-ornament
  > div:nth-child(4) {
    width: 260px;

    height: 260px;
  }


  .central-ornament
  > div:nth-child(5) {
    width: 330px;

    height: 330px;
  }


  .loading-frame {
    inset: 14px;
  }


  .corner {
    width: 30px;

    height: 30px;
  }


  .particle-7,
  .particle-8 {
    display: none;
  }


  .loading-reveal {
    margin-bottom: 28px;
  }


  .loading-reveal > div {
    gap: 12px;
  }


  .loading-reveal > div > span:first-child,
  .loading-reveal > div > span:last-child {
    width: 30px;
  }


  .loading-eyebrow {
    font-size: 9px;

    letter-spacing: 0.25em;

    white-space: nowrap;
  }


  .monogram {
    width: 84px;

    height: 84px;
  }


  .monogram > span:first-of-type {
    font-size: 28px;
  }


  .loading-name-groom,
  .loading-name-bride {
    font-size: clamp(3.8rem, 16vw, 5rem);

    line-height: 0.82;
  }


  .names-reveal .ampersand {
    margin-top: 14px;

    margin-bottom: 14px;

    font-size: 1.8rem;
  }


  .loading-subtitle {
    max-width: 280px;

    margin-left: auto;

    margin-right: auto;

    line-height: 1.8;
  }


  .loading-bar-reveal {
    max-width: 250px;

    margin-top: 34px;
  }


  .loading-label {
    max-width: 190px;

    line-height: 1.5;
  }


  .bottom-decoration {
    bottom: 20px;
  }


  .invitation-flap {
    width: 145vw;

    height: 82vh;

    min-height: 560px;
  }


  .invitation-flap-border {
    left: 6%;

    right: 6%;

    top: 5%;

    bottom: 4%;
  }


  .invitation-flap-ornament {
    gap: 12px;
  }


  .invitation-flap-ornament > span {
    width: 32px;
  }


  .invitation-flap-diamond {
    width: 38px;

    height: 38px;
  }


  .invitation-flap-center-line {
    height: 70px;
  }

}


/* =========================================================
   VERY SMALL SCREENS
   الشاشات الصغيرة جدًا
========================================================= */

@media (max-width: 430px) {

  .loading-content {
    padding-left: 16px;
    padding-right: 16px;
  }


  .loading-frame {
    inset: 9px;
  }


  .corner {
    width: 25px;

    height: 25px;
  }


  .loading-reveal {
    margin-bottom: 24px;
  }


  .loading-reveal > div {
    gap: 9px;
  }


  .loading-reveal > div > span:first-child,
  .loading-reveal > div > span:last-child {
    width: 22px;
  }


  .loading-eyebrow {
    font-size: 8px;

    letter-spacing: 0.16em;
  }


  .monogram {
    width: 78px;

    height: 78px;
  }


  .monogram > div:first-of-type {
    inset: 6px;
  }


  .monogram > span:first-of-type {
    font-size: 26px;
  }


  .monogram > span:nth-of-type(2) {
    bottom: 12px;
  }


  .monogram > span:nth-of-type(3) {
    right: 18px;

    top: 12px;
  }


  .logo-reveal {
    margin-bottom: 24px;
  }


  .loading-name-groom,
  .loading-name-bride {
    font-size: clamp(3.45rem, 17vw, 4.4rem);

    line-height: 0.84;

    letter-spacing: -0.045em;
  }


  .names-reveal .ampersand {
    margin-top: 12px;

    margin-bottom: 12px;

    font-size: 1.6rem;
  }


  .loading-subtitle {
    max-width: 260px;

    font-size: 9px;

    line-height: 1.9;

    letter-spacing: 0.16em;
  }


  .loading-subtitle.font-arabic {
    font-size: 13px;

    line-height: 2;
  }


  .loading-bar-reveal {
    max-width: 220px;

    margin-top: 28px;
  }


  .loading-bar-reveal > div:first-child {
    margin-bottom: 7px;
  }


  .loading-label {
    max-width: 165px;

    font-size: 8px;

    line-height: 1.5;

    letter-spacing: 0.12em;
  }


  .loading-bar-reveal > div:first-child > span:last-child {
    font-size: 8px;
  }


  .bottom-decoration {
    bottom: 14px;
  }


  .bottom-decoration .gap-3 {
    gap: 8px;
  }


  .bottom-decoration span:first-child,
  .bottom-decoration span:last-child {
    width: 24px;
  }


  .central-ornament {
    width: 330px;

    height: 330px;

    opacity: 0.035;
  }


  .central-ornament
  .ornament-square:nth-child(2) {
    inset: 48px;
  }


  .central-ornament
  .ornament-square:nth-child(3) {
    inset: 96px;
  }


  .central-ornament
  > div:nth-child(4) {
    width: 215px;

    height: 215px;
  }


  .central-ornament
  > div:nth-child(5) {
    width: 275px;

    height: 275px;
  }


  .invitation-flap {
    width: 165vw;

    height: 78vh;

    min-height: 520px;
  }


  .invitation-flap-ornament {
    top: 45%;

    gap: 9px;
  }


  .invitation-flap-ornament > span {
    width: 24px;
  }


  .invitation-flap-diamond {
    width: 32px;

    height: 32px;
  }


  .invitation-flap-diamond::before {
    inset: 5px;
  }


  .invitation-flap-diamond span {
    width: 10px;

    height: 10px;
  }


  .invitation-flap-center-line {
    height: 55px;
  }


  .invitation-flap-dot {
    width: 5px;

    height: 5px;
  }

}


/* =========================================================
   EXTRA SMALL PHONES
   الهواتف الصغيرة جدًا مثل 320px
========================================================= */

@media (max-width: 350px) {

  .loading-content {
    padding-left: 12px;
    padding-right: 12px;
  }


  .loading-eyebrow {
    font-size: 7px;

    letter-spacing: 0.12em;
  }


  .loading-name-groom,
  .loading-name-bride {
    font-size: 3.25rem;
  }


  .names-reveal .ampersand {
    margin-top: 10px;

    margin-bottom: 10px;

    font-size: 1.4rem;
  }


  .loading-subtitle {
    max-width: 230px;

    font-size: 8px;

    letter-spacing: 0.1em;
  }


  .loading-subtitle.font-arabic {
    font-size: 12px;
  }


  .loading-bar-reveal {
    max-width: 195px;

    margin-top: 24px;
  }


  .loading-frame {
    inset: 7px;
  }


  .corner {
    width: 20px;

    height: 20px;
  }


  .monogram {
    width: 72px;

    height: 72px;
  }


  .monogram > span:first-of-type {
    font-size: 24px;
  }


  .bottom-decoration {
    bottom: 10px;
  }


  .central-ornament {
    width: 280px;

    height: 280px;
  }


  .central-ornament
  .ornament-square:nth-child(2) {
    inset: 40px;
  }


  .central-ornament
  .ornament-square:nth-child(3) {
    inset: 80px;
  }


  .central-ornament
  > div:nth-child(4) {
    width: 180px;

    height: 180px;
  }


  .central-ornament
  > div:nth-child(5) {
    width: 230px;

    height: 230px;
  }


  .invitation-flap {
    width: 175vw;

    height: 76vh;
  }

}


/* =========================================================
   REDUCED MOTION
   احترام إعدادات تقليل الحركة في الجهاز
========================================================= */

@media (prefers-reduced-motion: reduce) {

  .ambient-main,
  .ambient-top,
  .ambient-bottom,
  .ambient-side,
  .tunisian-pattern,
  .central-ornament,
  .logo-glow,
  .ampersand,
  .particle,
  .loading-progress,
  .loading-reveal,
  .logo-reveal,
  .names-reveal,
  .subtitle-reveal,
  .date-reveal,
  .loading-bar-reveal,
  .bottom-decoration,
  .bottom-diamond {
    animation: none !important;
  }


  .loading-progress {
    transform:
      scaleX(1);
  }


  .invitation-flap {
    transition:
      opacity 0.3s ease;
  }


  .loading-screen.is-opening
  .invitation-flap {
    transform:
      translateX(-50%)
      translateY(-108%);
  }

}

</style>