<template>
  <section
    id="invitation"
    ref="sectionRef"
    class="invitation-section relative min-h-screen overflow-hidden text-[#30241c]"
    :class="{ 'invitation-active': isVisible }"
    :dir="language === 'ar' ? 'rtl' : 'ltr'"
  >
    <!-- =========================================================
         BACKGROUND
    ========================================================== -->

    <div class="absolute inset-0 bg-[#e7dfd1]"></div>

    <!-- Ambient lights -->
    <div
      class="ambient-light ambient-light-one pointer-events-none absolute rounded-full"
    ></div>

    <div
      class="ambient-light ambient-light-two pointer-events-none absolute rounded-full"
    ></div>

    <div
      class="ambient-light ambient-light-three pointer-events-none absolute rounded-full"
    ></div>

    <!-- Tunisian pattern -->
    <div
      class="tunisian-pattern pointer-events-none absolute -inset-[10%]"
    ></div>

    <!-- Dot pattern -->
    <div
      class="dot-pattern pointer-events-none absolute inset-0"
    ></div>

    <!-- =========================================================
         DECORATIONS
    ========================================================== -->

    <!-- Top ornament -->
    <div
      class="top-ornament pointer-events-none absolute left-1/2 top-[9%] flex -translate-x-1/2 items-center gap-3 opacity-45"
    >
      <span
        class="h-[6px] w-[6px] rotate-45 border border-[#8e6937]"
      ></span>

      <span
        class="h-3 w-3 rotate-45 border border-[#8e6937] bg-[#8e6937]/[0.08]"
      ></span>

      <span
        class="h-[6px] w-[6px] rotate-45 border border-[#8e6937]"
      ></span>
    </div>

    <!-- Floating diamonds -->
    <div
      class="floating-diamond diamond-one pointer-events-none absolute h-[11px] w-[11px] rotate-45 border border-[#8e6937]/42"
    ></div>

    <div
      class="floating-diamond diamond-two pointer-events-none absolute h-[11px] w-[11px] rotate-45 border border-[#8e6937]/42"
    ></div>

    <div
      class="floating-diamond diamond-three pointer-events-none absolute h-[11px] w-[11px] rotate-45 border border-[#8e6937]/42"
    ></div>

    <div
      class="floating-diamond diamond-four pointer-events-none absolute h-[11px] w-[11px] rotate-45 border border-[#8e6937]/42"
    ></div>

    <!-- Floating dots -->
    <div
      class="floating-dot dot-one pointer-events-none absolute h-1 w-1 rounded-full bg-[#8e6937] opacity-40"
    ></div>

    <div
      class="floating-dot dot-two pointer-events-none absolute h-1 w-1 rounded-full bg-[#8e6937] opacity-40"
    ></div>

    <div
      class="floating-dot dot-three pointer-events-none absolute h-1 w-1 rounded-full bg-[#8e6937] opacity-40"
    ></div>

    <div
      class="floating-dot dot-four pointer-events-none absolute h-1 w-1 rounded-full bg-[#8e6937] opacity-40"
    ></div>

    <div
      class="floating-dot dot-five pointer-events-none absolute h-1 w-1 rounded-full bg-[#8e6937] opacity-40"
    ></div>

    <!-- =========================================================
         SIDE DECORATIONS
    ========================================================== -->

    <div
      class="side-decoration side-left pointer-events-none absolute left-[5%] top-1/2 flex -translate-y-1/2 flex-col gap-[9px] opacity-35 max-[768px]:hidden"
    >
      <span class="h-px w-[34px] bg-[#8e6937]"></span>
      <span class="ml-2 h-px w-[18px] bg-[#8e6937]"></span>
      <span class="ml-[3px] h-px w-[26px] bg-[#8e6937]"></span>
    </div>

    <div
      class="side-decoration side-right pointer-events-none absolute right-[5%] top-1/2 flex -translate-y-1/2 flex-col gap-[9px] opacity-35 max-[768px]:hidden"
    >
      <span class="h-px w-[34px] bg-[#8e6937]"></span>
      <span class="ml-2 h-px w-[18px] bg-[#8e6937]"></span>
      <span class="ml-[3px] h-px w-[26px] bg-[#8e6937]"></span>
    </div>

    <!-- =========================================================
         OUTER FRAME
    ========================================================== -->

    <div
      class="pointer-events-none absolute inset-5 md:inset-8 max-[480px]:inset-3"
    >
      <div
        class="absolute inset-0 border border-[#8e6937]/15"
      ></div>

      <div
        class="corner corner-top-left absolute left-0 top-0 h-12 w-12 opacity-50 max-[480px]:h-9 max-[480px]:w-9"
      ></div>

      <div
        class="corner corner-top-right absolute right-0 top-0 h-12 w-12 rotate-90 opacity-50 max-[480px]:h-9 max-[480px]:w-9"
      ></div>

      <div
        class="corner corner-bottom-left absolute bottom-0 left-0 h-12 w-12 -rotate-90 opacity-50 max-[480px]:h-9 max-[480px]:w-9"
      ></div>

      <div
        class="corner corner-bottom-right absolute bottom-0 right-0 h-12 w-12 rotate-180 opacity-50 max-[480px]:h-9 max-[480px]:w-9"
      ></div>
    </div>

    <!-- =========================================================
         MAIN CONTENT
    ========================================================== -->

    <div
      class="relative z-20 flex min-h-screen items-center justify-center px-6 py-24 md:px-12 max-[480px]:px-3 max-[480px]:py-20"
    >
      <div class="w-full max-w-5xl">

        <!-- Central decoration -->

        <div
          class="central-decoration absolute left-1/2 top-[7%] z-[5] flex -translate-x-1/2 items-center gap-4 max-[768px]:top-[5%] max-[480px]:gap-2"
        >
          <div
            class="central-line h-px w-[42px] bg-[linear-gradient(to_right,transparent,rgba(142,105,55,0.6))] max-[768px]:w-7 max-[480px]:w-5"
          ></div>

          <div
            class="central-diamond-wrapper relative flex h-[26px] w-[26px] items-center justify-center max-[480px]:h-5 max-[480px]:w-5"
          >
            <div
              class="central-diamond absolute h-5 w-5 rotate-45 border border-[#8e6937] max-[480px]:h-4 max-[480px]:w-4"
            ></div>

            <div
              class="central-small-diamond h-[7px] w-[7px] rotate-45 bg-[#8e6937] max-[480px]:h-[5px] max-[480px]:w-[5px]"
            ></div>
          </div>

          <div
            class="central-circle h-[5px] w-[5px] rounded-full bg-[#8e6937] max-[480px]:h-1 max-[480px]:w-1"
          ></div>

          <div
            class="central-line central-line-right h-px w-[42px] bg-[linear-gradient(to_left,transparent,rgba(142,105,55,0.6))] max-[768px]:w-7 max-[480px]:w-5"
          ></div>
        </div>

        <!-- =====================================================
             INVITATION CARD
        ====================================================== -->

        <article
          class="invitation-card relative mx-auto w-full max-w-[850px] overflow-hidden border border-[#8e6937]/28 bg-[linear-gradient(135deg,rgba(255,253,248,0.94),rgba(250,244,233,0.84))] px-[55px] py-[70px] shadow-[0_25px_80px_rgba(70,48,28,0.09),inset_0_0_60px_rgba(142,105,55,0.025)] backdrop-blur-[14px] max-[768px]:px-[30px] max-[768px]:py-[58px] max-[480px]:px-[16px] max-[480px]:py-[48px]"
        >

          <div
            class="card-inner-frame pointer-events-none absolute inset-[14px] border border-[#8e6937]/11 max-[768px]:inset-[10px] max-[480px]:inset-[7px]"
          ></div>

          <!-- Card corners -->

          <div
            class="card-corner card-corner-tl absolute left-5 top-5 h-7 w-7 opacity-60 max-[768px]:left-4 max-[768px]:top-4 max-[480px]:left-3 max-[480px]:top-3"
          ></div>

          <div
            class="card-corner card-corner-tr absolute right-5 top-5 h-7 w-7 rotate-90 opacity-60 max-[768px]:right-4 max-[768px]:top-4 max-[480px]:right-3 max-[480px]:top-3"
          ></div>

          <div
            class="card-corner card-corner-bl absolute bottom-5 left-5 h-7 w-7 -rotate-90 opacity-60 max-[768px]:bottom-4 max-[768px]:left-4 max-[480px]:bottom-3 max-[480px]:left-3"
          ></div>

          <div
            class="card-corner card-corner-br absolute bottom-5 right-5 h-7 w-7 rotate-180 opacity-60 max-[768px]:bottom-4 max-[768px]:right-4 max-[480px]:bottom-3 max-[480px]:right-3"
          ></div>

          <!-- ===================================================
               EYEBROW
          ==================================================== -->

          <div
            class="invitation-eyebrow flex translate-y-5 items-center justify-center gap-[14px] text-center font-sans text-[10px] font-semibold tracking-[0.34em] text-[#8e6937] opacity-0 transition-all duration-700 ease-out [transition-delay:200ms] max-[480px]:gap-2 max-[480px]:text-[8px] max-[480px]:tracking-[0.18em]"
          >
            <span
              class="eyebrow-line h-px w-[34px] bg-[#8e6937]/45 max-[480px]:w-[18px]"
            ></span>

            <span>
              {{
                language === 'ar'
                  ? 'دعوة خاصة'
                  : 'UNE INVITATION PARTICULIÈRE'
              }}
            </span>

            <span
              class="eyebrow-line h-px w-[34px] bg-[#8e6937]/45 max-[480px]:w-[18px]"
            ></span>
          </div>

          <!-- ===================================================
               INTRODUCTION
          ==================================================== -->

          <p
            class="invitation-intro mt-6 translate-y-5 text-center font-sans text-[25px] font-medium tracking-[0.3em] text-[#705536] opacity-0 transition-all duration-700 ease-out [transition-delay:350ms] max-[768px]:text-[17px] max-[480px]:mt-5 max-[480px]:px-2 max-[480px]:text-[12px] max-[480px]:leading-6 max-[480px]:tracking-[0.12em]"
          >
            {{
              language === 'ar'
                ? 'تتشرف عائلة العريس وعائلة العروس'
                : 'La famille du marié et la famille de la mariée.'
            }}
          </p>

          <!-- ===================================================
               MAIN TITLE
          ==================================================== -->

          <h2
            class="invitation-title mx-auto mt-[22px] max-w-[680px] translate-y-7 text-center font-serif text-[clamp(1.8rem,4vw,3.2rem)] font-medium leading-[1.08] text-[#30241c] opacity-0 blur-[5px] transition-all duration-1000 ease-out [transition-delay:500ms] max-[768px]:max-w-[580px] max-[480px]:mt-5 max-[480px]:px-2 max-[480px]:text-[1.65rem] max-[380px]:text-[1.5rem]"
          >
            {{
              language === 'ar'
                ? 'بدعوتكم لمشاركتهم فرحة حفل الزواج'
                : 'ont l’honneur de vous inviter à partager la joie de leur mariage'
            }}
          </h2>

          <br />

          <!-- Gold divider -->

          <div
            class="gold-divider mx-auto my-[30px] flex origin-center scale-x-50 items-center justify-center gap-3 opacity-0 transition-all duration-700 ease-out [transition-delay:700ms] max-[480px]:my-[24px] max-[480px]:gap-2"
          >
            <span
              class="h-px w-[70px] bg-[linear-gradient(to_right,transparent,rgba(142,105,55,0.55))] max-[480px]:w-[30px]"
            ></span>

            <div
              class="divider-diamond h-[9px] w-[9px] rotate-45 border border-[#8e6937] max-[480px]:h-[7px] max-[480px]:w-[7px]"
            ></div>

            <span
              class="h-px w-[70px] bg-[linear-gradient(to_left,transparent,rgba(142,105,55,0.55))] max-[480px]:w-[30px]"
            ></span>
          </div>

          <!-- ===================================================
               MESSAGE
          ==================================================== -->

          <p
            class="invitation-message mx-auto max-w-[610px] translate-y-6 text-center font-sans text-[14px] leading-[2] text-[#5c4938] opacity-0 transition-all duration-700 ease-out [transition-delay:850ms] max-[768px]:text-[13px] max-[768px]:leading-[1.9] max-[480px]:px-2 max-[480px]:text-[12px] max-[480px]:leading-[2]"
          >
            {{
              language === 'ar'
                ? 'راجين من الله أن تكتمل فرحتهم بحضوركم وتشريفكم لهذه المناسبة السعيدة.'
                : 'Prions Dieu de parfaire leur bonheur par votre présence et votre bienveillante participation à cette heureuse occasion.'
            }}
          </p>

          <!-- ===================================================
               NAMES
          ==================================================== -->

          <div
            class="names-wrapper mt-12 flex translate-y-[30px] items-center justify-center gap-[42px] opacity-0 transition-all duration-700 ease-out [transition-delay:1000ms] max-[768px]:gap-6 max-[480px]:mt-9 max-[480px]:gap-3"
          >

            <!-- Groom -->

            <div class="person min-w-0 flex-1 text-center">
              

              <h3
                class="whitespace-nowrap font-serif text-[clamp(2.1rem,5vw,3.6rem)] font-medium leading-none text-[#30241c] max-[768px]:text-[2.7rem] max-[480px]:text-[2rem] max-[380px]:text-[1.8rem]"
              >
                {{ language === 'ar' ? 'العريس' : 'Le marié' }}
              </h3>
            </div>

            <!-- Separator -->

            <div
              class="names-ampersand shrink-0 font-serif text-5xl text-[#8e6937] max-[768px]:text-4xl max-[480px]:text-[2rem]"
            >
              &amp;
            </div>

            <!-- Bride -->

            <div class="person min-w-0 flex-1 text-center">
              

              <h3
                class="whitespace-nowrap font-serif text-[clamp(2.1rem,5vw,3.6rem)] font-medium leading-none text-[#30241c] max-[768px]:text-[2.7rem] max-[480px]:text-[2rem] max-[380px]:text-[1.8rem]"
              >
                {{ language === 'ar' ? 'العروس' : 'La mariée' }}
              </h3>
            </div>

          </div>

          <!-- ===================================================
               DATES
          ==================================================== -->

          <div
            class="date-wrapper mt-12 flex translate-y-[25px] items-center justify-center gap-8 opacity-0 transition-all duration-700 ease-out [transition-delay:1150ms] max-[768px]:gap-5 max-[480px]:mt-9 max-[480px]:gap-2"
          >

            <!-- Left line -->

            <span
              class="date-line h-px w-[60px] shrink-0 bg-[#8e6937]/30 max-[768px]:w-7 max-[480px]:w-3"
            ></span>

            <!-- =================================================
                 CEREMONY
            ================================================== -->

            <div
              class="date-content min-w-0 flex flex-col items-center gap-2 text-center font-sans text-[#705536]"
            >
              <span
                class="whitespace-nowrap text-[8px] tracking-[0.2em] text-[#8e6937] max-[480px]:text-[7px] max-[480px]:tracking-[0.08em]"
              >
              {{
                  language === 'ar'
                    ? 'العشاء'
                    : 'DÎNER'
                }}
              </span>

              <div
                class="date-info flex items-center gap-[9px] max-[600px]:flex-col max-[600px]:gap-0.5"
              >
                <span
                  class="date-day whitespace-nowrap text-[9px] tracking-[0.2em] max-[480px]:text-[8px] max-[480px]:tracking-[0.05em]"
                >
                {{
                    language === 'ar'
                      ? 'الخميس'
                      : 'JEUDI'
                  }}
                </span>

                <div
                  class="flex items-center gap-[9px] max-[480px]:gap-[5px]"
                >
                  <span
                    class="date-number font-serif text-[2rem] text-[#30241c] max-[480px]:text-[1.7rem]"
                  >
                    15
                  </span>

                  <span
                    class="date-month whitespace-nowrap text-[10px] tracking-[0.15em] max-[480px]:text-[8px] max-[480px]:tracking-[0.05em]"
                  >
                    {{
                      language === 'ar'
                        ? 'جويلية'
                        : 'JUILLET'
                    }}
                  </span>

                  <span
                    class="date-year text-[10px] tracking-[0.15em] max-[480px]:text-[8px] max-[480px]:tracking-[0.05em]"
                  >
                    2030
                  </span>
                </div>
              </div>
            </div>

            <!-- Central separator -->

            <span
              class="date-separator h-10 w-px shrink-0 bg-[#8e6937]/25 max-[480px]:h-8"
            ></span>

            <!-- =================================================
                 DINNER
            ================================================== -->

            <div
              class="date-content min-w-0 flex flex-col items-center gap-2 text-center font-sans text-[#705536]"
            >
              <span
                class="whitespace-nowrap text-[8px] tracking-[0.2em] text-[#8e6937] max-[480px]:text-[7px] max-[480px]:tracking-[0.08em]"
              >
              {{
                  language === 'ar'
                    ? 'عقد القران'
                    : 'CÉRÉMONIE DE MARIAGE'
                }}
              </span>

              <div
                class="date-info flex items-center gap-[9px] max-[600px]:flex-col max-[600px]:gap-0.5"
              >
                <span
                  class="date-day whitespace-nowrap text-[9px] tracking-[0.2em] max-[480px]:text-[8px] max-[480px]:tracking-[0.05em]"
                >
                {{
                    language === 'ar'
                      ? 'الجمعة'
                      : 'VENDREDI'
                  }}
                </span>

                <div
                  class="flex items-center gap-[9px] max-[480px]:gap-[5px]"
                >
                  <span
                    class="date-number font-serif text-[2rem] text-[#30241c] max-[480px]:text-[1.7rem]"
                  >
                    16
                  </span>

                  <span
                    class="date-month whitespace-nowrap text-[10px] tracking-[0.15em] max-[480px]:text-[8px] max-[480px]:tracking-[0.05em]"
                  >
                    {{
                      language === 'ar'
                        ? 'جويلية'
                        : 'JUILLET'
                    }}
                  </span>

                  <span
                    class="date-year text-[10px] tracking-[0.15em] max-[480px]:text-[8px] max-[480px]:tracking-[0.05em]"
                  >
                    2030
                  </span>
                </div>
              </div>
            </div>

            <!-- Right line -->

            <span
              class="date-line h-px w-[60px] shrink-0 bg-[#8e6937]/30 max-[768px]:w-7 max-[480px]:w-3"
            ></span>

          </div>

          <!-- ===================================================
               CLOSING MESSAGE
          ==================================================== -->

          <p
            class="invitation-closing mx-auto mt-[42px] max-w-[560px] translate-y-5 text-center font-sans text-[12px] leading-[1.9] text-[#6a5645] opacity-0 transition-all duration-700 ease-out [transition-delay:1300ms] max-[768px]:text-[11px] max-[480px]:mt-8 max-[480px]:px-2 max-[480px]:leading-[2]"
          >
            {{
              language === 'ar'
                ? 'حضوركم يزيد هذه المناسبة فرحًا، ويشرّفنا أن نشارككم هذه اللحظات السعيدة.'
                : 'Votre présence ajoutera à cette occasion une joie particulière, et nous serons heureux de partager avec vous ces précieux moments.'
            }}
          </p>

          <!-- ===================================================
               BOTTOM SYMBOL
          ==================================================== -->

          <div
            class="bottom-symbol mt-[35px] flex translate-y-[15px] items-center justify-center gap-[13px] opacity-0 transition-all duration-700 ease-out [transition-delay:1450ms] max-[480px]:mt-7"
          >
            <span
              class="h-px w-[45px] bg-[#8e6937]/40 max-[480px]:w-7"
            ></span>

            <div
              class="symbol-center flex h-[13px] w-[13px] rotate-45 items-center justify-center border border-[#8e6937]"
            >
              <div
                class="h-1 w-1 bg-[#8e6937]"
              ></div>
            </div>

            <span
              class="h-px w-[45px] bg-[#8e6937]/40 max-[480px]:w-7"
            ></span>
          </div>

          <!-- ===================================================
               WELCOME
          ==================================================== -->

          <p
            class="welcome-text mt-4 translate-y-[15px] text-center font-sans text-[9px] font-semibold tracking-[0.3em] text-[#8e6937] opacity-0 transition-all duration-700 ease-out [transition-delay:1550ms] max-[480px]:text-[8px] max-[480px]:tracking-[0.16em]"
          >
            {{
              language === 'ar'
                ? 'أهلاً وسهلاً بكم'
                : 'BIENVENUE À VOUS'
            }}
          </p>

        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
