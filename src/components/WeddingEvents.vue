<template>
  <section
    id="wedding-events"
    ref="sectionRef"
    class="relative isolate min-h-screen overflow-hidden bg-[#e7dfd1] text-[#30241c]"
    :class="{ 'events-active': isVisible }"
    :dir="language === 'ar' ? 'rtl' : 'ltr'"
  >
    <!-- =========================================================
         BACKGROUND
    ========================================================== -->

    <div class="absolute inset-0 bg-[#e7dfd1]"></div>

    <!-- Soft lights -->
    <div
      class="events-glow events-glow-top absolute left-[20%] top-[-180px] h-[430px] w-[430px] rounded-full bg-[rgba(155,117,63,0.22)]"
    ></div>

    <div
      class="events-glow events-glow-bottom absolute bottom-[-170px] right-[15%] h-[380px] w-[380px] rounded-full bg-[rgba(112,85,54,0.16)]"
    ></div>

    <!-- Moving geometric pattern -->
    <div
      class="events-pattern pointer-events-none absolute inset-[-15%] opacity-[0.055]"
    ></div>

    <!-- Vertical decorative pattern -->
    <div
      class="vertical-pattern pointer-events-none absolute bottom-[15%] left-[8%] top-[15%] w-px opacity-[0.35] max-[900px]:hidden"
    ></div>

    <div
      class="vertical-pattern pointer-events-none absolute bottom-[15%] right-[8%] top-[15%] w-px opacity-[0.35] max-[900px]:hidden"
    ></div>

    <!-- =========================================================
         FLOATING DECORATIONS
    ========================================================== -->

    <div
      class="floating-square floating-square-1 pointer-events-none absolute left-[14%] top-[18%] h-[13px] w-[13px]"
    ></div>

    <div
      class="floating-square floating-square-2 pointer-events-none absolute right-[10%] top-[52%] h-[13px] w-[13px]"
    ></div>

    <div
      class="floating-square floating-square-3 pointer-events-none absolute bottom-[16%] left-[17%] h-[13px] w-[13px]"
    ></div>

    <div
      class="floating-circle floating-circle-1 pointer-events-none absolute right-[19%] top-[28%] h-[6px] w-[6px]"
    ></div>

    <div
      class="floating-circle floating-circle-2 pointer-events-none absolute bottom-[28%] right-[24%] h-[6px] w-[6px]"
    ></div>

    <div
      class="floating-circle floating-circle-3 pointer-events-none absolute left-[10%] top-[65%] h-[6px] w-[6px]"
    ></div>

    <div
      class="floating-cross floating-cross-1 pointer-events-none absolute right-[28%] top-[21%]"
    >
      +
    </div>

    <div
      class="floating-cross floating-cross-2 pointer-events-none absolute bottom-[22%] left-[27%]"
    >
      +
    </div>

    <div
      class="floating-cross floating-cross-3 pointer-events-none absolute right-[12%] top-[72%]"
    >
      +
    </div>

    <!-- =========================================================
         OUTER FRAME
    ========================================================== -->

    <div
      class="events-frame pointer-events-none absolute inset-[22px] border border-[rgba(142,105,55,0.12)]"
    >
      <div class="frame-corner frame-tl"></div>
      <div class="frame-corner frame-tr"></div>
      <div class="frame-corner frame-bl"></div>
      <div class="frame-corner frame-br"></div>
    </div>

    <!-- =========================================================
         CONTENT
    ========================================================== -->

    <div
      class="relative z-20 mx-auto flex min-h-screen w-full max-w-6xl flex-col justify-center px-6 py-24 md:px-10 max-[700px]:min-h-0 max-[700px]:px-5 max-[700px]:py-20 max-[430px]:px-4 max-[430px]:py-[72px]"
    >
      <!-- =====================================================
           HEADER
      ====================================================== -->

      <header
        class="events-header mb-[70px] text-center max-[700px]:mb-[48px] max-[430px]:mb-[42px]"
      >
        <!-- Label -->
        <div
          class="reveal-label flex items-center justify-center gap-[13px] font-['Montserrat',sans-serif] text-[10px] font-semibold tracking-[0.32em] text-[#8e6937] max-[430px]:gap-2 max-[430px]:text-[8px] max-[430px]:tracking-[0.16em]"
        >
          <span
            class="h-px w-8 bg-[rgba(142,105,55,0.45)] max-[430px]:w-5"
          ></span>

          <span>
            {{
              language === 'ar'
                ? 'برنامج اليوم'
                : 'LE PROGRAMME'
            }}
          </span>

          <span
            class="h-px w-8 bg-[rgba(142,105,55,0.45)] max-[430px]:w-5"
          ></span>
        </div>

        <!-- Intro -->
        <p
          class="reveal-intro mt-[22px] font-['Montserrat',sans-serif] text-[10px] tracking-[0.27em] text-[#705536] max-[430px]:mt-[18px] max-[430px]:text-[9px] max-[430px]:tracking-[0.14em]"
          :class="{
            'font-arabic text-sm tracking-normal sm:text-base':
              language === 'ar'
          }"
        >
          {{
            language === 'ar'
              ? 'لحظات نعيشها معًا'
              : 'LES MOMENTS À PARTAGER'
          }}
        </p>

        <!-- Title -->
        <h2
          class="reveal-title mt-[14px] font-['Cormorant_Garamond',Georgia,serif] text-[clamp(2.5rem,6vw,4.5rem)] font-medium leading-none text-[#30241c] max-[700px]:text-[2.7rem] max-[430px]:mt-3 max-[430px]:text-[clamp(2rem,9vw,2.35rem)] max-[430px]:leading-[1.12]"
          :class="{
            'font-arabic leading-[1.5] max-[430px]:leading-[1.6]':
              language === 'ar'
          }"
        >
          {{
            language === 'ar'
              ? 'مواعيد فرحتنا'
              : 'Les rendez-vous de notre union'
          }}
        </h2>

        <!-- Description -->
        <p
          class="reveal-description mx-auto mt-[22px] max-w-[570px] font-['Montserrat',sans-serif] text-[13px] leading-[1.9] text-[#685545] max-[700px]:text-[12px] max-[430px]:mt-[18px] max-[430px]:px-2 max-[430px]:text-[11px] max-[430px]:leading-[1.95]"
          :class="{
            'font-arabic text-[14px] leading-[2.1] max-[430px]:text-[12px] max-[430px]:leading-[2]':
              language === 'ar'
          }"
        >
          {{
            language === 'ar'
              ? 'يسعدنا أن نشارككم هذه اللحظات الجميلة في موعدي فرحتنا.'
              : 'Nous avons le plaisir de vous retrouver pour partager ensemble ces deux beaux moments.'
          }}
        </p>

        <!-- ===================================================
             COUNTDOWN
        ==================================================== -->

        <div class="countdown-wrapper mt-[35px] max-[430px]:mt-[28px]">
          <p
            class="font-['Montserrat',sans-serif] text-[10px] font-semibold tracking-[0.28em] text-[#8e6937] max-[430px]:text-[8px] max-[430px]:tracking-[0.14em]"
            :class="{
              'font-arabic text-sm tracking-normal':
                language === 'ar'
            }"
          >
            {{
              language === 'ar'
                ? 'الوقت المتبقي حتى موعدنا'
                : 'LE COMPTE À REBOURS'
            }}
          </p>

          <!-- Active countdown -->
          <div
            v-if="!isDatePassed"
            class="countdown-big mt-[20px] max-[700px]:mt-[16px] max-[430px]:mt-[14px]"
          >
            <!-- DAYS -->
            <div class="countdown-big-item">
              <strong>
                {{ formatNumber(countdown.days) }}
              </strong>

              <span>
                {{
                  language === 'ar'
                    ? 'يوم'
                    : 'JOURS'
                }}
              </span>
            </div>

            <div class="countdown-big-separator">
              :
            </div>

            <!-- HOURS -->
            <div class="countdown-big-item">
              <strong>
                {{ formatNumber(countdown.hours) }}
              </strong>

              <span>
                {{
                  language === 'ar'
                    ? 'ساعة'
                    : 'HEURES'
                }}
              </span>
            </div>

            <div class="countdown-big-separator">
              :
            </div>

            <!-- MINUTES -->
            <div class="countdown-big-item">
              <strong>
                {{ formatNumber(countdown.minutes) }}
              </strong>

              <span>
                {{
                  language === 'ar'
                    ? 'دقيقة'
                    : 'MINUTES'
                }}
              </span>
            </div>

            <div class="countdown-big-separator">
              :
            </div>

            <!-- SECONDS -->
            <div class="countdown-big-item">
              <strong>
                {{ formatNumber(countdown.seconds) }}
              </strong>

              <span>
                {{
                  language === 'ar'
                    ? 'ثانية'
                    : 'SECONDES'
                }}
              </span>
            </div>
          </div>

          <!-- Date passed -->
          <div
            v-else
            class="countdown-passed max-[430px]:mx-2 max-[430px]:px-4 max-[430px]:py-3"
            :class="{
              'font-arabic tracking-normal':
                language === 'ar'
            }"
          >
            {{
              language === 'ar'
                ? 'حلّ موعدنا الجميل'
                : 'Notre belle date est arrivée'
            }}
          </div>

          <!-- Dynamic date -->
          <p
            class="countdown-date mt-[15px] font-['Montserrat',sans-serif] text-[10px] font-semibold tracking-[0.22em] text-[#705536] max-[430px]:mt-3 max-[430px]:px-2 max-[430px]:text-[8px] max-[430px]:leading-[1.8] max-[430px]:tracking-[0.08em]"
            :class="{
              'font-arabic tracking-normal':
                language === 'ar'
            }"
          >
            {{ formattedEventDate }}
          </p>
        </div>

        <!-- Divider -->
        <div
          class="header-divider mt-7 flex items-center justify-center gap-3 max-[430px]:mt-6 max-[430px]:gap-2"
        >
          <span></span>

          <div class="header-diamond"></div>

          <span></span>
        </div>
      </header>


      <!-- =====================================================
           TIMELINE
      ====================================================== -->

      <div class="timeline-wrapper relative w-full">

        <!-- Central line -->
        <div
          class="timeline-line absolute bottom-0 left-1/2 top-0 w-px -translate-x-1/2 bg-[rgba(142,105,55,0.18)] max-[700px]:left-[15px] max-[700px]:translate-x-0 max-[430px]:left-[12px]"
        >
          <div
            class="timeline-progress h-0 w-full bg-[linear-gradient(to_bottom,#8e6937,#b39563,#8e6937)]"
          ></div>
        </div>


        <!-- ===================================================
             EVENT 1
        ==================================================== -->

        <article
          class="event-row relative grid min-h-[240px] grid-cols-[1fr_80px_1fr] items-center max-[900px]:grid-cols-[1fr_55px_1fr] max-[700px]:mb-[25px] max-[700px]:min-h-[210px] max-[700px]:grid-cols-[30px_1fr] max-[430px]:mb-[20px] max-[430px]:min-h-[190px] max-[430px]:grid-cols-[25px_1fr]"
        >
          <div class="event-content event-left-content">

            <div
              class="event-time text-right max-[700px]:text-left"
            >
              19:30
            </div>

            <div class="event-card">

              <div class="event-card-top">

                <span class="event-number">
                  01
                </span>

                <div class="event-icon">

                  <!-- Dinner icon -->
                  <svg
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    aria-hidden="true"
                  >
                    <path
                      d="M7 3V11"
                      stroke="currentColor"
                      stroke-width="1.3"
                      stroke-linecap="round"
                    />

                    <path
                      d="M4.5 3V8C4.5 9.38 5.62 10.5 7 10.5C8.38 10.5 9.5 9.38 9.5 8V3"
                      stroke="currentColor"
                      stroke-width="1.3"
                      stroke-linecap="round"
                    />

                    <path
                      d="M7 10.5V21"
                      stroke="currentColor"
                      stroke-width="1.3"
                      stroke-linecap="round"
                    />

                    <path
                      d="M16 3V21"
                      stroke="currentColor"
                      stroke-width="1.3"
                      stroke-linecap="round"
                    />

                    <path
                      d="M16 3C18.2 5.2 18.2 9 16 11"
                      stroke="currentColor"
                      stroke-width="1.3"
                      stroke-linecap="round"
                    />
                  </svg>

                </div>

              </div>

              <h3>
                {{
                  language === 'ar'
                    ? 'العشاء'
                    : 'Dîner'
                }}
              </h3>

              <p>
                {{
                  language === 'ar'
                    ? '15 جويلية 2030 — ابتداءً من الساعة 19:30'
                    : '15 JUILLET 2030 — À partir de 19:30'
                }}
              </p>

              <div
                class="event-location justify-end max-[700px]:justify-start"
              >

                <svg
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                  aria-hidden="true"
                >
                  <path
                    d="M12 21C15.5 16.8 18 14.1 18 10.5C18 7.18 15.31 4.5 12 4.5C8.69 4.5 6 7.18 6 10.5C6 14.1 8.5 16.8 12 21Z"
                    stroke="currentColor"
                    stroke-width="1.3"
                  />

                  <circle
                    cx="12"
                    cy="10.5"
                    r="2"
                    stroke="currentColor"
                    stroke-width="1.3"
                  />
                </svg>

                {{
                    language === 'ar'
                      ? 'مكان الحفل غير متوفر حاليًا'
                      : 'Le lieu de l’événement n’est pas encore disponible'
                  }}

              </div>

            </div>
          </div>

          <div class="timeline-node">
            <span></span>
          </div>

          <div class="timeline-empty"></div>
        </article>


        <!-- ===================================================
             EVENT 2
        ==================================================== -->

        <article
          class="event-row relative grid min-h-[240px] grid-cols-[1fr_80px_1fr] items-center max-[900px]:grid-cols-[1fr_55px_1fr] max-[700px]:mb-[25px] max-[700px]:min-h-[210px] max-[700px]:grid-cols-[30px_1fr] max-[430px]:mb-[20px] max-[430px]:min-h-[190px] max-[430px]:grid-cols-[25px_1fr]"
        >

          <div class="timeline-empty"></div>

          <div class="timeline-node">
            <span></span>
          </div>

          <div class="event-content event-right-content">

            <div
              class="event-time text-left max-[700px]:text-left"
            >
              21:00 — 22:00
            </div>

            <div class="event-card">

              <div class="event-card-top">

                <span class="event-number">
                  02
                </span>

                <div class="event-icon">

                  <!-- Wedding / ceremony icon -->
                  <svg
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    aria-hidden="true"
                  >
                    <path
                      d="M12 3L13.8 8.2L19 10L13.8 11.8L12 17L10.2 11.8L5 10L10.2 8.2L12 3Z"
                      stroke="currentColor"
                      stroke-width="1.3"
                      stroke-linejoin="round"
                    />

                    <path
                      d="M19 16L19.8 18.2L22 19L19.8 19.8L19 22L18.2 19.8L16 19L18.2 18.2L19 16Z"
                      stroke="currentColor"
                      stroke-width="1.1"
                      stroke-linejoin="round"
                    />
                  </svg>

                </div>

              </div>

              <h3>
                {{
                  language === 'ar'
                    ? 'عقد القران'
                    : 'Cérémonie du mariage'
                }}
              </h3>

              <p>
                {{
                  language === 'ar'
                    ? '16 جويلية 2030 — من الساعة 21:00 إلى 22:00'
                    : '16 JUILLET 2030 — De 21:00 à 22:00'
                }}
              </p>

              <div class="event-location justify-start">

                <svg
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                  aria-hidden="true"
                >
                  <path
                    d="M12 21C15.5 16.8 18 14.1 18 10.5C18 7.18 15.31 4.5 12 4.5C8.69 4.5 6 7.18 6 10.5C6 14.1 8.5 16.8 12 21Z"
                    stroke="currentColor"
                    stroke-width="1.3"
                  />

                  <circle
                    cx="12"
                    cy="10.5"
                    r="2"
                    stroke="currentColor"
                    stroke-width="1.3"
                  />
                </svg>

                <span>
                  {{
                    language === 'ar'
                      ? 'مكان الحفل غير متوفر حاليًا'
                      : 'Le lieu de l’événement n’est pas encore disponible'
                  }}
                </span>

              </div>

            </div>
          </div>
        </article>

      </div>


      <!-- =====================================================
           BOTTOM MESSAGE
      ====================================================== -->

      <div
        class="events-footer mt-[65px] pb-0 text-center max-[700px]:mt-[35px] max-[700px]:pb-5 max-[430px]:mt-[28px]"
      >

        <div
          class="footer-symbol flex items-center justify-center gap-[13px] max-[430px]:gap-2"
        >
          <span></span>

          <div>
            <i></i>
          </div>

          <span></span>
        </div>

        <p
          :class="{
            'font-arabic text-sm tracking-normal':
              language === 'ar'
          }"
        >
          {{
            language === 'ar'
              ? 'ننتظركم لنشارككم هذه اللحظات الجميلة'
              : 'Nous vous attendons pour partager ensemble ces beaux moments'
          }}
        </p>

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

