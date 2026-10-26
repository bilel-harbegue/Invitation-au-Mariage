<template>
  <main class="w-full">

    <!-- ========================================================= -->
    <!-- LOADING / ÉCRAN DE CHARGEMENT -->
    <!-- ========================================================= -->

    <Transition name="loader">
      <LoadingScreen
        v-if="isLoading"
        :language="language"
        @finished="finishLoading"
      />
    </Transition>


    <!-- ========================================================= -->
    <!-- GLOBAL LANGUAGE SWITCHER / SÉLECTEUR DE LANGUE -->
    <!-- ========================================================= -->

    <Transition name="language-switcher">
      <div
        v-if="showLanguageSwitcher && !isLoading"
        class="global-language-switcher"
        dir="ltr"
      >

        <!--
          مؤشر ذهبي متحرك بين اللغتين.
          Indicateur doré animé entre les deux langues.
        -->
        <span
          class="language-switch-indicator"
          :class="{
            'language-switch-indicator-ar':
              language === 'ar',
          }"
          aria-hidden="true"
        ></span>


        <!-- Français -->
        <button
          type="button"
          class="language-button"
          :class="{
            'language-button-active':
              language === 'fr',
          }"
          :aria-pressed="language === 'fr'"
          @click="changeLanguage('fr')"
        >
          FR
        </button>


        <!-- العربية -->
        <button
          type="button"
          class="language-button language-button-arabic"
          :class="{
            'language-button-active':
              language === 'ar',
          }"
          :aria-pressed="language === 'ar'"
          @click="changeLanguage('ar')"
        >
          AR
        </button>

      </div>
    </Transition>


    <!-- ========================================================= -->
    <!-- GLOBAL SECTION NAVIGATION / NAVBAR DES SECTIONS -->
    <!-- PC UNIQUEMENT / DESKTOP ONLY -->
    <!-- ========================================================= -->

    <Transition name="section-navigation">
      <nav
        v-if="showLanguageSwitcher && !isLoading"
        class="section-navigation"
        :dir="language === 'ar' ? 'rtl' : 'ltr'"
        :aria-label="
          language === 'ar'
            ? 'التنقل بين أقسام الدعوة'
            : 'Navigation entre les sections'
        "
      >

        <!-- ===================================================== -->
        <!-- 1. ACCUEIL / الرئيسية -->
        <!-- ===================================================== -->

        <button
          type="button"
          class="navigation-item"
          :class="{
            'nav-active':
              activeSection === 'hero',
          }"
          @click="scrollToSection('hero')"
        >
          {{ navigation.home }}
        </button>


        <span
          class="navigation-separator"
          aria-hidden="true"
        ></span>


        <!-- ===================================================== -->
        <!-- 2. INVITATION / الدعوة -->
        <!-- ===================================================== -->

        <button
          type="button"
          class="navigation-item"
          :class="{
            'nav-active':
              activeSection === 'invitation',
          }"
          @click="scrollToSection('invitation')"
        >
          {{ navigation.invitation }}
        </button>


        <span
          class="navigation-separator"
          aria-hidden="true"
        ></span>


        <!-- ===================================================== -->
        <!-- 3. VERSETS & SAGESSE / آيات وأحاديث -->
        <!-- ===================================================== -->

        <button
          type="button"
          class="navigation-item"
          :class="{
            'nav-active':
              activeSection === 'islamic-marriage',
          }"
          @click="scrollToSection('islamic-marriage')"
        >
          {{ navigation.islamic }}
        </button>


        <span
          class="navigation-separator"
          aria-hidden="true"
        ></span>


        <!-- ===================================================== -->
        <!-- 4. CÉRÉMONIE / الحفل -->
        <!-- ===================================================== -->

        <button
          type="button"
          class="navigation-item"
          :class="{
            'nav-active':
              activeSection === 'wedding-events',
          }"
          @click="scrollToSection('wedding-events')"
        >
          {{ navigation.events }}
        </button>


        <span
          class="navigation-separator"
          aria-hidden="true"
        ></span>


        <!-- ===================================================== -->
        <!-- 5. LIEU / المكان -->
        <!-- ===================================================== -->

        <button
          type="button"
          class="navigation-item"
          :class="{
            'nav-active':
              activeSection === 'location',
          }"
          @click="scrollToSection('location')"
        >
          {{ navigation.location }}
        </button>

      </nav>
    </Transition>


    <!-- ========================================================= -->
    <!-- WEBSITE / SITE PRINCIPAL -->
    <!-- ========================================================= -->

    <div
      v-show="!isLoading"
      class="w-full"
    >

      <!-- ======================================================= -->
      <!-- HERO / ACCUEIL -->
      <!-- ======================================================= -->

      <Hero
        :language="language"
        @change-language="changeLanguage"
      />


      <!-- ======================================================= -->
      <!-- INVITATION / الدعوة -->
      <!-- ======================================================= -->

      <Invitation
        :language="language"
      />


      <!-- ======================================================= -->
      <!-- ISLAMIC MARRIAGE / VERSETS & SAGESSE -->
      <!-- آيات وأحاديث -->
      <!-- ======================================================= -->

      <IslamicMarriage
        :language="language"
      />


      <!-- ======================================================= -->
      <!-- EVENTS / CÉRÉMONIE -->
      <!-- الحفل -->
      <!-- ======================================================= -->

      <WeddingEvents
        :language="language"
      />


      <!-- ======================================================= -->
      <!-- LOCATION / LIEU -->
      <!-- المكان -->
      <!-- ======================================================= -->

      <Location
        :language="language"
      />


      <!-- ======================================================= -->
      <!-- FOOTER / PIED DE PAGE -->
      <!-- ======================================================= -->

      <Footer
        :language="language"
      />

    </div>


    <!-- ========================================================= -->
    <!-- BACK TO TOP / RETOUR EN HAUT -->
    <!-- ========================================================= -->

    <Transition name="back-to-top">
      <button
        v-if="showBackToTop && !isLoading"
        type="button"
        class="back-to-top"
        :aria-label="
          language === 'ar'
            ? 'العودة إلى الأعلى'
            : 'Retour en haut'
        "
        @click="scrollToTop"
      >

        <svg
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          class="h-4 w-4"
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

      </button>
    </Transition>

  </main>