import {
  onMounted,
  onBeforeUnmount,
  ref,
} from 'vue'

/*
  تعريف خصائص المكوّن
  Français : Définition des propriétés du composant
*/
defineProps({
  language: {
    type: String,
    default: 'fr',
  },
})

/*
  مرجع القسم وحالة ظهوره
  Français : Référence de la section et état de visibilité
*/
const sectionRef = ref(null)
const isVisible = ref(false)

/*
  مراقب ظهور القسم
  Français : Observateur de visibilité
*/
let observer = null

/*
  تشغيل IntersectionObserver
  Français : Initialisation de l’observateur
*/
onMounted(() => {
  observer = new IntersectionObserver(
    ([entry]) => {
      if (!entry) return

      isVisible.value = entry.isIntersecting
    },
    {
      threshold: 0.22,
    },
  )

  if (sectionRef.value) {
    observer.observe(sectionRef.value)
  }
})

/*
  تنظيف المراقب
  Français : Nettoyage de l’observateur
*/
onBeforeUnmount(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<style scoped>

/* ============================================================
   SECTION
============================================================ */

.invitation-section {
  isolation: isolate;
}

/* ============================================================
   AMBIENT LIGHT
============================================================ */

.ambient-light {
  pointer-events: none;
  filter: blur(90px);
  opacity: 0.18;

  transition:
    transform 3.5s cubic-bezier(0.22, 1, 0.36, 1),
    opacity 2s ease;

  will-change: transform;
}

.ambient-light-one {
  width: 420px;
  height: 420px;
  top: 5%;
  left: -180px;
  background: rgba(168, 130, 74, 0.22);
  animation: ambientFloatOne 16s cubic-bezier(0.45, 0, 0.55, 1) infinite;
}

.ambient-light-two {
  width: 360px;
  height: 360px;
  right: -150px;
  top: 38%;
  background: rgba(112, 85, 54, 0.14);
  animation: ambientFloatTwo 19s cubic-bezier(0.45, 0, 0.55, 1) infinite;
}

.ambient-light-three {
  width: 300px;
  height: 300px;
  left: 42%;
  bottom: -150px;
  background: rgba(155, 117, 63, 0.13);
  animation: ambientFloatThree 18s cubic-bezier(0.45, 0, 0.55, 1) infinite;
}

@keyframes ambientFloatOne {
  0%,
  100% {
    transform: translate3d(0, 0, 0) scale(1);
  }

  50% {
    transform: translate3d(80px, 45px, 0) scale(1.06);
  }
}

@keyframes ambientFloatTwo {
  0%,
  100% {
    transform: translate3d(0, 0, 0) scale(1);
  }

  50% {
    transform: translate3d(-70px, -45px, 0) scale(1.05);
  }
}

@keyframes ambientFloatThree {
  0%,
  100% {
    transform: translate3d(0, 0, 0) scale(1);
  }

  50% {
    transform: translate3d(40px, -60px, 0) scale(1.06);
  }
}

/* ============================================================
   TUNISIAN PATTERN
============================================================ */

.tunisian-pattern {
  opacity: 0.075;

  background-image:
    linear-gradient(
      45deg,
      transparent 42%,
      #705536 43%,
      #705536 47%,
      transparent 48%
    ),
    linear-gradient(
      -45deg,
      transparent 42%,
      #705536 43%,
      #705536 47%,
      transparent 48%
    );

  background-size: 72px 72px;
  animation: patternMove 34s linear infinite;
  will-change: transform;
}

@keyframes patternMove {
  from {
    transform: translate3d(0, 0, 0);
  }

  to {
    transform: translate3d(72px, 72px, 0);
  }
}

/* ============================================================
   DOT PATTERN
============================================================ */

.dot-pattern {
  opacity: 0.18;

  background-image:
    radial-gradient(
      #8e6937 0.8px,
      transparent 0.8px
    );

  background-size: 28px 28px;
  animation: dotsMove 28s linear infinite;
  will-change: transform;
}

@keyframes dotsMove {
  from {
    transform: translate3d(0, 0, 0);
  }

  to {
    transform: translate3d(0, 28px, 0);
  }
}

/* ============================================================
   TOP ORNAMENT
============================================================ */

.top-ornament span {
  animation: topOrnamentPulse 4.5s ease-in-out infinite;
}

.top-ornament span:nth-child(2) {
  animation-delay: 0.45s;
}

.top-ornament span:nth-child(3) {
  animation-delay: 0.9s;
}

@keyframes topOrnamentPulse {
  0%,
  100% {
    transform: rotate(45deg) scale(1);
    opacity: 0.65;
  }

  50% {
    transform: rotate(45deg) scale(1.2);
    opacity: 1;
  }
}

/* ============================================================
   FLOATING DIAMONDS
============================================================ */

.diamond-one {
  top: 22%;
  left: 8%;
  animation: diamondFloatOne 11s cubic-bezier(0.45, 0, 0.55, 1) infinite;
  will-change: transform;
}

.diamond-two {
  top: 31%;
  right: 9%;
  animation: diamondFloatTwo 13s cubic-bezier(0.45, 0, 0.55, 1) infinite;
  will-change: transform;
}

.diamond-three {
  bottom: 23%;
  left: 12%;
  animation: diamondFloatThree 14s cubic-bezier(0.45, 0, 0.55, 1) infinite;
  will-change: transform;
}

.diamond-four {
  bottom: 16%;
  right: 14%;
  animation: diamondFloatFour 12s cubic-bezier(0.45, 0, 0.55, 1) infinite;
  will-change: transform;
}

@keyframes diamondFloatOne {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(45deg);
  }

  50% {
    transform: translate3d(14px, -18px, 0) rotate(105deg);
  }
}

