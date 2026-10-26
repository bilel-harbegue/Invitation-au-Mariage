<template>

  <footer
    ref="footerRef"
    class="relative overflow-hidden border-t border-[#9b753f]/15 bg-[#e7dfd1] px-6 py-9 text-[#705536] sm:py-10"
    :dir="language === 'ar' ? 'rtl' : 'ltr'"
  >

    <!-- ========================================================= -->
    <!-- Background Glow / توهج الخلفية -->
    <!-- ========================================================= -->

    <div
      class="pointer-events-none absolute left-1/2 top-0 h-24 w-72 -translate-x-1/2 rounded-full bg-[#d4af37]/[0.045] blur-3xl"
    ></div>


    <!-- ========================================================= -->
    <!-- Subtle Bottom Glow / توهج خفيف في الأسفل -->
    <!-- ========================================================= -->

    <div
      class="pointer-events-none absolute bottom-0 left-1/2 h-16 w-96 -translate-x-1/2 rounded-full bg-[#9b753f]/[0.025] blur-3xl"
    ></div>


    <!-- ========================================================= -->
    <!-- THANNA WATERMARK / العلامة المائية لثنّا -->
    <!-- ========================================================= -->

    <div
      class="footer-brand-watermark pointer-events-none absolute bottom-[-35px] left-[-25px] z-0 sm:bottom-[-55px] sm:left-[-45px]"
      :class="{
        'footer-watermark-visible': isVisible,
      }"
      aria-hidden="true"
    >

      <img
        :src="logof"
        alt=""
        class="h-auto w-[210px] object-contain sm:w-[270px] md:w-[320px]"
      />

    </div>


    <!-- ========================================================= -->
    <!-- Left Decoration / الزخرفة اليسرى -->
    <!-- ========================================================= -->

    <div
      class="footer-decoration footer-decoration-left pointer-events-none absolute left-[8%] top-1/2 h-2.5 w-2.5 -translate-y-1/2 rotate-45 border border-[#9b753f]/20"
      :class="{
        'footer-decoration-left-active': isVisible,
      }"
    ></div>


    <!-- ========================================================= -->
    <!-- Right Decoration / الزخرفة اليمنى -->
    <!-- ========================================================= -->

    <div
      class="footer-decoration footer-decoration-right pointer-events-none absolute right-[8%] top-1/2 h-2.5 w-2.5 -translate-y-1/2 rotate-45 border border-[#9b753f]/20"
      :class="{
        'footer-decoration-right-active': isVisible,
      }"
    ></div>


    <!-- ========================================================= -->
    <!-- Main Content / Contenu principal -->
    <!-- ========================================================= -->

    <div
      class="footer-content relative z-10 mx-auto flex max-w-5xl flex-col items-center justify-center gap-4"
      :class="{
        'footer-visible': isVisible,
      }"
    >

      <!-- ======================================================= -->
      <!-- Copyright / حقوق النشر -->
      <!-- ======================================================= -->
      <p
        class="footer-copyright max-w-full text-center text-[10px] tracking-[0.08em] text-[#705536]/75 sm:text-[11px]"
        :class="{
          'font-arabic tracking-normal': language === 'ar',
        }"
      >
        {{ current().copyright }}
      </p>

      <!-- Company Credit / حقوق تنفيذ المشروع -->
      <p
        class="text-center text-[10px] text-[#705536]/65 sm:text-[11px]"
        :class="{
          'font-arabic tracking-normal': language === 'ar',
        }"
      >
        {{ language === 'ar' ? 'تنفيذ' : 'Réalisé par' }}

        <a
          href="https://thanna.vercel.app"
          target="_blank"
          rel="noopener noreferrer"
          class="font-medium text-[#9b753f] underline decoration-[#9b753f]/30 underline-offset-4 transition-colors duration-300 hover:text-[#705536] hover:decoration-[#705536]"
          :aria-label="
            language === 'ar'
              ? 'زيارة موقع THANNA'
              : 'Visiter le site de THANNA'
          "
        >
          THANNA
        </a>
      </p>



      <!-- ======================================================= -->
      <!-- Back To Top / العودة إلى الأعلى -->
      <!-- ======================================================= -->

      <button
        type="button"
        class="footer-back-to-top group flex max-w-full items-center gap-2 text-center text-[9px] tracking-[0.12em] text-[#705536]/60 transition duration-300 hover:text-[#9b753f]"
        :class="{
          'font-arabic text-sm tracking-normal':
            language === 'ar',
        }"
        @click="scrollToTop"
      >

        <svg
          class="h-3.5 w-3.5 shrink-0 transition-transform duration-300 group-hover:-translate-y-1"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          aria-hidden="true"
        >

          <path
            d="M12 19V5"
            stroke-linecap="round"
          />

          <path
            d="M6 11l6-6 6 6"
            stroke-linecap="round"
            stroke-linejoin="round"
          />

        </svg>


        <span>

          {{ current().backToTop }}

        </span>

      </button>

    </div>


    <br><br>

  </footer>