const props = defineProps({
  language: {
    type: String,
    default: 'fr',
  },
})

const sectionRef = ref(null)
const isVisible = ref(false)

/* ============================================================
   EVENT DATE
   Countdown jusqu'au premier rendez-vous :
   02 JUILLET 2027 à 19:30
============================================================ */

const EVENT_DATE = '2030-07-15T19:30:00'

const eventDate = new Date(EVENT_DATE)

const countdown = ref({
  days: 0,
  hours: 0,
  minutes: 0,
  seconds: 0,
})

const isDatePassed = ref(false)

let observer = null
let countdownInterval = null


/* ============================================================
   MONTHS
============================================================ */

const frenchMonths = [
  'JANVIER',
  'FÉVRIER',
  'MARS',
  'AVRIL',
  'MAI',
  'JUIN',
  'JUILLET',
  'AOÛT',
  'SEPTEMBRE',
  'OCTOBRE',
  'NOVEMBRE',
  'DÉCEMBRE',
]

const arabicMonths = [
  'جانفي',
  'فيفري',
  'مارس',
  'أفريل',
  'ماي',
  'جوان',
  'جويلية',
  'أوت',
  'سبتمبر',
  'أكتوبر',
  'نوفمبر',
  'ديسمبر',
]


const formattedEventDate = computed(() => {
  const day = eventDate.getDate()
  const month = eventDate.getMonth()
  const year = eventDate.getFullYear()

  if (props.language === 'ar') {
    return `${day} ${arabicMonths[month]} ${year}`
  }

  return `${day} ${frenchMonths[month]} ${year}`
})