@keyframes diamondFloatTwo {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(45deg);
  }

  50% {
    transform: translate3d(-18px, 16px, 0) rotate(105deg);
  }
}

@keyframes diamondFloatThree {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(45deg);
  }

  50% {
    transform: translate3d(18px, -15px, 0) rotate(105deg);
  }
}

@keyframes diamondFloatFour {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(45deg);
  }

  50% {
    transform: translate3d(-14px, -19px, 0) rotate(135deg);
  }
}

/* ============================================================
   FLOATING DOTS
============================================================ */

.dot-one {
  top: 18%;
  left: 22%;
  animation: dotFloat 9s ease-in-out infinite;
}

.dot-two {
  top: 48%;
  right: 13%;
  animation: dotFloat 11s ease-in-out infinite 1s;
}

.dot-three {
  bottom: 20%;
  left: 23%;
  animation: dotFloat 10s ease-in-out infinite 2s;
}

.dot-four {
  bottom: 34%;
  right: 20%;
  animation: dotFloat 12s ease-in-out infinite 1.5s;
}

.dot-five {
  top: 66%;
  left: 9%;
  animation: dotFloat 13s ease-in-out infinite 0.5s;
}

@keyframes dotFloat {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
    opacity: 0.25;
  }

  50% {
    transform: translate3d(0, -16px, 0);
    opacity: 0.6;
  }
}

