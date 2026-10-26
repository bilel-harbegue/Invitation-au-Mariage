<template>
  <section
    id="islamic-marriage"
    ref="sectionRef"
    class="islamic-marriage relative isolate min-h-screen overflow-hidden bg-[#e7dfd1] text-[#30241c]"
    :class="{ 'islamic-active': isVisible }"
    :dir="language === 'ar' ? 'rtl' : 'ltr'"
  >
    <!-- =========================================================
         الخلفية
         Français : Arrière-plan
    ========================================================== -->

    <div class="absolute inset-0 bg-[#e7dfd1]"></div>

    <!-- الإضاءات المحيطة / Lumières d’ambiance -->
    <div class="islamic-glow glow-one"></div>
    <div class="islamic-glow glow-two"></div>
    <div class="islamic-glow glow-three"></div>

    <!-- النمط الهندسي الدائري الرئيسي / Motif géométrique circulaire principal -->
    <div class="islamic-circle-pattern"></div>

    <!-- النمط الدائري الثانوي / Motif circulaire secondaire -->
    <div class="islamic-circle-grid"></div>

    <!-- =========================================================
         الزخارف الدائرية العائمة
         Français : Ornements circulaires flottants
    ========================================================== -->

    <!-- الدوائر العائمة / Cercles flottants -->
    <div class="floating-circle circle-one"></div>
    <div class="floating-circle circle-two"></div>
    <div class="floating-circle circle-three"></div>
    <div class="floating-circle circle-four"></div>

    <!-- النقاط العائمة / Points flottants -->
    <div class="floating-dot dot-one"></div>
    <div class="floating-dot dot-two"></div>
    <div class="floating-dot dot-three"></div>
    <div class="floating-dot dot-four"></div>

    <!-- =========================================================
         الإطار الخارجي
         Français : Cadre extérieur
    ========================================================== -->

    <div
      class="islamic-frame pointer-events-none absolute inset-[22px] border border-[#241b15]/[0.12]"
      aria-hidden="true"
    >
      <div class="frame-corner frame-tl"></div>
      <div class="frame-corner frame-tr"></div>
      <div class="frame-corner frame-bl"></div>
      <div class="frame-corner frame-br"></div>
    </div>

    <!-- =========================================================
         المحتوى الرئيسي
         Français : Contenu principal
    ========================================================== -->

    <div
      class="relative z-20 mx-auto w-full max-w-5xl px-6 py-24 sm:px-8 lg:px-10 lg:py-28"
    >

      <!-- =======================================================
           رأس الصفحة
           Français : En-tête de la section
      ======================================================== -->

      <header class="islamic-header mx-auto max-w-3xl text-center">

        <!-- العنوان الصغير / Petit titre -->

        <div
          class="islamic-label flex items-center justify-center gap-[13px]"
        >
          <span></span>

          <span>
            {{ current().eyebrow }}
          </span>

          <span></span>
        </div>

        <!-- العنوان الرئيسي / Titre principal -->

        <h2 class="islamic-title mt-[18px]">
          {{ current().title }}
        </h2>

        <!-- الوصف / Description -->

        <p class="islamic-description mx-auto mt-[22px] max-w-[680px]">
          {{ current().intro }}
        </p>

        <!-- الفاصل / Séparateur -->

        <div
          class="islamic-divider mt-[30px] flex items-center justify-center gap-3"
        >
          <span></span>
          <div></div>
          <span></span>
        </div>
      </header>

      <!-- =======================================================
           البطاقة الرئيسية للآية القرآنية
           Français : Carte principale du verset coranique
      ======================================================== -->

      <article
        class="main-card reveal-card premium-card relative mx-auto mt-[58px] max-w-4xl overflow-hidden rounded-[28px] border border-[#241b15]/[0.16] bg-[#f3ede2]/95 px-7 py-12 shadow-[0_25px_65px_rgba(70,48,28,0.08),inset_0_0_50px_rgba(142,105,55,0.025)] backdrop-blur-[12px] sm:px-12 sm:py-14"
      >

        <!-- الخط الذهبي العلوي / Accent supérieur doré -->
        <div class="card-top-accent"></div>

        <!-- الإطار الداخلي / Cadre intérieur -->
        <div
          class="pointer-events-none absolute inset-[14px] rounded-[20px] border border-[#241b15]/[0.07]"
        ></div>

        <!-- الإضاءة الداخلية / Lumière intérieure -->
        <div class="card-inner-glow"></div>

        <!-- المرجع / Référence -->
        <p class="islamic-card-reference mt-6 text-center">
          {{ current().rumReference }}
        </p>

        <!-- الآية القرآنية / Verset coranique -->

        <blockquote
          class="islamic-main-quote relative mx-auto mt-8 max-w-3xl text-center"
        >
          {{ current().rumMeaning }}
        </blockquote>

        <!-- الرسالة / Message -->

        <p
          class="islamic-card-text relative mx-auto mt-9 max-w-2xl text-center"
        >
          {{ current().messageOne }}
        </p>

        <!-- الزخرفة السفلية بدون دائرة / Décoration inférieure sans cercle -->

        <div
          class="relative mt-10 flex items-center justify-center gap-3"
          aria-hidden="true"
        >
          <span class="card-line"></span>
          <span class="card-line"></span>
        </div>
      </article>

      <!-- =======================================================
           البطاقات الثانوية والختامية
           Français : Cartes secondaires et finale
           البطاقات 2 و3 و4 في صف واحد
           Français : Cartes 2, 3 et 4 sur la même ligne
      ======================================================== -->

      <div
        class="mt-12 grid grid-cols-1 items-stretch gap-7 sm:mt-14 md:grid-cols-3 md:gap-6 lg:gap-8"
      >

        <!-- =====================================================
             البطاقة 2 — القرآن
             Français : Carte 2 — Furqan
        ====================================================== -->

        <article
          class="secondary-card secondary-card-one reveal-card premium-card group relative flex h-full max-w-none flex-col overflow-hidden rounded-[24px] border border-[#241b15]/[0.15] bg-[#f3ede2]/95 px-7 py-8 shadow-[0_22px_55px_rgba(70,48,28,0.065),inset_0_0_45px_rgba(142,105,55,0.025)] backdrop-blur-[12px] transition-[transform,border-color,box-shadow,background-color] duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] hover:-translate-y-2 hover:border-[#8e6937]/[0.42] hover:bg-[#f6f0e6] hover:shadow-[0_32px_70px_rgba(70,48,28,0.13),0_0_0_1px_rgba(142,105,55,0.06)] sm:px-8 sm:py-9"
        >

          <!-- الخط الذهبي العلوي / Accent supérieur doré -->
          <div class="card-top-accent"></div>

          <!-- الإطار الداخلي / Cadre intérieur -->
          <div
            class="pointer-events-none absolute inset-[12px] rounded-[17px] border border-[#241b15]/[0.07]"
          ></div>

          <!-- الإضاءة الداخلية / Lumière intérieure -->
          <div class="card-inner-glow"></div>

          <!-- المرجع في الأعلى / Référence en haut -->

          <p class="secondary-reference">
            {{ current().furqanReference }}
          </p>

          <!-- عنوان البطاقة / Titre de la carte -->

          <p class="secondary-label mt-2">
            {{ current().duaaLabel }}
          </p>

          <!-- الاقتباس / Citation -->

          <p class="secondary-quote relative mt-7 flex-1">
            {{ current().furqanMeaning }}
          </p>

          <!-- الزخرفة السفلية / Décoration inférieure -->

          <div
            class="relative mt-7 h-px w-16 bg-[#241b15]/[0.24] transition-all duration-700 group-hover:w-28 group-hover:bg-[#8e6937]/[0.55]"
          ></div>
        </article>

        <!-- =====================================================
             البطاقة 3 — الحديث
             Français : Carte 3 — Hadith
        ====================================================== -->

        <article
          class="secondary-card secondary-card-two reveal-card premium-card group relative flex h-full max-w-none flex-col overflow-hidden rounded-[24px] border border-[#241b15]/[0.15] bg-[#f3ede2]/95 px-7 py-8 shadow-[0_22px_55px_rgba(70,48,28,0.065),inset_0_0_45px_rgba(142,105,55,0.025)] backdrop-blur-[12px] transition-[transform,border-color,box-shadow,background-color] duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] hover:-translate-y-2 hover:border-[#8e6937]/[0.42] hover:bg-[#f6f0e6] hover:shadow-[0_32px_70px_rgba(70,48,28,0.13),0_0_0_1px_rgba(142,105,55,0.06)] sm:px-8 sm:py-9"
        >

          <!-- الخط الذهبي العلوي / Accent supérieur doré -->
          <div class="card-top-accent"></div>

          <!-- الإطار الداخلي / Cadre intérieur -->
          <div
            class="pointer-events-none absolute inset-[12px] rounded-[17px] border border-[#241b15]/[0.07]"
          ></div>

          <!-- الإضاءة الداخلية / Lumière intérieure -->
          <div class="card-inner-glow"></div>

          <!-- المرجع في الأعلى / Référence en haut -->

          <p class="secondary-reference">
            {{ current().hadithReference }}
          </p>

          <!-- عنوان البطاقة / Titre de la carte -->

          <p class="secondary-label mt-2">
            {{ current().hadithLabel }}
          </p>

          <!-- الاقتباس / Citation -->

          <p class="secondary-quote relative mt-7 flex-1">
            {{ current().hadithMeaning }}
          </p>

          <!-- الزخرفة السفلية / Décoration inférieure -->

          <div
            class="relative mt-7 ml-auto h-px w-16 bg-[#241b15]/[0.24] transition-all duration-700 group-hover:w-28 group-hover:bg-[#8e6937]/[0.55]"
          ></div>
        </article>

        <!-- =====================================================
             البطاقة 4 — الحديث الختامي
             Français : Carte 4 — Hadith final
        ====================================================== -->

        <article
          class="final-card reveal-card premium-card group relative flex h-full max-w-none flex-col overflow-hidden rounded-[24px] border border-[#241b15]/[0.16] bg-[#f3ede2]/95 px-7 py-8 text-center shadow-[0_22px_55px_rgba(70,48,28,0.065),inset_0_0_45px_rgba(142,105,55,0.025)] backdrop-blur-[12px] transition-[transform,border-color,box-shadow,background-color] duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] hover:-translate-y-2 hover:border-[#8e6937]/[0.42] hover:bg-[#f6f0e6] hover:shadow-[0_32px_70px_rgba(70,48,28,0.13),0_0_0_1px_rgba(142,105,55,0.06)] sm:px-8 sm:py-9"
        >

          <!-- الخط الذهبي العلوي / Accent supérieur doré -->
          <div class="card-top-accent"></div>

          <!-- الإطار الداخلي / Cadre intérieur -->
          <div
            class="pointer-events-none absolute inset-[12px] rounded-[17px] border border-[#241b15]/[0.07]"
          ></div>

          <!-- الإضاءة الداخلية / Lumière intérieure -->
          <div class="card-inner-glow"></div>

          <!-- المرجع في الأعلى / Référence en haut -->

          <p class="final-reference relative">
            {{ current().muslimReference }}
          </p>

          <!-- الاقتباس / Citation -->

          <blockquote class="final-quote relative mt-7 flex-1">
            {{ current().finalHadith }}
          </blockquote>

          <!-- الزخرفة السفلية بدون دائرة / Ornement inférieur sans cercle -->

          <div
            class="relative mt-7 h-px w-16 bg-[#241b15]/[0.24] transition-all duration-700 group-hover:w-28 group-hover:bg-[#8e6937]/[0.55]"
          ></div>
        </article>
      </div>

      <!-- =======================================================
           الخاتمة
           Français : Conclusion
      ======================================================== -->

      <div
        class="closing-area reveal-card mx-auto mt-16 max-w-3xl text-center"
      >

        <!-- الزخرفة العلوية / Décoration supérieure -->

        <div
          class="mb-7 flex items-center justify-center gap-[13px]"
          aria-hidden="true"
        >
          <span></span>

          <div class="closing-circle">
            <i></i>
          </div>

          <span></span>
        </div>

        <!-- العبارة الصغيرة / Petite phrase -->

        <p class="closing-small">
          {{ current().closingSmall }}
        </p>

        <!-- الرسالة الختامية / Message final -->

        <p class="closing-main mx-auto mt-5 max-w-2xl">
          {{ current().closingMain }}
        </p>

        <!-- أسماء العروسين / Noms des mariés -->

        <p class="closing-names mt-7">
          {{ current().names }}
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import {
  ref,
  onMounted,
  onUnmounted,
} from 'vue'