</template>


<script setup>
import {
  ref,
  watch,
  computed,
  onMounted,
  onUnmounted,
} from 'vue'

import LoadingScreen from './components/LoadingScreen.vue'
import Hero from './components/Hero.vue'
import Invitation from './components/Invitation.vue'
import IslamicMarriage from './components/IslamicMarriage.vue'
import WeddingEvents from './components/WeddingEvents.vue'
import Location from './components/Location.vue'
import Footer from './components/Footer.vue'


/* =========================================================
   LOADING / CHARGEMENT
   ========================================================= */

const isLoading = ref(true)


/*
 * LoadingScreen.vue contrôle la fin du chargement.
 *
 * العربية:
 * شاشة التحميل هي المسؤولة عن تحديد نهاية التحميل.
 */
const finishLoading = () => {
  isLoading.value = false

  unlockPage()

  /*
   * تحديث حالة الـNavbar مباشرة بعد انتهاء التحميل.
   * Mise à jour immédiate de la navigation après le chargement.
   */
  requestAnimationFrame(() => {
    updateScrollState()
  })
}


/* =========================================================
   LANGUAGE / LANGUE
   ========================================================= */

/*
 * العربية هي اللغة الافتراضية عند أول زيارة.
 *
 * إذا كانت هناك لغة محفوظة سابقاً، يتم استعمالها.
 *
 * La préférence déjà enregistrée par l'utilisateur
 * reste prioritaire.
 */
const language = ref(
  localStorage.getItem('wedding-language') || 'ar'
)


/*
 * Changer la langue globale du site.
 *
 * العربية:
 * تغيير اللغة على مستوى الموقع بالكامل.
 */
const changeLanguage = (lang) => {
  if (lang !== 'fr' && lang !== 'ar') {
    return
  }

  if (language.value === lang) {
    return
  }

  language.value = lang

  /*
   * Notification globale pour les composants qui
   * écoutent le changement de langue.
   *
   * العربية:
   * إرسال حدث عام للمكونات التي تراقب تغيير اللغة.
   */
  window.dispatchEvent(
    new CustomEvent(
      'wedding-language-change',
      {
        detail: {
          language: lang,
        },
      }
    )
  )
}


/* =========================================================
   GLOBAL LANGUAGE SWITCHER
   / SÉLECTEUR GLOBAL DE LANGUE
   ========================================================= */

const showLanguageSwitcher = ref(false)