/* ============================================================
   OUTER FRAME CORNERS
============================================================ */

.corner::before,
.corner::after {
  content: "";
  position: absolute;
  background: #8e6937;
}

.corner::before {
  width: 48px;
  height: 1px;
}

.corner::after {
  width: 1px;
  height: 48px;
}

/* ============================================================
   CENTRAL DECORATION
============================================================ */

.central-diamond {
  animation: centralDiamondRotate 18s linear infinite;
  will-change: transform;
}

.central-small-diamond {
  animation: centralSmallPulse 4s ease-in-out infinite;
}

.central-circle {
  animation: circlePulse 3.5s ease-in-out infinite;
}

@keyframes centralDiamondRotate {
  from {
    transform: rotate(45deg);
  }

  to {
    transform: rotate(405deg);
  }
}

@keyframes centralSmallPulse {
  0%,
  100% {
    transform: rotate(45deg) scale(1);
    opacity: 0.8;
  }

  50% {
    transform: rotate(45deg) scale(1.25);
    opacity: 1;
  }
}

@keyframes circlePulse {
  0%,
  100% {
    transform: scale(1);
    opacity: 0.5;
  }

  50% {
    transform: scale(1.5);
    opacity: 0.9;
  }
}

/* ============================================================
   CARD CORNERS
============================================================ */