/*
  خصائص المكوّن
  Français : Propriétés du composant
*/
const props = defineProps({
  language: {
    type: String,
    default: 'fr',
  },
})

/*
  مرجع القسم وحالة الظهور
  Français : Référence de la section et état de visibilité
*/
const sectionRef = ref(null)
const isVisible = ref(false)

let observer = null

/*
  محتوى الصفحة بالفرنسية والعربية
  Français : Contenu de la section en français et en arabe
*/
const content = {
  fr: {
    eyebrow: 'QUELQUES MOTS POUR CE JOUR',

    title:
      'Et pour accompagner cette belle journée…',

    intro:
      'Quelques paroles du Coran et de la tradition du Prophète ﷺ, choisies pour les beaux sens qu’elles portent : la sérénité, l’affection, la miséricorde et la vie à deux.',

    rumReference:
      'سورة الروم — الآية 21',

    // الآية تبقى بالعربية / Le verset reste en arabe
    rumMeaning:
      ' وَمِنْ آيَاتِهِ أَنْ خَلَقَ لَكُم مِّنْ أَنفُسِكُمْ أَزْوَاجًا لِّتَسْكُنُوا إِلَيْهَا وَجَعَلَ بَيْنَكُم مَّوَدَّةً وَرَحْمَةً ۚ إِنَّ فِي ذَٰلِكَ لَآيَاتٍ لِّقَوْمٍ يَتَفَكَّرُونَ ',

    messageOne:
      'Nous souhaitons que leur chemin soit rempli de cette douceur : se retrouver, se comprendre et avancer ensemble, jour après jour.',

    duaaLabel:
      'دعاء من القرآن الكريم',

    furqanReference:
      'سورة الفرقان — الآية 74',

    furqanMeaning:
      ' رَبَّنَا هَبْ لَنَا مِنْ أَزْوَاجِنَا وَذُرِّيَّاتِنَا قُرَّةَ أَعْيُنٍ وَاجْعَلْنَا لِّلْمُتَّقِينَ إِمَامًا ',

    hadithLabel:
      'من هدي النبي ﷺ',

    hadithReference:
      'رواه الترمذي — 3895',

    hadithMeaning:
      ' خيركم خيركم لأهله، وأنا خيركم لأهلي. ',

    finalHadith:
      ' الدنيا متاع، وخير متاع الدنيا المرأة الصالحة. ',

    muslimReference:
      'رواه مسلم — 1467',

    closingSmall:
      'POUR COMMENCER CETTE NOUVELLE VIE',

    closingMain:
      'Qu’Allah bénisse leur union, mette entre eux sérénité, affection et miséricorde, et les accompagne dans chaque étape de leur chemin.',

    names:
      'foulen & faltena',
  },

  ar: {
    eyebrow:
      'من هدي الإسلام',

    title:
      'وبين يدي هذه الفرحة…',

    intro:
      'كلمات من كتاب الله وسنة نبيه ﷺ، نحب أن ترافق هذه المناسبة بما تحمله من سكينة ومودة ورحمة.',

    rumReference:
      'سورة الروم — الآية 21',

    rumMeaning:
      '﴿ وَمِنْ آيَاتِهِ أَنْ خَلَقَ لَكُم مِّنْ أَنفُسِكُمْ أَزْوَاجًا لِّتَسْكُنُوا إِلَيْهَا وَجَعَلَ بَيْنَكُم مَّوَدَّةً وَرَحْمَةً ۚ إِنَّ فِي ذَٰلِكَ لَآيَاتٍ لِّقَوْمٍ يَتَفَكَّرُونَ ﴾',

    messageOne:
      'نسأل الله أن يجعل بينهما من المودة ما يطمئن القلب، ومن الرحمة ما يبقى مع الأيام، وأن يبارك لهما في حياتهما القادمة.',

    duaaLabel:
      'دعاء من القرآن الكريم',

    furqanReference:
      'سورة الفرقان — الآية 74',

    furqanMeaning:
      '﴿ رَبَّنَا هَبْ لَنَا مِنْ أَزْوَاجِنَا وَذُرِّيَّاتِنَا قُرَّةَ أَعْيُنٍ وَاجْعَلْنَا لِّلْمُتَّقِينَ إِمَامًا ﴾',

    hadithLabel:
      'من هدي النبي ﷺ',

    hadithReference:
      'رواه الترمذي — 3895',

    hadithMeaning:
      '« خيركم خيركم لأهله، وأنا خيركم لأهلي. »',

    finalHadith:
      '« الدنيا متاع، وخير متاع الدنيا المرأة الصالحة. »',

    muslimReference:
      'رواه مسلم — 1467',

    closingSmall:
      'وفي بداية هذه الحياة الجديدة',

    closingMain:
      'اللهم بارك لهما، وبارك عليهما، واجمع بينهما في خير، وارزقهما السكينة والمودة والرحمة، واجعل حياتهما مليئة بالخير والبركة.',

    names:
      'فولان & فلتانة',
  },
}