/* =========================================================
   BACK TO TOP / RETOUR EN HAUT
   ========================================================= */

const showBackToTop = ref(false)


/* =========================================================
   ACTIVE SECTION / SECTION ACTIVE
   ========================================================= */

const activeSection = ref('hero')


/*
 * أثناء الضغط على Navbar، نحدد القسم مباشرة.
 *
 * العربية:
 * هذا يمنع بقاء العنصر القديم محدداً أثناء
 * الـsmooth scroll.
 */
const isProgrammaticScrolling = ref(false)


/* =========================================================
   NAVIGATION TRANSLATIONS
   / TRADUCTIONS DE LA NAVIGATION
   ========================================================= */

const navigation = computed(() => {

  if (language.value === 'ar') {

    return {
      home: 'الرئيسية',
      invitation: 'الدعوة',
      islamic: 'آيات وأحاديث',
      events: 'الحفل',
      location: 'المكان',
    }

  }

  return {
    home: 'ACCUEIL',
    invitation: 'INVITATION',
    islamic: 'VERSETS & SAGESSE',
    events: 'CÉRÉMONIE',
    location: 'LIEU',
  }

})


/* =========================================================
   SECTIONS
   / SECTIONS DU SITE
   ========================================================= */

/*
 * ترتيب الأقسام مطابق تماماً لترتيب الـNavbar:
 *
 * 1. Hero
 * 2. Invitation
 * 3. IslamicMarriage
 * 4. WeddingEvents
 * 5. Location
 */
const sections = [
  'hero',
  'invitation',
  'islamic-marriage',
  'wedding-events',
  'location',
]


/* =========================================================
   ACTIVE SECTION DETECTION
   / DÉTECTION DE LA SECTION ACTIVE
   ========================================================= */

/*
 * تحديد القسم الموجود فعلياً داخل الشاشة.
 *
 * العربية:
 * نستعمل نقطة داخل الشاشة بدل الاعتماد فقط على offsetTop.
 * هذا يجعل الـactive state أكثر دقة أثناء التمرير.
 */
const updateActiveSection = () => {

  const viewportHeight =
    window.innerHeight

  /*
   * نقطة التحديد موجودة تقريباً في الجزء العلوي
   * من منتصف الشاشة.
   */
  const detectionLine =
    viewportHeight * 0.38

  let currentSection =
    'hero'


  /*
   * نبحث عن القسم الذي تمر منه نقطة التحديد.
   */
  for (const id of sections) {

    const section =
      document.getElementById(id)

    if (!section) {
      continue
    }

    const rect =
      section.getBoundingClientRect()

    if (
      rect.top <= detectionLine &&
      rect.bottom > detectionLine
    ) {
      currentSection = id
      break
    }

  }


  /*
   * في حالة وجود مسافة بين قسمين،
   * نحدد آخر قسم بدأ قبل خط التحديد.
   */
  if (currentSection === 'hero') {

    let closestSection =
      'hero'

    let closestDistance =
      Infinity


    for (const id of sections) {

      const section =
        document.getElementById(id)

      if (!section) {
        continue
      }

      const rect =
        section.getBoundingClientRect()


      if (rect.top <= detectionLine) {

        const distance =
          Math.abs(
            detectionLine -
            rect.top
          )


        if (
          distance <
          closestDistance
        ) {

          closestDistance =
            distance

          closestSection =
            id

        }

      }

    }


    currentSection =
      closestSection

  }


  activeSection.value =
    currentSection
}


/* =========================================================
   SCROLL HANDLER / GESTION DU SCROLL
   ========================================================= */

const updateScrollState = () => {

  const scrollPosition =
    window.scrollY


  /*
   * Afficher les contrôles après un léger défilement.
   *
   * العربية:
   * إظهار عناصر التحكم بعد بدء التمرير.
   */
  showLanguageSwitcher.value =
    scrollPosition > 10


  /*
   * Afficher le bouton "Retour en haut".
   *
   * العربية:
   * إظهار زر العودة للأعلى بعد النزول قليلاً.
   */
  showBackToTop.value =
    scrollPosition >
    window.innerHeight * 0.7


  /*
   * تحديث الصفحة النشطة.
   * Mise à jour de la section active.
   */
  updateActiveSection()
}


/* =========================================================
   SCROLL TO SECTION
   / ALLER À UNE SECTION
   ========================================================= */