.card-corner::before,
.card-corner::after {
  content: "";
  position: absolute;
  background: #8e6937;
}

.card-corner::before {
  width: 28px;
  height: 1px;
}

.card-corner::after {
  width: 1px;
  height: 28px;
}

/* ============================================================
   DIVIDER
============================================================ */

.divider-diamond {
  animation: dividerPulse 4s ease-in-out infinite;
}

@keyframes dividerPulse {
  0%,
  100% {
    transform: rotate(45deg) scale(1);
    opacity: 0.7;
  }

  50% {
    transform: rotate(45deg) scale(1.18);
    opacity: 1;
  }
}

/* ============================================================
   NAMES SEPARATOR
============================================================ */

.names-ampersand {
  animation: ampersandGlow 4s ease-in-out infinite;
}

@keyframes ampersandGlow {
  0%,
  100% {
    opacity: 0.65;
    transform: scale(1);
    text-shadow: 0 0 0 rgba(142, 105, 55, 0);
  }

  50% {
    opacity: 1;
    transform: scale(1.05);
    text-shadow: 0 0 18px rgba(142, 105, 55, 0.22);
  }
}

/* ============================================================
   BOTTOM SYMBOL
============================================================ */

.symbol-center {
  animation: symbolRotate 12s linear infinite;
  will-change: transform;
}