/*
  الحصول على المحتوى حسب اللغة الحالية
  Français : Récupération du contenu selon la langue active
*/
const current = () => {
  return content[props.language] || content.fr
}

/*
  مراقبة ظهور القسم أثناء التمرير
  Français : Observation de la visibilité de la section au défilement
*/
onMounted(() => {
  if (!sectionRef.value) return

  observer = new IntersectionObserver(
    ([entry]) => {
      isVisible.value = entry.isIntersecting
    },
    {
      threshold: 0.12,
    },
  )

  observer.observe(sectionRef.value)
})

/*
  تنظيف المراقب عند إزالة المكوّن
  Français : Nettoyage de l’observateur lors de la destruction du composant
*/
onUnmounted(() => {
  observer?.disconnect()
})
</script>

<style scoped>

/* ============================================================
   الأساس
   Français : Base de la section
============================================================ */

.islamic-marriage {
  isolation: isolate;
}

/* ============================================================
   الإضاءات المحيطة
   Français : Lumières d’ambiance
============================================================ */

.islamic-glow {
  position: absolute;
  border-radius: 9999px;
  pointer-events: none;
  filter: blur(100px);
  will-change: transform;
}

.glow-one {
  width: 440px;
  height: 440px;
  top: -170px;
  right: -130px;
  background: rgba(155, 117, 63, 0.12);
  animation: glowOne 22s ease-in-out infinite;
}

.glow-two {
  width: 400px;
  height: 400px;
  bottom: -170px;
  left: -120px;
  background: rgba(112, 85, 54, 0.09);
  animation: glowTwo 25s ease-in-out infinite;
}

.glow-three {
  width: 300px;
  height: 300px;
  top: 42%;
  left: 42%;
  background: rgba(168, 130, 74, 0.06);
  animation: glowThree 20s ease-in-out infinite;
}