/* ============================================================
   COUNTDOWN
============================================================ */

const updateCountdown = () => {
  const difference =
    eventDate.getTime() - Date.now()

  if (difference <= 0) {
    isDatePassed.value = true

    countdown.value = {
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
    }

    return
  }

  isDatePassed.value = false

  const totalSeconds =
    Math.floor(difference / 1000)

  countdown.value = {
    days: Math.floor(
      totalSeconds / 86400,
    ),

    hours: Math.floor(
      (totalSeconds % 86400) / 3600,
    ),

    minutes: Math.floor(
      (totalSeconds % 3600) / 60,
    ),

    seconds:
      totalSeconds % 60,
  }
}


const formatNumber = (value) => {
  return String(value).padStart(2, '0')
}


/* ============================================================
   LIFECYCLE
============================================================ */

onMounted(() => {
  observer = new IntersectionObserver(
    ([entry]) => {
      isVisible.value =
        entry.isIntersecting
    },
    {
      threshold: 0.18,
    },
  )

  if (sectionRef.value) {
    observer.observe(sectionRef.value)
  }

  updateCountdown()

  countdownInterval =
    window.setInterval(
      updateCountdown,
      1000,
    )
})


onBeforeUnmount(() => {
  observer?.disconnect()

  if (countdownInterval) {
    window.clearInterval(
      countdownInterval,
    )
  }
})
</script>