@keyframes symbolRotate {
  from {
    transform: rotate(45deg);
  }

  to {
    transform: rotate(405deg);
  }
}

/* ============================================================
   ACTIVE STATE
============================================================ */

.invitation-active .invitation-card {
  opacity: 1;
  transform: translateY(0) scale(1);
  filter: blur(0);
}

.invitation-card {
  opacity: 0;

  transform:
    translateY(70px)
    scale(0.97);

  filter: blur(8px);

  transition:
    opacity 1.15s cubic-bezier(0.16, 1, 0.3, 1),
    transform 1.35s cubic-bezier(0.16, 1, 0.3, 1),
    filter 1.15s cubic-bezier(0.16, 1, 0.3, 1);

  will-change: opacity, transform, filter;
}

.invitation-active .invitation-eyebrow,
.invitation-active .invitation-intro,
.invitation-active .invitation-title,
.invitation-active .gold-divider,
.invitation-active .invitation-message,
.invitation-active .names-wrapper,
.invitation-active .date-wrapper,
.invitation-active .invitation-closing,
.invitation-active .bottom-symbol,
.invitation-active .welcome-text {
  opacity: 1;
  transform: translateY(0);
}

.invitation-active .invitation-title {
  filter: blur(0);
}

.invitation-active .gold-divider {
  transform: scaleX(1);
}