@keyframes glowOne {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }

  50% {
    transform: translate3d(-50px, 45px, 0);
  }
}

@keyframes glowTwo {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }

  50% {
    transform: translate3d(55px, -45px, 0);
  }
}

@keyframes glowThree {
  0%,
  100% {
    transform: translate3d(0, 0, 0) scale(1);
  }

  50% {
    transform: translate3d(25px, -30px, 0) scale(1.08);
  }
}

/* ============================================================
   النمط الدائري الرئيسي
   Français : Motif circulaire principal
============================================================ */

.islamic-circle-pattern {
  position: absolute;
  inset: -8%;
  pointer-events: none;

  opacity: 0.095;

  background-image:
    radial-gradient(
      circle at center,
      transparent 0 18px,
      #705536 18px 20px,
      transparent 20px 34px,
      #8e6937 34px 36px,
      transparent 36px 51px
    );

  background-size: 108px 108px;

  animation:
    islamicCirclePatternMove
    44s
    linear
    infinite;

  will-change: background-position;
}

@keyframes islamicCirclePatternMove {
  from {
    background-position: 0 0;
  }

  to {
    background-position: 108px 108px;
  }
}

/* ============================================================
   الشبكة الدائرية الثانوية
   Français : Grille circulaire secondaire
============================================================ */

.islamic-circle-grid {
  position: absolute;
  inset: -5%;
  pointer-events: none;

  opacity: 0.075;

  background-image:
    radial-gradient(
      circle,
      #241b15 1.2px,
      transparent 1.3px
    );

  background-size: 36px 36px;

  animation:
    islamicCircleGridMove
    36s
    linear
    infinite;

  will-change: background-position;
}

@keyframes islamicCircleGridMove {
  from {
    background-position: 0 0;
  }

  to {
    background-position: 36px 36px;
  }
}

/* ============================================================
   المدارات الكبيرة
   Français : Grandes orbites
============================================================ */

.islamic-orbit {
  position: absolute;
  border-radius: 50%;
  pointer-events: none;

  border: 2px solid rgba(112, 85, 54, 0.12);
}

.orbit-one {
  width: 250px;
  height: 250px;
  top: 14%;
  left: -125px;

  box-shadow:
    0 0 0 18px rgba(112, 85, 54, 0.025),
    0 0 0 36px rgba(112, 85, 54, 0.018);

  animation:
    orbitOne
    26s
    ease-in-out
    infinite;
}

.orbit-two {
  width: 300px;
  height: 300px;
  right: -150px;
  bottom: 12%;

  box-shadow:
    0 0 0 20px rgba(112, 85, 54, 0.025),
    0 0 0 42px rgba(112, 85, 54, 0.018);

  animation:
    orbitTwo
    30s
    ease-in-out
    infinite;
}

@keyframes orbitOne {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }

  50% {
    transform: translate3d(18px, -15px, 0) rotate(8deg);
  }
}

@keyframes orbitTwo {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }

  50% {
    transform: translate3d(-20px, 16px, 0) rotate(-8deg);
  }
}

/* ============================================================
   الدوائر العائمة
   Français : Cercles flottants
============================================================ */

.floating-circle {
  position: absolute;
  border-radius: 50%;
  pointer-events: none;

  border: 2px solid rgba(112, 85, 54, 0.25);
}

.floating-circle::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;

  width: 6px;
  height: 6px;

  transform: translate(-50%, -50%);
  border-radius: 50%;

  background: #8e6937;
  opacity: 0.55;
}

.circle-one {
  width: 32px;
  height: 32px;
  top: 25%;
  left: 12%;

  animation:
    floatingCircleOne
    17s
    ease-in-out
    infinite;
}

.circle-two {
  width: 24px;
  height: 24px;
  top: 38%;
  right: 12%;

  animation:
    floatingCircleTwo
    19s
    ease-in-out
    infinite;
}

.circle-three {
  width: 28px;
  height: 28px;
  bottom: 23%;
  left: 15%;

  animation:
    floatingCircleThree
    21s
    ease-in-out
    infinite;
}

.circle-four {
  width: 38px;
  height: 38px;
  right: 14%;
  bottom: 19%;

  animation:
    floatingCircleFour
    23s
    ease-in-out
    infinite;
}

@keyframes floatingCircleOne {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }

  50% {
    transform: translate3d(18px, -18px, 0);
  }
}

@keyframes floatingCircleTwo {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }

  50% {
    transform: translate3d(-18px, 15px, 0);
  }
}

@keyframes floatingCircleThree {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }

  50% {
    transform: translate3d(15px, -18px, 0);
  }
}

@keyframes floatingCircleFour {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }

  50% {
    transform: translate3d(-16px, -20px, 0);
  }
}

/* ============================================================
   النقاط
   Français : Points flottants
============================================================ */

.floating-dot {
  position: absolute;

  width: 5px;
  height: 5px;

  border-radius: 50%;
  background: #241b15;

  opacity: 0.3;
  pointer-events: none;
}

.dot-one {
  top: 19%;
  right: 23%;
  animation: dotFloat 14s ease-in-out infinite;
}

.dot-two {
  top: 62%;
  left: 10%;
  animation: dotFloat 17s ease-in-out infinite 1s;
}

.dot-three {
  right: 20%;
  bottom: 24%;
  animation: dotFloat 15s ease-in-out infinite 2s;
}

.dot-four {
  top: 42%;
  left: 24%;
  animation: dotFloat 18s ease-in-out infinite 1.5s;
}

@keyframes dotFloat {
  0%,
  100% {
    transform: translateY(0);
    opacity: 0.2;
  }

  50% {
    transform: translateY(-10px);
    opacity: 0.45;
  }
}

/* ============================================================
   الإطار
   Français : Cadre
============================================================ */

.frame-corner {
  position: absolute;
  width: 42px;
  height: 42px;
}

.frame-corner::before,
.frame-corner::after {
  content: "";
  position: absolute;
  background: #241b15;
  opacity: 0.55;
}

.frame-corner::before {
  width: 42px;
  height: 1px;
}

.frame-corner::after {
  width: 1px;
  height: 42px;
}

.frame-tl {
  top: 0;
  left: 0;
}

.frame-tr {
  top: 0;
  right: 0;
  transform: rotate(90deg);
}

.frame-bl {
  bottom: 0;
  left: 0;
  transform: rotate(-90deg);
}

.frame-br {
  right: 0;
  bottom: 0;
  transform: rotate(180deg);
}