const scrollToSection = (id) => {

  const section =
    document.getElementById(id)

  if (!section) {
    return
  }


  /*
   * تحديد العنصر مباشرة قبل بدء الحركة.
   *
   * العربية:
   * هذا يجعل العنصر المحدد يظهر فوراً أثناء الانتقال.
   */
  activeSection.value =
    id


  isProgrammaticScrolling.value =
    true


  section.scrollIntoView({
    behavior: 'smooth',
    block: 'start',
  })


  /*
   * بعد انتهاء الحركة نعيد الحساب الحقيقي
   * للتأكد من أن القسم النشط صحيح.
   */
  window.setTimeout(() => {

    isProgrammaticScrolling.value =
      false

    updateScrollState()

  }, 750)

}


/* =========================================================
   SCROLL TO TOP / RETOUR EN HAUT
   ========================================================= */

const scrollToTop = () => {

  activeSection.value =
    'hero'


  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })


  window.setTimeout(() => {
    updateScrollState()
  }, 750)

}


/* =========================================================
   IMAGE LOADING / CHARGEMENT DES IMAGES
   ========================================================= */

const waitForImage = (img) => {

  return new Promise((resolve) => {

    if (img.complete) {
      resolve()
      return
    }


    img.addEventListener(
      'load',
      resolve,
      {
        once: true,
      }
    )


    img.addEventListener(
      'error',
      resolve,
      {
        once: true,
      }
    )

  })

}


const waitForImages = async () => {

  const images =
    Array.from(
      document.images
    )


  await Promise.all(
    images.map(waitForImage)
  )

}


/* =========================================================
   FONTS / POLICES
   ========================================================= */

const waitForFonts = async () => {

  if (
    document.fonts &&
    document.fonts.ready
  ) {

    try {

      await document.fonts.ready

    } catch {

      /*
       * Ignore les erreurs de chargement
       * des polices.
       */

    }

  }

}


/* =========================================================
   WINDOW LOAD / CHARGEMENT DE LA FENÊTRE
   ========================================================= */

const waitForWindowLoad = () => {

  return new Promise((resolve) => {

    if (
      document.readyState ===
      'complete'
    ) {

      resolve()
      return

    }


    window.addEventListener(
      'load',
      resolve,
      {
        once: true,
      }
    )

  })

}


/* =========================================================
   PRELOAD ICONS / PRÉCHARGEMENT DES ICÔNES
   ========================================================= */

const preloadIcons = async () => {

  const icons = [

    'https://unpkg.com/lucide-static@latest/icons/heart.svg',

    'https://unpkg.com/lucide-static@latest/icons/sparkles.svg',

    'https://unpkg.com/lucide-static@latest/icons/arrow-down.svg',

    'https://unpkg.com/lucide-static@latest/icons/calendar-heart.svg',

    'https://unpkg.com/lucide-static@latest/icons/heart-handshake.svg',

    'https://unpkg.com/lucide-static@latest/icons/champagne.svg',

    'https://unpkg.com/lucide-static@latest/icons/music-2.svg',

    'https://unpkg.com/lucide-static@latest/icons/map-pin.svg',

  ]


  await Promise.all(

    icons.map((src) => {

      return new Promise((resolve) => {

        const img =
          new Image()


        img.onload =
          resolve

        img.onerror =
          resolve

        img.src =
          src

      })

    })

  )

}


/* =========================================================
   PRELOAD EVERYTHING / PRÉCHARGEMENT GLOBAL
   ========================================================= */

const preloadEverything = async () => {

  await Promise.all([

    waitForWindowLoad(),

    waitForImages(),

    waitForFonts(),

    preloadIcons(),

  ])

}


/* =========================================================
   PAGE LOCK / BLOQUER LE SCROLL
   ========================================================= */

const lockPage = () => {

  document.documentElement.classList.add(
    'page-scroll-locked'
  )

  document.body.classList.add(
    'page-scroll-locked'
  )

}


const unlockPage = () => {

  document.documentElement.classList.remove(
    'page-scroll-locked'
  )

  document.body.classList.remove(
    'page-scroll-locked'
  )

}


/* =========================================================
   START / INITIALISATION
   ========================================================= */