</template>


<script setup>

import {
  ref,
  onMounted,
  onBeforeUnmount,
} from 'vue'


/* =========================================================
   LOGOS / LOGOS
========================================================= */

/*
 * Thanna Logo
 */
import logof from '../assets/images/logof.png'


/* =========================================================
   PROPS / PROPRIÉTÉS
========================================================= */

const props = defineProps({

  language: {

    type: String,

    default: 'fr',

  },

})


/* =========================================================
   FOOTER STATE / ÉTAT DU FOOTER
========================================================= */

const footerRef = ref(null)

const isVisible = ref(false)

let observer = null


/* =========================================================
   TRANSLATIONS / TRADUCTIONS
========================================================= */

const content = {

  fr: {

    copyright:
      '© 2027 THANNA — Tous droits réservés.',

    backToTop:
      'Retour en haut',

  },


  ar: {

    copyright:
      '© 2027 THANNA — جميع الحقوق محفوظة.',

    backToTop:
      'العودة إلى الأعلى',

  },

}


/* =========================================================
   CURRENT CONTENT / CONTENU ACTUEL
========================================================= */

const current = () => {

  return (
    content[props.language] ||
    content.fr
  )

}


/* =========================================================
   SCROLL TO TOP / RETOUR EN HAUT
========================================================= */

const scrollToTop = () => {

  window.scrollTo({

    top: 0,

    behavior: 'smooth',

  })

}


/* =========================================================
   INTERSECTION OBSERVER
   / OBSERVATION DE L'APPARITION
========================================================= */

onMounted(() => {

  /*
   * Animation du Footer lorsqu'il entre
   * dans la zone visible.
   *
   * العربية:
   * تشغيل حركة ظهور الـFooter عند دخوله الشاشة.
   */

  observer =
    new IntersectionObserver(

      (entries) => {

        entries.forEach((entry) => {

          isVisible.value =
            entry.isIntersecting

        })

      },

      {
        threshold: 0.2,
      },

    )


  if (footerRef.value) {

    observer.observe(
      footerRef.value
    )

  }

})


/* =========================================================
   CLEANUP / NETTOYAGE
========================================================= */

onBeforeUnmount(() => {

  if (observer) {

    observer.disconnect()

  }

})

</script>


<style scoped>


/* =========================================================
   Footer Reveal
   Animation d'apparition du Footer
========================================================= */

.footer-visible {

  animation:
    footerReveal
    0.9s
    ease-out
    forwards;

}