/* ============================================================
   رأس الصفحة
   Français : En-tête
============================================================ */

.islamic-label {
  color: #8e6937;

  font-family: "Montserrat", sans-serif;
  font-size: 10px;
  font-weight: 600;
  letter-spacing: 0.32em;

  opacity: 0;
  transform: translateY(18px);

  transition:
    opacity 1.1s cubic-bezier(0.22, 1, 0.36, 1),
    transform 1.1s cubic-bezier(0.22, 1, 0.36, 1);
}

.islamic-active .islamic-label {
  opacity: 1;
  transform: translateY(0);
}

.islamic-label span:not(:nth-child(2)) {
  width: 34px;
  height: 1px;
  background: rgba(36, 27, 21, 0.3);
}

.islamic-title {
  color: #30241c;

  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: clamp(2.7rem, 6vw, 4.6rem);
  font-weight: 500;
  line-height: 1;

  opacity: 0;
  transform: translateY(22px);

  transition:
    opacity 1.35s cubic-bezier(0.22, 1, 0.36, 1) 0.2s,
    transform 1.35s cubic-bezier(0.22, 1, 0.36, 1) 0.2s;
}

.islamic-active .islamic-title {
  opacity: 1;
  transform: translateY(0);
}

.islamic-description {
  color: #685545;

  font-family: "Montserrat", sans-serif;
  font-size: 13px;
  line-height: 1.9;

  opacity: 0;
  transform: translateY(18px);

  transition:
    opacity 1.1s cubic-bezier(0.22, 1, 0.36, 1) 0.4s,
    transform 1.1s cubic-bezier(0.22, 1, 0.36, 1) 0.4s;
}

.islamic-active .islamic-description {
  opacity: 1;
  transform: translateY(0);
}

.islamic-divider {
  opacity: 0;
  transform: scaleX(0.65);

  transition:
    opacity 1.1s ease 0.55s,
    transform 1.1s cubic-bezier(0.22, 1, 0.36, 1) 0.55s;
}

.islamic-active .islamic-divider {
  opacity: 1;
  transform: scaleX(1);
}

.islamic-divider span {
  width: 58px;
  height: 1px;
  background: rgba(36, 27, 21, 0.28);
}

.islamic-divider div {
  width: 10px;
  height: 10px;

  border: 1px solid #241b15;
  border-radius: 50%;

  animation:
    dividerCircle
    7s
    ease-in-out
    infinite;
}

@keyframes dividerCircle {
  0%,
  100% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.25);
  }
}

/* ============================================================
   ظهور البطاقات
   Français : Animation d’apparition des cartes
============================================================ */

.reveal-card {
  opacity: 0;
  filter: blur(3px);
  transform: translateY(32px);

  transition:
    opacity 1.3s cubic-bezier(0.22, 1, 0.36, 1),
    filter 1.3s cubic-bezier(0.22, 1, 0.36, 1),
    transform 1.3s cubic-bezier(0.22, 1, 0.36, 1);
}

.islamic-active .reveal-card {
  opacity: 1;
  filter: blur(0);
  transform: translateY(0);
}

.main-card {
  transition-delay: 0.7s;

  animation:
    mainCardFloat
    8s
    ease-in-out
    2.2s
    infinite;
}

.secondary-card-one {
  transition-delay: 0.9s;

  animation:
    secondaryFloatOne
    7.5s
    ease-in-out
    2.5s
    infinite;
}

.secondary-card-two {
  transition-delay: 1.1s;

  animation:
    secondaryFloatTwo
    8.5s
    ease-in-out
    2.7s
    infinite;
}

.final-card {
  transition-delay: 1.3s;

  animation:
    finalCardFloat
    9s
    ease-in-out
    2.9s
    infinite;
}

.closing-area {
  transition-delay: 1.5s;
}

/* ============================================================
   حركة البطاقات
   Français : Animation flottante des cartes
============================================================ */

@keyframes mainCardFloat {
  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-5px);
  }
}

@keyframes secondaryFloatOne {
  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-5px);
  }
}

@keyframes secondaryFloatTwo {
  0%,
  100% {
    transform: translateY(-2px);
  }

  50% {
    transform: translateY(5px);
  }
}

@keyframes finalCardFloat {
  0%,
  100% {
    transform: translateY(2px);
  }

  50% {
    transform: translateY(-5px);
  }
}

/* ============================================================
   نظام البطاقات الفاخرة
   Français : Système des cartes premium
============================================================ */

.premium-card {
  isolation: isolate;
  will-change: transform;
}

/* الخط الذهبي الدقيق في الأعلى / Fine ligne dorée supérieure */

.card-top-accent {
  position: absolute;
  top: 0;
  left: 50%;
  z-index: 5;

  width: 86px;
  height: 1px;

  transform: translateX(-50%);

  background:
    linear-gradient(
      90deg,
      transparent,
      rgba(142, 105, 55, 0.7),
      transparent
    );

  opacity: 0.65;

  transition:
    width 700ms cubic-bezier(0.22, 1, 0.36, 1),
    opacity 700ms ease;
}

.premium-card:hover .card-top-accent {
  width: 150px;
  opacity: 1;
}

/* الإضاءة الداخلية الناعمة / Lumière intérieure subtile */

.card-inner-glow {
  position: absolute;
  inset: 0;
  z-index: -1;

  pointer-events: none;

  background:
    radial-gradient(
      circle at 50% 0%,
      rgba(142, 105, 55, 0.075),
      transparent 42%
    );

  opacity: 0.65;

  transition: opacity 800ms ease;
}

.premium-card:hover .card-inner-glow {
  opacity: 1;
}

/* ============================================================
   البطاقة الرئيسية
   Français : Carte principale
============================================================ */

.islamic-card-reference {
  color: #8e6937;

  font-family: "Montserrat", sans-serif;
  font-size: 10px;
  font-weight: 600;
  letter-spacing: 0.3em;
}

.islamic-main-quote {
  color: #30241c;

  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: clamp(1.3rem, 2.5vw, 1.75rem);
  line-height: 2.1;
  text-wrap: balance;
}

.islamic-card-text {
  color: #685545;

  font-family: "Montserrat", sans-serif;
  font-size: 13px;
  line-height: 1.95;
}

/* ============================================================
   زخرفة البطاقة الرئيسية
   Français : Ornement de la carte principale
============================================================ */

.card-ornament {
  opacity: 0.9;
}

.card-ring {
  position: absolute;

  border: 1px solid rgba(36, 27, 21, 0.3);
  border-radius: 50%;
}