onMounted(async () => {

  /*
   * LoadingScreen.vue gère :
   *
   * 1. Le chargement
   * 2. L'ouverture de l'enveloppe
   * 3. La durée d'affichage
   * 4. emit('finished')
   * 5. finishLoading()
   *
   * العربية:
   * شاشة التحميل هي التي تتحكم في العملية بالكامل.
   */

  lockPage()


  /*
   * Écoute du scroll.
   *
   * العربية:
   * مراقبة التمرير لتحديث الصفحة النشطة.
   */
  window.addEventListener(
    'scroll',
    updateScrollState,
    {
      passive: true,
    }
  )


  /*
   * Écoute du redimensionnement.
   *
   * العربية:
   * إعادة حساب الصفحة النشطة عند تغيير حجم الشاشة.
   */
  window.addEventListener(
    'resize',
    updateScrollState,
    {
      passive: true,
    }
  )


  /*
   * Initialisation après affichage du DOM.
   */
  requestAnimationFrame(() => {
    updateScrollState()
  })


  try {

    await preloadEverything()

  } catch {

    /*
     * Le site continue normalement
     * même si une ressource échoue.
     */

  }

})


/* =========================================================
   LANGUAGE WATCHER
   / SURVEILLANCE DE LA LANGUE
   ========================================================= */

watch(

  language,

  (lang) => {

    /*
     * Sauvegarder la langue choisie.
     */
    localStorage.setItem(
      'wedding-language',
      lang
    )


    /*
     * Mettre à jour la langue HTML.
     */
    document.documentElement.lang =
      lang


    /*
     * Mettre à jour la direction globale.
     */
    document.documentElement.dir =
      lang === 'ar'
        ? 'rtl'
        : 'ltr'

  },

  {
    immediate: true,
  }

)


/* =========================================================
   CLEANUP / NETTOYAGE
   ========================================================= */

onUnmounted(() => {

  unlockPage()


  window.removeEventListener(
    'scroll',
    updateScrollState
  )


  window.removeEventListener(
    'resize',
    updateScrollState
  )


  document.documentElement.classList.remove(
    'page-scroll-locked'
  )

  document.body.classList.remove(
    'page-scroll-locked'
  )

})
</script>


<style>

/* ===================================================== */
/* GLOBAL / GLOBAL */
/* ===================================================== */

html {
  scroll-behavior: smooth;
}


body {
  margin: 0;

  overflow-x: hidden;

  background: #e7dfd1;
}


* {
  box-sizing: border-box;
}


/* ===================================================== */
/* PAGE LOCK / BLOCAGE DU SCROLL */
/* ===================================================== */

html.page-scroll-locked,
body.page-scroll-locked {
  overflow: hidden !important;

  height: 100% !important;
}


/* ===================================================== */
/* GLOBAL LANGUAGE SWITCHER */
/* SÉLECTEUR GLOBAL DE LANGUE */
/* ===================================================== */

.global-language-switcher {
  position: fixed;

  top: 24px;
  right: 28px;

  z-index: 9999;

  /*
   * Grid avec deux colonnes identiques.
   *
   * العربية:
   * كل زر له نفس العرض حتى يتحرك المؤشر
   * الذهبي بدقة بين اللغتين.
   */
  display: grid;

  grid-template-columns:
    56px 56px;

  align-items: center;

  gap: 4px;

  padding: 4px;

  border: 1px solid
    rgba(155, 117, 63, 0.32);

  border-radius: 999px;

  background:
    rgba(255, 253, 248, 0.82);

  box-shadow:
    0 12px 35px
    rgba(91, 65, 35, 0.12);

  backdrop-filter:
    blur(16px);

  isolation: isolate;

  transition:
    box-shadow 0.4s ease,
    transform 0.4s ease;
}


.global-language-switcher:hover {
  transform:
    translateY(-2px);

  box-shadow:
    0 16px 40px
    rgba(91, 65, 35, 0.16);
}


/* ===================================================== */
/* LANGUAGE SWITCH INDICATOR */
/* INDICATEUR DU SWITCH */
/* ===================================================== */

.language-switch-indicator {
  position: absolute;

  top: 4px;
  left: 4px;

  z-index: -1;

  width: 56px;
  height: 32px;

  border-radius: 999px;

  background: #8e6937;

  box-shadow:
    0 5px 15px
    rgba(120, 80, 30, 0.18);

  /*
   * حركة ناعمة مثل Switch حقيقي.
   *
   * Animation fluide comme un vrai switch.
   */
  transition:
    transform 0.55s
    cubic-bezier(
      0.22,
      1,
      0.36,
      1
    );
}