/* ============================================================
   ARABIC
============================================================ */

[dir="rtl"] .invitation-card {
  font-family: "Tahoma", "Arial", sans-serif;
}

[dir="rtl"] .invitation-title,
[dir="rtl"] .person h3,
[dir="rtl"] .names-ampersand,
[dir="rtl"] .date-number {
  font-family: "Amiri", "Noto Naskh Arabic", serif;
}

[dir="rtl"] .invitation-message,
[dir="rtl"] .invitation-closing {
  line-height: 2.2;
}

[dir="rtl"] .invitation-eyebrow,
[dir="rtl"] .person-label,
[dir="rtl"] .date-day,
[dir="rtl"] .date-month,
[dir="rtl"] .date-year,
[dir="rtl"] .welcome-text {
  letter-spacing: 0;
}

/* ============================================================
   TABLET
============================================================ */

@media (max-width: 900px) {
  .ambient-light-one {
    width: 340px;
    height: 340px;
  }

  .ambient-light-two {
    width: 300px;
    height: 300px;
  }

  .ambient-light-three {
    width: 260px;
    height: 260px;
  }
}

/* ============================================================
   MOBILE
============================================================ */

@media (max-width: 768px) {
  .side-decoration {
    display: none;
  }

  .invitation-section {
    min-height: auto;
  }

  .invitation-card {
    box-shadow:
      0 18px 55px rgba(70, 48, 28, 0.08),
      inset 0 0 45px rgba(142, 105, 55, 0.025);
  }

  .tunisian-pattern {
    background-size: 58px 58px;
  }

  .dot-pattern {
    background-size: 24px 24px;
  }

  .date-content {
    flex-shrink: 1;
  }
}