.ring-one {
  inset: 0;

  animation:
    ringRotate
    20s
    linear
    infinite;
}

.ring-two {
  inset: 10px;

  border-color: rgba(142, 105, 55, 0.5);

  animation:
    ringPulse
    4s
    ease-in-out
    infinite;
}

.card-ring-dot {
  width: 6px;
  height: 6px;

  border-radius: 50%;
  background: #8e6937;

  animation:
    dotPulse
    3.5s
    ease-in-out
    infinite;
}

@keyframes ringRotate {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

@keyframes ringPulse {
  0%,
  100% {
    transform: scale(0.88);
    opacity: 0.55;
  }

  50% {
    transform: scale(1.1);
    opacity: 0.9;
  }
}

@keyframes dotPulse {
  0%,
  100% {
    transform: scale(0.8);
    opacity: 0.5;
  }

  50% {
    transform: scale(1.5);
    opacity: 0.9;
  }
}

.card-line {
  width: 55px;
  height: 1px;
  background: rgba(36, 27, 21, 0.25);
}

.card-small-circle {
  width: 7px;
  height: 7px;

  border: 1px solid rgba(36, 27, 21, 0.5);
  border-radius: 50%;

  animation:
    smallCirclePulse
    3.5s
    ease-in-out
    infinite;
}

@keyframes smallCirclePulse {
  0%,
  100% {
    transform: scale(0.8);
    opacity: 0.5;
  }

  50% {
    transform: scale(1.3);
    opacity: 1;
  }
}

/* ============================================================
   البطاقات الثانوية
   Français : Cartes secondaires
============================================================ */

.secondary-label {
  color: #8e6937;

  font-family: "Montserrat", sans-serif;
  font-size: 9px;
  font-weight: 600;
  letter-spacing: 0.28em;

  line-height: 1.5;
}

.secondary-reference {
  color: #705536;

  font-family: "Montserrat", sans-serif;
  font-size: 10px;
  font-weight: 500;
  line-height: 1.6;
}

.secondary-quote {
  color: #30241c;

  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: clamp(1.3rem, 2.5vw, 1.7rem);
  line-height: 2.05;
  text-wrap: balance;
}

.secondary-ornament {
  position: relative;

  display: flex;
  width: 42px;
  height: 42px;

  flex-shrink: 0;

  align-items: center;
  justify-content: center;
}

.secondary-ornament span {
  position: absolute;

  border: 1px solid rgba(36, 27, 21, 0.32);
  border-radius: 50%;
}

.secondary-ornament span:first-child {
  inset: 0;

  animation:
    ringRotate
    18s
    linear
    infinite;
}

.secondary-ornament span:last-child {
  inset: 10px;

  border-color: rgba(142, 105, 55, 0.55);

  animation:
    ringPulse
    4s
    ease-in-out
    infinite;
}

/* ============================================================
   البطاقة النهائية
   Français : Carte finale
============================================================ */

.final-ornament {
  opacity: 0.9;
}

.final-ornament span {
  position: absolute;

  border: 1px solid rgba(36, 27, 21, 0.3);
  border-radius: 50%;
}

.final-ornament span:first-child {
  inset: 0;

  animation:
    ringRotate
    20s
    linear
    infinite;
}

.final-ornament span:nth-child(2) {
  inset: 9px;

  border-color: rgba(142, 105, 55, 0.55);

  animation:
    ringPulse
    4s
    ease-in-out
    infinite;
}

.final-ornament i {
  width: 5px;
  height: 5px;

  border-radius: 50%;
  background: #8e6937;

  animation:
    dotPulse
    3.5s
    ease-in-out
    infinite;
}

.final-quote {
  color: #30241c;

  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: clamp(1.3rem, 2.5vw, 1.7rem);
  line-height: 2.1;
  text-wrap: balance;
}

.final-reference {
  color: #8e6937;

  font-family: "Montserrat", sans-serif;
  font-size: 10px;
  font-weight: 600;
  letter-spacing: 0.25em;
}

/* الزخرفة السفلية الصغيرة / Petit ornement inférieur */

.final-bottom-ornament {
  display: flex;

  align-items: center;
  justify-content: center;
  gap: 7px;

  margin-top: 25px;

  opacity: 0.65;
}

.final-bottom-ornament span {
  width: 22px;
  height: 1px;

  background: rgba(36, 27, 21, 0.24);
}

.final-bottom-ornament i {
  width: 5px;
  height: 5px;

  border: 1px solid rgba(142, 105, 55, 0.65);
  border-radius: 50%;

  animation:
    smallCirclePulse
    3.5s
    ease-in-out
    infinite;
}

/* ============================================================
   الخاتمة
   Français : Conclusion
============================================================ */

.closing-area > div span {
  width: 55px;
  height: 1px;
  background: rgba(36, 27, 21, 0.28);
}

.closing-circle {
  display: flex;

  width: 12px;
  height: 12px;

  align-items: center;
  justify-content: center;

  border: 1px solid #241b15;
  border-radius: 50%;

  animation:
    closingCircle
    6s
    ease-in-out
    infinite;
}

.closing-circle i {
  width: 4px;
  height: 4px;

  border-radius: 50%;
  background: #241b15;
}

@keyframes closingCircle {
  0%,
  100% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.25);
  }
}

.closing-small {
  color: #8e6937;

  font-family: "Montserrat", sans-serif;
  font-size: 9px;
  font-weight: 600;
  letter-spacing: 0.3em;
}

.closing-main {
  color: #30241c;

  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: clamp(1.3rem, 2.5vw, 1.7rem);
  line-height: 2.1;
}

.closing-names {
  color: #8e6937;

  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: 1.2rem;
  font-style: italic;
}

/* ============================================================
   اللغة العربية
   Français : Styles pour l’arabe
============================================================ */

[dir="rtl"] .islamic-title,
[dir="rtl"] .islamic-main-quote,
[dir="rtl"] .secondary-quote,
[dir="rtl"] .final-quote,
[dir="rtl"] .closing-main,
[dir="rtl"] .closing-names {
  font-family: "Amiri", "Noto Naskh Arabic", serif;
}

[dir="rtl"] .islamic-description,
[dir="rtl"] .islamic-card-text {
  line-height: 2.15;
}

[dir="rtl"] .islamic-label,
[dir="rtl"] .secondary-label,
[dir="rtl"] .secondary-reference,
[dir="rtl"] .final-reference,
[dir="rtl"] .closing-small {
  letter-spacing: normal;
}