<style scoped>

/* ============================================================
   BACKGROUND ANIMATIONS
============================================================ */

.events-glow {
  pointer-events: none;

  filter:
    blur(100px);

  opacity:
    0.14;
}

.events-glow-top {
  animation:
    glowTopMove
    13s
    ease-in-out
    infinite;
}

.events-glow-bottom {
  animation:
    glowBottomMove
    15s
    ease-in-out
    infinite;
}

.events-pattern {
  background-image:
    linear-gradient(
      30deg,
      transparent 45%,
      #705536 46%,
      #705536 48%,
      transparent 49%
    ),
    linear-gradient(
      150deg,
      transparent 45%,
      #705536 46%,
      #705536 48%,
      transparent 49%
    );

  background-size:
    100px 100px;

  animation:
    eventsPatternMove
    30s
    linear
    infinite;
}

.vertical-pattern {
  background:
    repeating-linear-gradient(
      to bottom,
      rgba(142, 105, 55, 0.35) 0,
      rgba(142, 105, 55, 0.35) 2px,
      transparent 2px,
      transparent 12px
    );

  animation:
    verticalMove
    8s
    linear
    infinite;
}

.vertical-pattern:nth-of-type(2) {
  animation-direction:
    reverse;

  animation-duration:
    10s;
}


/* ============================================================
   DECORATIONS
============================================================ */

.floating-square {
  border:
    1px solid rgba(142, 105, 55, 0.35);

  transform:
    rotate(45deg);
}

.floating-square-1 {
  animation:
    squareFloat
    8s
    ease-in-out
    infinite;
}

.floating-square-2 {
  animation:
    squareFloat
    10s
    ease-in-out
    1s
    infinite;
}