/*
 * العربية:
 * ننتقل بعرض الزر + المسافة بين الزرين.
 */
.language-switch-indicator-ar {
  transform:
    translateX(
      calc(100% + 4px)
    );
}


/* ===================================================== */
/* LANGUAGE BUTTON / BOUTON DE LANGUE */
/* ===================================================== */

.language-button {
  position: relative;

  z-index: 1;

  width: 56px;
  height: 32px;

  border: 0;

  border-radius: 999px;

  background: transparent;

  padding: 0;

  cursor: pointer;

  color: #705b48;

  font-size: 9px;

  font-weight: 700;

  letter-spacing: 0.12em;

  line-height: 1;

  transition:
    color 0.4s ease,
    transform 0.3s ease;
}


.language-button:hover {
  color: #8e6937;

  transform:
    translateY(-1px);
}


/* Arabic language button */

.language-button-arabic {
  font-family:
    "Noto Sans Arabic",
    "Tahoma",
    sans-serif;

  font-size: 10px;

  letter-spacing: 0;
}


/* Active language / اللغة النشطة */

.language-button-active {
  color: white !important;
}


/* ===================================================== */
/* SECTION NAVIGATION / NAVBAR */
/* PC UNIQUEMENT */
/* ===================================================== */

.section-navigation {
  position: fixed;

  left: 50%;
  bottom: 22px;

  z-index: 9998;

  display: flex;

  align-items: center;

  justify-content: center;

  gap: 12px;

  transform:
    translateX(-50%);

  padding: 8px 15px;

  border: 1px solid
    rgba(155, 117, 63, 0.22);

  border-radius: 999px;

  background:
    rgba(255, 253, 248, 0.72);

  box-shadow:
    0 12px 35px
    rgba(91, 65, 35, 0.09);

  backdrop-filter:
    blur(18px);

  white-space: nowrap;
}


/* ===================================================== */
/* NAVIGATION ITEM / ÉLÉMENT DE NAVIGATION */
/* ===================================================== */

.navigation-item {
  position: relative;

  border: 0;

  padding: 6px 9px;

  border-radius: 999px;

  cursor: pointer;

  background: transparent;

  color: #806b56;

  font-family:
    "Cormorant Garamond",
    Georgia,
    serif;

  font-size: 11px;

  font-weight: 600;

  letter-spacing: 0.16em;

  line-height: 1;

  transition:
    color 0.35s ease,
    background 0.35s ease,
    box-shadow 0.35s ease,
    transform 0.35s ease;
}


/* Hover / Survol */

.navigation-item:hover {
  color: #8e6937;

  transform:
    translateY(-1px);
}


/* ===================================================== */
/* ACTIVE NAVIGATION / SECTION ACTIVE */
/* ===================================================== */

.navigation-item.nav-active {
  color: #60482d;

  background:
    rgba(142, 105, 55, 0.11);

  box-shadow:
    inset 0 0 0 1px
    rgba(142, 105, 55, 0.08),

    0 3px 10px
    rgba(91, 65, 35, 0.06);

  font-weight: 700;

  text-shadow:
    0 0 10px
    rgba(142, 105, 55, 0.12);
}


/* Arabic navigation */

[dir="rtl"] .navigation-item {
  font-family:
    "Noto Sans Arabic",
    "Tahoma",
    sans-serif;

  font-size: 11px;

  letter-spacing: 0;

  line-height: 1.4;
}


[dir="rtl"] .navigation-item.nav-active {
  font-weight: 700;
}


/* ===================================================== */
/* NAVIGATION SEPARATOR / SÉPARATEUR */
/* ===================================================== */

.navigation-separator {
  width: 3px;

  height: 3px;

  flex-shrink: 0;

  border-radius: 999px;

  background:
    rgba(155, 117, 63, 0.38);
}


/* ===================================================== */
/* BACK TO TOP / RETOUR EN HAUT */
/* ===================================================== */

.back-to-top {
  position: fixed;

  right: 28px;
  bottom: 25px;

  z-index: 9999;

  display: flex;

  align-items: center;
  justify-content: center;

  width: 42px;
  height: 42px;

  border: 1px solid
    rgba(155, 117, 63, 0.35);

  border-radius: 999px;

  cursor: pointer;

  color: #8e6937;

  background:
    rgba(255, 253, 248, 0.78);

  box-shadow:
    0 10px 30px
    rgba(91, 65, 35, 0.12);

  backdrop-filter:
    blur(16px);

  transition:
    transform 0.35s ease,
    background 0.35s ease,
    box-shadow 0.35s ease;
}