/* ============================================================
   الهاتف والشاشات الصغيرة
   Français : Mobile et petits écrans

   ملاحظة:
   لا يتم تغيير التصميم الأساسي هنا.
   فقط يتم ضبط الأحجام والمسافات حتى يظهر المحتوى بشكل مرتب.
============================================================ */

@media (max-width: 700px) {

  /* ----------------------------------------------------------
     الخلفية
     فقط تخفيف بسيط جدًا للزخارف
  ---------------------------------------------------------- */

  .islamic-circle-pattern {
    opacity: 0.075;
    background-size: 82px 82px;
  }

  .islamic-circle-grid {
    opacity: 0.055;
    background-size: 30px 30px;
  }

  .islamic-orbit {
    opacity: 0.5;
  }

  .orbit-one {
    width: 190px;
    height: 190px;
    left: -95px;
  }

  .orbit-two {
    width: 220px;
    height: 220px;
    right: -110px;
  }

  .floating-circle {
    opacity: 0.55;
  }


  /* ----------------------------------------------------------
     الإطار الخارجي
     نفس الإطار، فقط أصغر قليلًا على الهاتف
  ---------------------------------------------------------- */

  .islamic-frame {
    inset: 16px;
  }

  .frame-corner {
    width: 34px;
    height: 34px;
  }

  .frame-corner::before {
    width: 34px;
  }

  .frame-corner::after {
    height: 34px;
  }


  /* ----------------------------------------------------------
     المحتوى الرئيسي
     تقليل padding الجانبي فقط
  ---------------------------------------------------------- */

  .islamic-marriage > .relative.z-20 {
    padding-left: 20px;
    padding-right: 20px;
  }


  /* ----------------------------------------------------------
     العنوان
  ---------------------------------------------------------- */

  .islamic-title {
    font-size: 2.7rem;
    line-height: 1.08;
  }


  /* ----------------------------------------------------------
     الوصف
  ---------------------------------------------------------- */

  .islamic-description {
    padding-left: 4px;
    padding-right: 4px;

    font-size: 12px;
    line-height: 1.95;
  }


  /* ----------------------------------------------------------
     الفاصل
  ---------------------------------------------------------- */

  .islamic-divider {
    gap: 9px;
  }

  .islamic-divider span {
    width: 42px;
  }


  /* ----------------------------------------------------------
     البطاقة الرئيسية
     نفس التصميم، فقط padding مناسب للهاتف
  ---------------------------------------------------------- */

  .main-card {
    margin-top: 42px;

    padding-left: 22px;
    padding-right: 22px;

    padding-top: 40px;
    padding-bottom: 40px;

    border-radius: 24px;
  }


  /* الإطار الداخلي */

  .main-card > .pointer-events-none {
    inset: 11px;
    border-radius: 17px;
  }


  /* المرجع */

  .islamic-card-reference {
    padding-left: 6px;
    padding-right: 6px;

    font-size: 9px;
    line-height: 1.7;
    letter-spacing: 0.18em;
  }


  /* الآية */

  .islamic-main-quote {
    padding-left: 3px;
    padding-right: 3px;

    font-size: 1.25rem;
    line-height: 2.15;

    overflow-wrap: anywhere;
  }


  /* الرسالة */

  .islamic-card-text {
    padding-left: 3px;
    padding-right: 3px;

    font-size: 12px;
    line-height: 2;
  }


  /* ----------------------------------------------------------
     البطاقات الثانوية
     لا نغير grid:
     تبقى عمودية على الهاتف كما هي أصلًا
  ---------------------------------------------------------- */

  .secondary-card,
  .final-card {
    min-width: 0;

    padding-left: 22px;
    padding-right: 22px;

    padding-top: 32px;
    padding-bottom: 32px;

    border-radius: 22px;
  }


  /* المرجع */

  .secondary-reference,
  .final-reference {
    padding-left: 4px;
    padding-right: 4px;

    font-size: 9px;
    line-height: 1.7;

    overflow-wrap: anywhere;
  }


  /* عنوان البطاقة */

  .secondary-label {
    font-size: 8px;
    line-height: 1.7;
    letter-spacing: 0.14em;
  }


  /* الاقتباسات */

  .secondary-quote,
  .final-quote {
    padding-left: 2px;
    padding-right: 2px;

    font-size: 1.25rem;
    line-height: 2.15;

    overflow-wrap: anywhere;
  }


  /* ----------------------------------------------------------
     الخاتمة
  ---------------------------------------------------------- */

  .closing-area {
    margin-top: 56px;
  }

  .closing-area > div {
    gap: 9px;
  }

  .closing-area > div span {
    width: 40px;
  }

  .closing-small {
    padding-left: 8px;
    padding-right: 8px;

    font-size: 8px;
    line-height: 1.8;
    letter-spacing: 0.18em;
  }

  .closing-main {
    padding-left: 4px;
    padding-right: 4px;

    font-size: 1.25rem;
    line-height: 2.15;

    overflow-wrap: anywhere;
  }

  .closing-names {
    font-size: 1.1rem;
  }


  /* ----------------------------------------------------------
     الإضاءة الداخلية
     لا نلغيها، فقط نجعلها أخف قليلًا
  ---------------------------------------------------------- */

  .card-inner-glow {
    opacity: 0.55;
  }
}


/* ============================================================
   الهواتف الصغيرة جدًا
   430px وما دون
============================================================ */