.floating-square-3 {
  animation:
    squareFloat
    9s
    ease-in-out
    2s
    infinite;
}

.floating-circle {
  border:
    1px solid #8e6937;

  border-radius:
    50%;

  opacity:
    0.45;
}

.floating-circle-1 {
  animation:
    circleFloat
    7s
    ease-in-out
    infinite;
}

.floating-circle-2 {
  animation:
    circleFloat
    9s
    ease-in-out
    1s
    infinite;
}

.floating-circle-3 {
  animation:
    circleFloat
    8s
    ease-in-out
    2s
    infinite;
}

.floating-cross {
  color:
    #8e6937;

  font-family:
    Georgia,
    serif;

  font-size:
    16px;

  opacity:
    0.25;

  animation:
    crossFloat
    6s
    ease-in-out
    infinite;
}

.floating-cross-1 {
  animation-delay:
    0s;
}

.floating-cross-2 {
  animation-delay:
    1.5s;
}

.floating-cross-3 {
  animation-delay:
    2.5s;
}


/* ============================================================
   FRAME
============================================================ */

.events-frame {
  transition:
    inset 0.3s ease;
}

.frame-corner {
  position:
    absolute;

  width:
    38px;

  height:
    38px;
}

.frame-corner::before,
.frame-corner::after {
  content:
    "";

  position:
    absolute;

  background:
    #8e6937;
}

.frame-corner::before {
  width:
    38px;

  height:
    1px;
}

.frame-corner::after {
  width:
    1px;

  height:
    38px;
}

.frame-tl {
  top:
    0;

  left:
    0;
}

.frame-tr {
  top:
    0;

  right:
    0;

  transform:
    rotate(90deg);
}

.frame-bl {
  bottom:
    0;

  left:
    0;

  transform:
    rotate(-90deg);
}

.frame-br {
  right:
    0;

  bottom:
    0;

  transform:
    rotate(180deg);
}


/* ============================================================
   REVEAL ANIMATIONS
============================================================ */

.reveal-label,
.reveal-intro,
.reveal-title,
.reveal-description,
.countdown-wrapper,
.header-divider,
.event-content,
.timeline-node,
.events-footer {
  opacity:
    0;
}

.reveal-label {
  transform:
    translateY(25px);

  transition:
    opacity 0.8s ease,
    transform 0.8s ease;
}

.reveal-intro {
  transform:
    translateY(25px);

  transition:
    opacity 0.8s ease 0.15s,
    transform 0.8s ease 0.15s;
}

.reveal-title {
  transform:
    translateY(30px);

  filter:
    blur(5px);

  transition:
    opacity 1s ease 0.3s,
    transform 1s ease 0.3s,
    filter 1s ease 0.3s;
}

.reveal-description {
  transform:
    translateY(25px);

  transition:
    opacity 0.8s ease 0.45s,
    transform 0.8s ease 0.45s;
}

.events-active .reveal-label,
.events-active .reveal-intro,
.events-active .reveal-title,
.events-active .reveal-description {
  opacity:
    1;

  transform:
    translateY(0);
}

.events-active .reveal-title {
  filter:
    blur(0);
}


/* ============================================================
   BIG COUNTDOWN
============================================================ */

.countdown-wrapper {
  transform:
    translateY(30px);

  filter:
    blur(4px);

  transition:
    opacity 1s ease 0.55s,
    transform 1s ease 0.55s,
    filter 1s ease 0.55s;
}

.events-active .countdown-wrapper {
  opacity:
    1;

  transform:
    translateY(0);

  filter:
    blur(0);
}

.countdown-big {
  display:
    flex;

  align-items:
    center;

  justify-content:
    center;

  gap:
    18px;

  direction:
    ltr;

  width:
    100%;

  max-width:
    100%;
}

.countdown-big-item {
  width:
    100px;

  min-height:
    105px;

  display:
    flex;

  flex-direction:
    column;

  align-items:
    center;

  justify-content:
    center;

  padding:
    14px 12px;

  background:
    rgba(255, 253, 248, 0.82);

  border:
    1px solid rgba(142, 105, 55, 0.22);

  box-shadow:
    0 15px 40px rgba(70, 48, 28, 0.055),
    inset 0 0 25px rgba(142, 105, 55, 0.025);

  backdrop-filter:
    blur(8px);

  transition:
    transform 0.35s ease,
    border-color 0.35s ease,
    box-shadow 0.35s ease;
}

.countdown-big-item:hover {
  transform:
    translateY(-4px);

  border-color:
    rgba(142, 105, 55, 0.4);

  box-shadow:
    0 20px 45px rgba(70, 48, 28, 0.09),
    inset 0 0 25px rgba(142, 105, 55, 0.035);
}

.countdown-big-item strong {
  color:
    #30241c;

  font-family:
    "Cormorant Garamond",
    Georgia,
    serif;

  font-size:
    3.2rem;

  font-weight:
    500;

  line-height:
    1;
}

.countdown-big-item span {
  margin-top:
    9px;

  color:
    #8e6937;

  font-family:
    "Montserrat",
    sans-serif;

  font-size:
    8px;

  font-weight:
    600;

  letter-spacing:
    0.13em;

  white-space:
    nowrap;
}

.countdown-big-separator {
  flex:
    0 0 auto;

  color:
    #8e6937;

  font-family:
    "Cormorant Garamond",
    Georgia,
    serif;

  font-size:
    2.3rem;

  transform:
    translateY(-4px);

  opacity:
    0.65;
}