.back-to-top:hover {
  transform:
    translateY(-4px);

  background:
    rgba(255, 253, 248, 0.96);

  box-shadow:
    0 14px 35px
    rgba(91, 65, 35, 0.17);
}


/* ===================================================== */
/* LANGUAGE TRANSITION / TRANSITION DE LANGUE */
/* ===================================================== */

.language-switcher-enter-active,
.language-switcher-leave-active {
  transition:
    opacity 0.45s ease,
    transform 0.45s
      cubic-bezier(
        0.22,
        1,
        0.36,
        1
      );
}


.language-switcher-enter-from,
.language-switcher-leave-to {
  opacity: 0;

  transform:
    translateY(-15px)
    scale(0.94);
}


/* ===================================================== */
/* SECTION NAVIGATION TRANSITION */
/* ===================================================== */

.section-navigation-enter-active,
.section-navigation-leave-active {
  transition:
    opacity 0.45s ease,
    transform 0.45s
      cubic-bezier(
        0.22,
        1,
        0.36,
        1
      );
}


.section-navigation-enter-from,
.section-navigation-leave-to {
  opacity: 0;

  transform:
    translateX(-50%)
    translateY(15px)
    scale(0.96);
}


/* ===================================================== */
/* BACK TO TOP TRANSITION */
/* ===================================================== */

.back-to-top-enter-active,
.back-to-top-leave-active {
  transition:
    opacity 0.35s ease,
    transform 0.35s
      cubic-bezier(
        0.22,
        1,
        0.36,
        1
      );
}


.back-to-top-enter-from,
.back-to-top-leave-to {
  opacity: 0;

  transform:
    translateY(12px)
    scale(0.85);
}


/* ===================================================== */
/* LOADING TRANSITION / TRANSITION DU LOADER */
/* ===================================================== */

.loader-leave-active {
  transition:
    opacity 1s ease,
    transform 1.2s
      cubic-bezier(
        0.16,
        1,
        0.3,
        1
      );
}


.loader-leave-to {
  opacity: 0;

  transform:
    scale(1.06);
}


/* ===================================================== */
/* TABLET / MOBILE — HIDE NAVBAR */
/* ===================================================== */

@media (max-width: 900px) {

  /*
   * العربية:
   * الـNavbar الخاص بالأقسام يظهر فقط على PC.
   *
   * Français:
   * La navigation des sections est visible
   * uniquement sur les écrans PC.
   *
   * مهم:
   * Language Switcher et Back To Top restent visibles.
   */

  .section-navigation {
    display: none !important;
  }

}


/* ===================================================== */
/* MOBILE / RESPONSIVE */
/* ===================================================== */

@media (max-width: 640px) {

  /* =================================================== */
  /* Language switcher / Sélecteur de langue */
  /* =================================================== */

  .global-language-switcher {

    top: 16px;

    right: 16px;

    grid-template-columns:
      48px 48px;
  }


  .language-button {

    width: 48px;

    height: 30px;

    font-size: 8px;
  }


  .language-button-arabic {

    font-size: 9px;
  }


  .language-switch-indicator {

    width: 48px;

    height: 30px;
  }


  /* =================================================== */
  /* Back to top / Retour en haut */
  /* =================================================== */

  .back-to-top {

    right: 16px;

    bottom: 18px;

    width: 40px;

    height: 40px;
  }

}


/* ===================================================== */
/* VERY SMALL PHONES */
/* ===================================================== */

@media (max-width: 380px) {

  .global-language-switcher {

    top: 12px;

    right: 12px;

    grid-template-columns:
      44px 44px;

    gap: 3px;

    padding: 3px;
  }


  .language-button {

    width: 44px;

    height: 28px;
  }


  .language-switch-indicator {

    top: 3px;

    left: 3px;

    width: 44px;

    height: 28px;
  }

}


/* ===================================================== */
/* REDUCED MOTION / RÉDUCTION DES ANIMATIONS */
/* ===================================================== */

@media (prefers-reduced-motion: reduce) {

  html {
    scroll-behavior: auto;
  }


  .global-language-switcher,
  .section-navigation,
  .back-to-top,
  .language-switch-indicator {

    transition: none;
  }

}
</style>