@media (max-width: 430px) {

  /* ----------------------------------------------------------
     الإطار
  ---------------------------------------------------------- */

  .islamic-frame {
    inset: 12px;
  }

  .frame-corner {
    width: 30px;
    height: 30px;
  }

  .frame-corner::before {
    width: 30px;
  }

  .frame-corner::after {
    height: 30px;
  }


  /* ----------------------------------------------------------
     المحتوى
  ---------------------------------------------------------- */

  .islamic-marriage > .relative.z-20 {
    padding-left: 16px;
    padding-right: 16px;
  }


  /* ----------------------------------------------------------
     العنوان
  ---------------------------------------------------------- */

  .islamic-title {
    font-size: 2.35rem;
    line-height: 1.1;
  }


  /* ----------------------------------------------------------
     الوصف
  ---------------------------------------------------------- */

  .islamic-description {
    font-size: 11px;
    line-height: 1.9;
  }


  /* ----------------------------------------------------------
     الفاصل
  ---------------------------------------------------------- */

  .islamic-divider {
    gap: 7px;
  }

  .islamic-divider span {
    width: 32px;
  }


  /* ----------------------------------------------------------
     البطاقة الرئيسية
  ---------------------------------------------------------- */

  .main-card {
    margin-top: 36px;

    padding-left: 18px;
    padding-right: 18px;

    padding-top: 34px;
    padding-bottom: 34px;

    border-radius: 22px;
  }

  .main-card > .pointer-events-none {
    inset: 10px;
    border-radius: 16px;
  }


  /* ----------------------------------------------------------
     المرجع
  ---------------------------------------------------------- */

  .islamic-card-reference {
    font-size: 8px;
    line-height: 1.75;
    letter-spacing: 0.1em;
  }


  /* ----------------------------------------------------------
     الآية
  ---------------------------------------------------------- */

  .islamic-main-quote {
    margin-top: 24px;

    font-size: 1.16rem;
    line-height: 2.1;
  }


  /* ----------------------------------------------------------
     الرسالة
  ---------------------------------------------------------- */

  .islamic-card-text {
    margin-top: 26px;

    font-size: 11px;
    line-height: 2;
  }


  /* ----------------------------------------------------------
     البطاقات الثانوية
  ---------------------------------------------------------- */

  .secondary-card,
  .final-card {
    padding-left: 18px;
    padding-right: 18px;

    padding-top: 29px;
    padding-bottom: 29px;

    border-radius: 20px;
  }


  .secondary-reference,
  .final-reference {
    font-size: 8px;
    line-height: 1.75;
  }


  .secondary-label {
    font-size: 7.5px;
    line-height: 1.7;
    letter-spacing: 0.08em;
  }


  .secondary-quote,
  .final-quote {
    margin-top: 22px;

    font-size: 1.16rem;
    line-height: 2.1;
  }


  /* ----------------------------------------------------------
     الخاتمة
  ---------------------------------------------------------- */

  .closing-area {
    margin-top: 48px;
  }

  .closing-area > div span {
    width: 32px;
  }

  .closing-small {
    font-size: 7px;
    line-height: 1.8;
    letter-spacing: 0.12em;
  }

  .closing-main {
    margin-top: 16px;

    font-size: 1.16rem;
    line-height: 2.1;
  }

  .closing-names {
    margin-top: 18px;

    font-size: 1.05rem;
  }


  /* ----------------------------------------------------------
     الزخارف الخلفية
     فقط تقليل بسيط جدًا
  ---------------------------------------------------------- */

  .islamic-circle-pattern {
    opacity: 0.065;
    background-size: 72px 72px;
  }

  .islamic-circle-grid {
    opacity: 0.045;
  }

  .floating-circle {
    opacity: 0.35;
  }
}


/* ============================================================
   الهواتف الصغيرة جدًا جدًا
   360px وما دون
============================================================ */

@media (max-width: 360px) {

  .islamic-frame {
    inset: 9px;
  }

  .frame-corner {
    width: 25px;
    height: 25px;
  }

  .frame-corner::before {
    width: 25px;
  }

  .frame-corner::after {
    height: 25px;
  }


  .islamic-marriage > .relative.z-20 {
    padding-left: 13px;
    padding-right: 13px;
  }


  .islamic-title {
    font-size: 2.1rem;
  }


  .islamic-description {
    font-size: 10px;
  }


  .islamic-divider span {
    width: 27px;
  }


  .main-card {
    padding-left: 15px;
    padding-right: 15px;
  }


  .islamic-main-quote {
    font-size: 1.1rem;
    line-height: 2.05;
  }


  .islamic-card-text {
    font-size: 10px;
    line-height: 1.95;
  }


  .secondary-card,
  .final-card {
    padding-left: 15px;
    padding-right: 15px;
  }


  .secondary-quote,
  .final-quote {
    font-size: 1.1rem;
    line-height: 2.05;
  }


  .closing-main {
    font-size: 1.1rem;
    line-height: 2.05;
  }


  .closing-names {
    font-size: 1rem;
  }
}


/* ============================================================
   اللغة العربية على الهاتف
   Français : Arabe sur mobile
============================================================ */

@media (max-width: 700px) {

  [dir="rtl"] .islamic-title {
    font-size: 2.45rem;
    line-height: 1.4;
  }

  [dir="rtl"] .islamic-description {
    font-size: 14px;
    line-height: 2.15;
  }

  [dir="rtl"] .islamic-card-reference {
    font-size: 12px;
    letter-spacing: normal;
  }

  [dir="rtl"] .islamic-main-quote,
  [dir="rtl"] .secondary-quote,
  [dir="rtl"] .final-quote {
    font-size: 1.35rem;
    line-height: 2.2;
  }

  [dir="rtl"] .islamic-card-text {
    font-size: 13px;
    line-height: 2.15;
  }

  [dir="rtl"] .secondary-label {
    font-size: 13px;
    letter-spacing: normal;
  }

  [dir="rtl"] .secondary-reference,
  [dir="rtl"] .final-reference {
    font-size: 12px;
    letter-spacing: normal;
  }

  [dir="rtl"] .closing-small {
    font-size: 13px;
    letter-spacing: normal;
  }

  [dir="rtl"] .closing-main {
    font-size: 1.35rem;
    line-height: 2.2;
  }
}


@media (max-width: 430px) {

  [dir="rtl"] .islamic-title {
    font-size: 2.2rem;
  }

  [dir="rtl"] .islamic-description {
    font-size: 13px;
  }

  [dir="rtl"] .islamic-main-quote,
  [dir="rtl"] .secondary-quote,
  [dir="rtl"] .final-quote {
    font-size: 1.27rem;
  }

  [dir="rtl"] .islamic-card-text {
    font-size: 12px;
  }

  [dir="rtl"] .closing-main {
    font-size: 1.27rem;
  }
}


/* ============================================================
   تقليل الحركة
   Français : Réduction des animations
============================================================ */

@media (prefers-reduced-motion: reduce) {

  .islamic-glow,
  .islamic-circle-pattern,
  .islamic-circle-grid,
  .islamic-orbit,
  .floating-circle,
  .floating-dot,
  .card-ring,
  .card-ring-dot,
  .card-small-circle,
  .secondary-ornament span,
  .final-ornament span,
  .final-ornament i,
  .final-bottom-ornament i,
  .closing-circle,
  .main-card,
  .secondary-card-one,
  .secondary-card-two,
  .final-card {
    animation: none !important;
  }

  .islamic-label,
  .islamic-title,
  .islamic-description,
  .islamic-divider,
  .reveal-card {
    opacity: 1 !important;
    transform: none !important;
    filter: none !important;
    transition: none !important;
  }
}

</style>