.countdown-passed {
  display:
    inline-flex;

  align-items:
    center;

  justify-content:
    center;

  margin-top:
    20px;

  padding:
    14px 26px;

  color:
    #8e6937;

  font-family:
    "Montserrat",
    sans-serif;

  font-size:
    10px;

  font-weight:
    600;

  letter-spacing:
    0.12em;

  background:
    rgba(255, 253, 248, 0.72);

  border:
    1px solid rgba(142, 105, 55, 0.18);

  box-shadow:
    0 10px 30px
      rgba(70, 48, 28, 0.045);

  backdrop-filter:
    blur(8px);

  max-width:
    calc(100% - 20px);
}


/* ============================================================
   DIVIDER
============================================================ */

.header-divider {
  transform:
    scaleX(0.5);

  transition:
    opacity 0.8s ease 0.7s,
    transform 0.8s ease 0.7s;
}

.events-active .header-divider {
  opacity:
    1;

  transform:
    scaleX(1);
}

.header-divider > span {
  width:
    60px;

  height:
    1px;

  background:
    rgba(142, 105, 55, 0.35);
}

.header-diamond {
  flex:
    0 0 auto;

  width:
    9px;

  height:
    9px;

  border:
    1px solid #8e6937;

  transform:
    rotate(45deg);

  animation:
    headerDiamond
    4s
    ease-in-out
    infinite;
}


/* ============================================================
   TIMELINE
============================================================ */

.timeline-progress {
  transition:
    height 2s
      cubic-bezier(0.22, 1, 0.36, 1);
}

.events-active .timeline-progress {
  height:
    100%;
}

.event-content {
  min-width:
    0;

  opacity:
    0;

  filter:
    blur(6px);

  transition:
    opacity 0.9s ease,
    transform 1s
      cubic-bezier(0.22, 1, 0.36, 1),
    filter 1s ease;
}

.event-left-content {
  transform:
    translateX(-70px);

  padding-right:
    45px;

  text-align:
    right;
}

.event-right-content {
  transform:
    translateX(70px);

  padding-left:
    45px;

  text-align:
    left;
}

.event-row:nth-child(2) .event-content {
  transition-delay:
    0.45s;
}

.event-row:nth-child(3) .event-content {
  transition-delay:
    0.7s;
}

.events-active .event-content {
  opacity:
    1;

  transform:
    translateX(0);

  filter:
    blur(0);
}

.event-time {
  margin-bottom:
    9px;

  color:
    #8e6937;

  font-family:
    "Montserrat",
    sans-serif;

  font-size:
    10px;

  font-weight:
    600;

  letter-spacing:
    0.25em;
}


/* ============================================================
   CARDS
============================================================ */

.event-card {
  position:
    relative;

  min-width:
    0;

  padding:
    28px 30px;

  background:
    rgba(255, 253, 248, 0.78);

  border:
    1px solid rgba(142, 105, 55, 0.2);

  box-shadow:
    0 15px 45px
      rgba(70, 48, 28, 0.06),
    inset 0 0 30px
      rgba(142, 105, 55, 0.02);

  backdrop-filter:
    blur(10px);

  transition:
    transform 0.4s ease,
    border-color 0.4s ease,
    box-shadow 0.4s ease;
}

.event-card:hover {
  transform:
    translateY(-5px);

  border-color:
    rgba(142, 105, 55, 0.4);

  box-shadow:
    0 22px 55px
      rgba(70, 48, 28, 0.1),
    inset 0 0 30px
      rgba(142, 105, 55, 0.03);
}

.event-card-top {
  display:
    flex;

  align-items:
    center;

  justify-content:
    space-between;
}

.event-number {
  color:
    rgba(142, 105, 55, 0.5);

  font-family:
    "Montserrat",
    sans-serif;

  font-size:
    9px;

  letter-spacing:
    0.2em;
}

.event-icon {
  flex:
    0 0 auto;

  width:
    42px;

  height:
    42px;

  display:
    flex;

  align-items:
    center;

  justify-content:
    center;

  color:
    #8e6937;

  border:
    1px solid rgba(142, 105, 55, 0.28);

  transition:
    transform 0.4s ease,
    background 0.4s ease;
}

.event-icon svg {
  width:
    21px;

  height:
    21px;
}

.event-card:hover .event-icon {
  transform:
    rotate(8deg)
    scale(1.08);

  background:
    rgba(142, 105, 55, 0.05);
}

.event-card h3 {
  margin-top:
    18px;

  color:
    #30241c;

  font-family:
    "Cormorant Garamond",
    Georgia,
    serif;

  font-size:
    2rem;

  font-weight:
    500;

  overflow-wrap:
    anywhere;
}

.event-card p {
  margin-top:
    7px;

  color:
    #705b48;

  font-family:
    "Montserrat",
    sans-serif;

  font-size:
    11px;

  line-height:
    1.7;

  overflow-wrap:
    anywhere;
}

.event-location {
  display:
    flex;

  align-items:
    center;

  gap:
    7px;

  margin-top:
    18px;

  color:
    #8e6937;

  font-family:
    "Montserrat",
    sans-serif;

  font-size:
    9px;

  letter-spacing:
    0.05em;

  min-width:
    0;
}

.event-location svg {
  flex:
    0 0 auto;

  width:
    15px;

  height:
    15px;
}

.event-location span {
  overflow-wrap:
    anywhere;
}


/* ============================================================
   NODES
============================================================ */