@keyframes footerReveal {

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


/* =========================================================
   THANNA WATERMARK
   العلامة المائية لثنّا
========================================================= */

.footer-brand-watermark {

  /*
   * مخفي في البداية حتى يبدأ Animation
   */

  opacity: 0;


  /*
   * بداية الحركة:
   * الشعار يأتي من الأسفل قليلًا
   */

  transform:
    translateY(25px)
    rotate(-8deg);


  transition:
    opacity 1.4s ease,
    transform 1.4s ease;


  /*
   * يجعل الشعار أكثر هدوءًا
   */

  filter:
    saturate(0.75)
    contrast(0.9);

}


/*
 * عند ظهور الـFooter
 */

.footer-watermark-visible {

  /*
   * شفافية العلامة المائية
   */

  opacity: 0.10;


  /*
   * الوضع النهائي
   */

  transform:
    translateY(0)
    rotate(-8deg);

}


/* =========================================================
   Decorative Diamonds
   Décorations en forme de losange
========================================================= */

.footer-decoration-left-active {

  animation:
    decorationLeft
    5s
    ease-in-out
    infinite;

}


.footer-decoration-right-active {

  animation:
    decorationRight
    5s
    ease-in-out
    infinite;

}


@keyframes decorationLeft {

  0%,
  100% {

    transform:
      translateY(-50%)
      rotate(45deg);

    opacity: 0.35;

  }


  50% {

    transform:
      translateY(-50%)
      translateY(-4px)
      rotate(90deg);

    opacity: 0.75;

  }

}


@keyframes decorationRight {

  0%,
  100% {

    transform:
      translateY(-50%)
      rotate(45deg);

    opacity: 0.35;

  }


  50% {

    transform:
      translateY(-50%)
      translateY(4px)
      rotate(90deg);

    opacity: 0.75;

  }

}


/* =========================================================
   MOBILE
   Responsive pour téléphone
========================================================= */

@media (max-width: 640px) {

  .footer-content {

    gap: 14px;

  }


  .footer-brand-watermark {

    /*
     * إبقاء الشعار داخل الشاشة
     * على الهاتف
     */

    left: -45px;

    bottom: -30px;

  }


  .footer-watermark-visible {

    /*
     * شفافية أقل على الهاتف
     */

    opacity: 0.075;

  }


  .footer-decoration {

    width: 8px;

    height: 8px;

  }


  .footer-decoration-left {

    left: 5%;

  }


  .footer-decoration-right {

    right: 5%;

  }


  .footer-copyright {

    max-width: 280px;

    line-height: 1.7;

  }


  .footer-back-to-top {

    min-height: 32px;

    padding-left: 6px;

    padding-right: 6px;

    line-height: 1.6;

  }

}


/* =========================================================
   VERY SMALL SCREENS
   الهواتف الصغيرة جدًا
========================================================= */

@media (max-width: 430px) {

  footer {

    padding-left: 16px;

    padding-right: 16px;

    padding-top: 28px;

    padding-bottom: 28px;

  }


  .footer-content {

    gap: 12px;

  }


  .footer-copyright {

    max-width: 240px;

    font-size: 9px;

    line-height: 1.8;

    letter-spacing: 0.05em;

  }


  .footer-back-to-top {

    gap: 6px;

    font-size: 8px;

    letter-spacing: 0.08em;

  }


  .footer-back-to-top.font-arabic {

    font-size: 12px;

    line-height: 1.8;

  }


  .footer-back-to-top svg {

    width: 13px;

    height: 13px;

  }


  .footer-brand-watermark {

    left: -55px;

    bottom: -28px;

  }


  .footer-brand-watermark img {

    width: 185px;

  }


  .footer-decoration-left {

    left: 3%;

  }


  .footer-decoration-right {

    right: 3%;

  }


  footer > br {

    display: none;

  }

}


/* =========================================================
   EXTRA SMALL SCREENS
   الشاشات الصغيرة جدًا مثل 320px
========================================================= */

@media (max-width: 350px) {

  footer {

    padding-left: 12px;

    padding-right: 12px;

    padding-top: 25px;

    padding-bottom: 25px;

  }


  .footer-copyright {

    max-width: 215px;

    font-size: 8px;

    line-height: 1.8;

  }


  .footer-back-to-top {

    font-size: 7px;

    gap: 5px;

  }


  .footer-back-to-top.font-arabic {

    font-size: 11px;

  }


  .footer-brand-watermark {

    left: -65px;

    bottom: -25px;

  }


  .footer-brand-watermark img {

    width: 165px;

  }


  .footer-decoration-left {

    left: 2%;

  }


  .footer-decoration-right {

    right: 2%;

  }

}


/* =========================================================
   REDUCED MOTION
   Réduction des animations
========================================================= */

@media (prefers-reduced-motion: reduce) {

  .footer-visible,
  .footer-decoration-left-active,
  .footer-decoration-right-active {

    animation:
      none !important;

  }


  .footer-brand-watermark {

    transition:
      none !important;

  }

}

</style>