/* ============================================================
   MOBILE DATE FIX
   تحسين عرض التاريخ على الهاتف
============================================================ */

@media (max-width: 480px) {
  .ambient-light-one {
    width: 260px;
    height: 260px;
  }

  .ambient-light-two {
    width: 240px;
    height: 240px;
  }

  .ambient-light-three {
    width: 220px;
    height: 220px;
  }

  .top-ornament {
    top: 4%;
    transform: translateX(-50%) scale(0.8);
  }

  /*
    التاريخ يأخذ تقريباً نصف البطاقة لكل مناسبة.
    Français : Chaque date reçoit presque la moitié de la largeur.
  */
  .date-wrapper {
    width: 100%;
    gap: 0;
    justify-content: space-between;
  }

  /*
    إخفاء الخطوط الجانبية فقط على الهاتف
    حتى لا تستهلك مساحة التاريخ.
  */
  .date-line {
    display: none;
  }

  /*
    إعطاء كل تاريخ مساحة مستقلة أكبر.
  */
  .date-content {
    width: calc(50% - 10px);
    max-width: none;
    flex: 0 0 calc(50% - 10px);
  }

  /*
    الحفاظ على الفاصل بين التاريخين.
  */
  .date-separator {
    display: block;
    flex-shrink: 0;
  }

  .date-info {
    width: 100%;
  }

  .card-corner::before {
    width: 22px;
  }

  .card-corner::after {
    height: 22px;
  }
}

/* ============================================================
   VERY SMALL MOBILE
   320px / 360px
============================================================ */

@media (max-width: 380px) {
  .invitation-card {
    padding-left: 12px;
    padding-right: 12px;
  }

  .invitation-intro {
    font-size: 11px !important;
  }

  .invitation-title {
    font-size: 1.45rem !important;
  }

  .invitation-message {
    font-size: 11px !important;
  }

  .names-wrapper {
    gap: 7px;
  }

  .person-label {
    font-size: 7px !important;
  }

  .person h3 {
    font-size: 1.7rem !important;
  }

  .names-ampersand {
    font-size: 1.8rem !important;
  }

  /*
    على 320/360px نزيد عرض التاريخين أكثر.
  */
  .date-wrapper {
    gap: 0;
  }

  .date-content {
    width: calc(50% - 7px);
    max-width: none;
    flex-basis: calc(50% - 7px);
  }

  .date-content > span:first-child {
    font-size: 6px;
  }

  .date-number {
    font-size: 1.45rem !important;
  }

  .date-month,
  .date-year,
  .date-day {
    font-size: 7px !important;
  }

  .date-separator {
    height: 28px !important;
  }

  .welcome-text {
    font-size: 7px !important;
  }
}

/* ============================================================
   REDUCED MOTION
============================================================ */

@media (prefers-reduced-motion: reduce) {
  .tunisian-pattern,
  .dot-pattern,
  .ambient-light,
  .floating-diamond,
  .floating-dot,
  .top-ornament span,
  .central-diamond,
  .central-small-diamond,
  .central-circle,
  .divider-diamond,
  .names-ampersand,
  .symbol-center {
    animation: none !important;
  }

  .invitation-card,
  .invitation-eyebrow,
  .invitation-intro,
  .invitation-title,
  .gold-divider,
  .invitation-message,
  .names-wrapper,
  .date-wrapper,
  .invitation-closing,
  .bottom-symbol,
  .welcome-text {
    transition: none !important;
  }
}

</style>