.timeline-node {
  position:
    relative;

  z-index:
    5;

  width:
    22px;

  height:
    22px;

  margin:
    auto;

  display:
    flex;

  align-items:
    center;

  justify-content:
    center;

  background:
    #e7dfd1;

  border:
    1px solid rgba(142, 105, 55, 0.6);

  transform:
    rotate(45deg)
    scale(0.4);

  transition:
    opacity 0.6s ease,
    transform 0.6s ease;
}

.timeline-node span {
  width:
    6px;

  height:
    6px;

  background:
    #8e6937;
}

.events-active .timeline-node {
  opacity:
    1;

  transform:
    rotate(45deg)
    scale(1);
}

.events-active .timeline-node span {
  animation:
    nodePulse
    2.5s
    ease-in-out
    infinite;
}


/* ============================================================
   FOOTER
============================================================ */

.events-footer {
  opacity:
    0;

  transform:
    translateY(25px);

  transition:
    opacity 0.8s ease 1.4s,
    transform 0.8s ease 1.4s;
}

.events-active .events-footer {
  opacity:
    1;

  transform:
    translateY(0);
}

.footer-symbol span {
  width:
    50px;

  height:
    1px;

  background:
    rgba(142, 105, 55, 0.35);
}

.footer-symbol > div {
  flex:
    0 0 auto;

  width:
    12px;

  height:
    12px;

  display:
    flex;

  align-items:
    center;

  justify-content:
    center;

  border:
    1px solid #8e6937;

  transform:
    rotate(45deg);

  animation:
    footerRotate
    8s
    linear
    infinite;
}

.footer-symbol i {
  width:
    4px;

  height:
    4px;

  background:
    #8e6937;
}

.events-footer p {
  max-width:
    90%;

  margin:
    16px auto 0;

  color:
    #8e6937;

  font-family:
    "Montserrat",
    sans-serif;

  font-size:
    9px;

  font-weight:
    600;

  letter-spacing:
    0.24em;

  line-height:
    1.8;
}


/* ============================================================
   ARABIC
============================================================ */

[dir="rtl"] .reveal-title,
[dir="rtl"] .event-card h3 {
  font-family:
    "Amiri",
    "Noto Naskh Arabic",
    Tahoma,
    Arial,
    serif;
}

[dir="rtl"] .reveal-description,
[dir="rtl"] .event-card p {
  line-height:
    2.1;
}

[dir="rtl"] .event-left-content,
[dir="rtl"] .event-right-content {
  text-align:
    right;
}

[dir="rtl"] .event-location {
  justify-content:
    flex-start;
}

[dir="rtl"] .countdown-big {
  direction:
    ltr;
}

[dir="rtl"] .countdown-date {
  letter-spacing:
    0;
}


/* ============================================================
   TABLET
============================================================ */

@media (max-width: 900px) {

  .event-left-content {
    padding-right:
      25px;
  }

  .event-right-content {
    padding-left:
      25px;
  }

  .event-card {
    padding:
      24px 22px;
  }
}


/* ============================================================
   MOBILE
============================================================ */

@media (max-width: 700px) {

  .events-frame {
    inset:
      12px;
  }

  .frame-corner {
    width:
      28px;

    height:
      28px;
  }

  .frame-corner::before {
    width:
      28px;
  }

  .frame-corner::after {
    height:
      28px;
  }

  .event-left-content,
  .event-right-content {
    grid-column:
      2;

    grid-row:
      1;

    min-width:
      0;

    padding-left:
      25px;

    padding-right:
      0;

    text-align:
      left;

    transform:
      translateX(45px);
  }

  .events-active .event-content {
    transform:
      translateX(0);
  }

  .timeline-node {
    grid-column:
      1;

    grid-row:
      1;

    width:
      18px;

    height:
      18px;
  }

  .event-time {
    font-size:
      9px;

    letter-spacing:
      0.18em;
  }

  .event-card {
    padding:
      22px 20px;
  }

  .event-card h3 {
    font-size:
      1.8rem;
  }

  .event-card p {
    font-size:
      10px;
  }

  .event-location {
    font-size:
      8px;

    line-height:
      1.7;
  }

  .floating-square,
  .floating-circle,
  .floating-cross {
    opacity:
      0.35;
  }

  .countdown-big {
    gap:
      7px;
  }

  .countdown-big-item {
    width:
      72px;

    min-height:
      88px;

    padding:
      11px 6px;
  }

  .countdown-big-item strong {
    font-size:
      2.35rem;
  }

  .countdown-big-item span {
    font-size:
      6px;
  }

  .countdown-big-separator {
    font-size:
      1.6rem;
  }

  .header-divider > span {
    width:
      45px;
  }

  .footer-symbol span {
    width:
      40px;
  }
}


/* ============================================================
   SMALL MOBILE
============================================================ */

@media (max-width: 430px) {

  .events-frame {
    inset:
      10px;
  }

  .frame-corner {
    width:
      22px;

    height:
      22px;
  }

  .frame-corner::before {
    width:
      22px;
  }

  .frame-corner::after {
    height:
      22px;
  }

  .events-glow {
    opacity:
      0.09;

    filter:
      blur(75px);
  }

  .events-pattern {
    opacity:
      0.035;

    background-size:
      70px 70px;
  }

  .countdown-big {
    gap:
      3px;
  }

  .countdown-big-item {
    width:
      60px;

    min-height:
      75px;

    padding:
      9px 4px;
  }

  .countdown-big-item strong {
    font-size:
      1.9rem;
  }

  .countdown-big-item span {
    font-size:
      5px;

    letter-spacing:
      0.06em;
  }

  .countdown-big-separator {
    font-size:
      1.15rem;
  }

  .event-left-content,
  .event-right-content {
    padding-left:
      18px;
  }

  .event-time {
    margin-bottom:
      7px;

    font-size:
      8px;

    letter-spacing:
      0.12em;
  }

  .event-card {
    padding:
      18px 16px;
  }

  .event-card-top {
    min-height:
      36px;
  }

  .event-number {
    font-size:
      8px;

    letter-spacing:
      0.14em;
  }

  .event-icon {
    width:
      36px;

    height:
      36px;
  }

  .event-icon svg {
    width:
      18px;

    height:
      18px;
  }

  .event-card h3 {
    margin-top:
      14px;

    font-size:
      1.55rem;

    line-height:
      1.15;
  }

  .event-card p {
    margin-top:
      8px;

    font-size:
      9px;

    line-height:
      1.8;
  }

  .event-location {
    gap:
      5px;

    margin-top:
      14px;

    font-size:
      7.5px;

    line-height:
      1.7;

    letter-spacing:
      0.02em;
  }

  .event-location svg {
    width:
      13px;

    height:
      13px;
  }

  .timeline-node {
    width:
      16px;

    height:
      16px;
  }

  .timeline-node span {
    width:
      5px;

    height:
      5px;
  }

  .header-divider > span {
    width:
      32px;
  }

  .header-diamond {
    width:
      7px;

    height:
      7px;
  }

  .footer-symbol span {
    width:
      32px;
  }

  .footer-symbol > div {
    width:
      10px;

    height:
      10px;
  }

  .footer-symbol i {
    width:
      3px;

    height:
      3px;
  }

  .events-footer p {
    max-width:
      280px;

    margin-top:
      14px;

    font-size:
      8px;

    letter-spacing:
      0.12em;

    line-height:
      1.9;
  }

  [dir="rtl"] .event-left-content,
  [dir="rtl"] .event-right-content {
    text-align:
      right;

    padding-left:
      18px;

    padding-right:
      0;
  }

  [dir="rtl"] .event-card p {
    line-height:
      2;
  }

  [dir="rtl"] .event-location {
    justify-content:
      flex-start;

    font-size:
      9px;
  }
}


/* ============================================================
   VERY SMALL PHONES
============================================================ */

@media (max-width: 360px) {

  .countdown-big {
    gap:
      2px;
  }

  .countdown-big-item {
    width:
      55px;

    min-height:
      70px;

    padding:
      8px 3px;
  }

  .countdown-big-item strong {
    font-size:
      1.7rem;
  }

  .countdown-big-item span {
    font-size:
      4.5px;
  }

  .countdown-big-separator {
    font-size:
      1rem;
  }

  .event-left-content,
  .event-right-content {
    padding-left:
      14px;
  }

  .event-card {
    padding:
      16px 13px;
  }

  .event-card h3 {
    font-size:
      1.4rem;
  }

  .event-card p {
    font-size:
      8.5px;
  }

  .event-location {
    font-size:
      7px;
  }

  .event-icon {
    width:
      33px;

    height:
      33px;
  }

  .event-icon svg {
    width:
      16px;

    height:
      16px;
  }
}


/* ============================================================
   ANIMATIONS
============================================================ */

@keyframes glowTopMove {

  0%,
  100% {
    transform:
      translate(0, 0);
  }

  50% {
    transform:
      translate(90px, 60px);
  }
}

@keyframes glowBottomMove {

  0%,
  100% {
    transform:
      translate(0, 0);
  }

  50% {
    transform:
      translate(-80px, -55px);
  }
}

@keyframes eventsPatternMove {

  from {
    transform:
      translate3d(0, 0, 0);
  }

  to {
    transform:
      translate3d(-100px, 100px, 0);
  }
}

@keyframes verticalMove {

  from {
    background-position:
      0 0;
  }

  to {
    background-position:
      0 80px;
  }
}

@keyframes squareFloat {

  0%,
  100% {
    transform:
      translate(0, 0)
      rotate(45deg);
  }

  50% {
    transform:
      translate(18px, -25px)
      rotate(135deg);
  }
}

@keyframes circleFloat {

  0%,
  100% {
    transform:
      translateY(0)
      scale(1);
  }

  50% {
    transform:
      translateY(-20px)
      scale(1.5);
  }
}

@keyframes crossFloat {

  0%,
  100% {
    transform:
      translateY(0)
      rotate(0);
  }

  50% {
    transform:
      translateY(-14px)
      rotate(90deg);
  }
}

@keyframes headerDiamond {

  0%,
  100% {
    transform:
      rotate(45deg)
      scale(1);
  }

  50% {
    transform:
      rotate(135deg)
      scale(1.2);
  }
}

@keyframes nodePulse {

  0%,
  100% {
    transform:
      rotate(-45deg)
      scale(1);
  }

  50% {
    transform:
      rotate(-45deg)
      scale(1.5);
  }
}

@keyframes footerRotate {

  from {
    transform:
      rotate(45deg);
  }

  to {
    transform:
      rotate(405deg);
  }
}


/* ============================================================
   REDUCED MOTION
============================================================ */

@media (prefers-reduced-motion: reduce) {

  .events-glow,
  .events-pattern,
  .vertical-pattern,
  .floating-square,
  .floating-circle,
  .floating-cross,
  .header-diamond,
  .timeline-node span,
  .footer-symbol > div {
    animation:
      none !important;
  }

  .event-content,
  .events-header *,
  .events-footer,
  .countdown-wrapper,
  .timeline-progress {
    transition:
      none !important;
  }
}

</style>