<template>
  <section
    id="location"
    ref="sectionRef"
    class="location-section relative isolate min-h-screen overflow-hidden bg-[#e7dfd1] text-[#30241c]"
    :class="{ 'location-active': isVisible }"
    :dir="language === 'ar' ? 'rtl' : 'ltr'"
  >
    <!-- =========================================================
         BACKGROUND
    ========================================================== -->

    <div class="absolute inset-0 bg-[#e7dfd1]"></div>

    <!-- Ambient lights -->
    <div class="location-glow glow-one"></div>
    <div class="location-glow glow-two"></div>

    <!-- Moving geometric background -->
    <div class="location-pattern"></div>

    <!-- Small grid -->
    <div class="location-grid"></div>

    <!-- =========================================================
         FLOATING ORNAMENTS
    ========================================================== -->

    <div class="location-orbit orbit-one"></div>
    <div class="location-orbit orbit-two"></div>

    <div class="floating-diamond location-diamond-one"></div>
    <div class="floating-diamond location-diamond-two"></div>
    <div class="floating-diamond location-diamond-three"></div>

    <div class="floating-dot location-dot-one"></div>
    <div class="floating-dot location-dot-two"></div>
    <div class="floating-dot location-dot-three"></div>
    <div class="floating-dot location-dot-four"></div>

    <!-- =========================================================
         FRAME
    ========================================================== -->

    <div
      class="location-frame pointer-events-none absolute inset-[22px] border border-[#241b15]/[0.12] max-[700px]:inset-[12px] max-[430px]:inset-[9px]"
      aria-hidden="true"
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
      class="relative z-20 mx-auto flex min-h-screen w-full max-w-6xl items-center px-6 py-24 md:px-10 max-[700px]:px-5 max-[700px]:py-20 max-[430px]:px-4 max-[430px]:py-16"
    >
      <div class="w-full min-w-0">

        <!-- =====================================================
             HEADER
        ====================================================== -->

        <header class="location-header mb-[60px] text-center">

          <!-- Label -->
          <div
            class="location-label flex items-center justify-center gap-[13px]"
          >
            <span></span>

            <span>
              {{ language === 'ar' ? 'مكاننا' : 'LE LIEU' }}
            </span>

            <span></span>
          </div>

          <!-- Intro -->
          <p class="location-intro mt-[22px]">
            {{
              language === 'ar'
                ? 'يسعدنا أن نلتقي بكم في مكانين مميزين لنحتفل معًا بهذه المناسبة الجميلة.'
                : 'Nous serons heureux de vous retrouver dans deux lieux privilégiés pour partager ensemble ces beaux moments.'
            }}
          </p>

          <!-- Title -->
          <h2 class="location-title mt-[14px]">
            {{
              language === 'ar'
                ? 'مكانا احتفالنا'
                : 'Les lieux de notre célébration'
            }}
          </h2>

          <!-- Description -->
          <p class="location-description mx-auto mt-[22px] max-w-[580px]">
            {{
              language === 'ar'
                ? 'سيتم الإعلان عن المكانين في وقت لاحق. ترقّبوا التحديثات.'
                : 'Les deux lieux seront communiqués ultérieurement. Restez à l’écoute.'
            }}
          </p>

          <!-- Divider -->
          <div
            class="location-divider mt-[28px] flex items-center justify-center gap-3"
          >
            <span></span>
            <div></div>
            <span></span>
          </div>

        </header>

        <!-- =====================================================
             TWO LOCATIONS
        ====================================================== -->

        <div
          class="location-layout grid min-w-0 items-stretch gap-[40px] min-[951px]:grid-cols-2 max-[950px]:max-w-[720px] max-[950px]:mx-auto"
        >

          <!-- ===================================================
               EVENT 1 — LOCATION NOT AVAILABLE
          ==================================================== -->

          <article
            class="location-info-wrapper relative min-w-0 overflow-hidden border border-[#241b15]/[0.18] bg-[#f3ede2]/95 px-[42px] py-[48px] shadow-[0_25px_65px_rgba(70,48,28,0.07),inset_0_0_50px_rgba(142,105,55,0.025)] backdrop-blur-[12px] transition duration-1000 ease-[cubic-bezier(0.22,1,0.36,1)] hover:-translate-y-1 hover:border-[#241b15]/[0.24] max-[700px]:px-[25px] max-[700px]:py-[42px] max-[430px]:px-4 max-[430px]:py-8"
          >

            <div
              class="pointer-events-none absolute inset-[13px] border border-[#241b15]/[0.09] max-[430px]:inset-[10px]"
            ></div>

            <!-- Top ornament -->
            <div
              class="mb-[25px] flex items-center justify-center gap-2.5 max-[430px]:mb-5"
            >
              <span
                class="h-px w-[34px] bg-[#241b15]/[0.3] max-[430px]:w-[25px]"
              ></span>

              <div
                class="info-ornament h-[10px] w-[10px] rotate-45 border border-[#241b15]"
              ></div>

              <span
                class="h-px w-[34px] bg-[#241b15]/[0.3] max-[430px]:w-[25px]"
              ></span>
            </div>

            <!-- Label -->
            <span
              class="block text-center font-['Montserrat',sans-serif] text-[10px] font-semibold tracking-[0.28em] text-[#8e6937] max-[430px]:text-[8px] max-[430px]:tracking-[0.18em]"
            >
              {{ language === 'ar' ? 'العشاء' : 'DÎNER' }}
            </span>

            <!-- Title -->
            <h3
              class="mt-[14px] text-center font-['Cormorant_Garamond',Georgia,serif] text-[clamp(2.2rem,4vw,3.2rem)] font-medium leading-none text-[#30241c] max-[430px]:mt-3 max-[430px]:text-[2rem]"
            >
              {{
                language === 'ar'
                  ? 'مكان الحفل غير متوفر حاليًا'
                  : 'Le lieu de l’événement n’est pas encore disponible'
              }}
            </h3>

            <!-- Information rows -->
            <div
              class="info-list mt-[30px] border-t border-[#241b15]/[0.11] max-[430px]:mt-6"
            >

              <!-- Venue -->
              <div
                class="info-row flex min-w-0 items-center gap-4 border-b border-[#241b15]/[0.11] py-[17px] max-[700px]:gap-3 max-[430px]:gap-2.5 max-[430px]:py-[14px]"
              >
                <div
                  class="info-icon flex h-10 w-10 shrink-0 items-center justify-center border border-[#241b15]/[0.18] text-[#8e6937] transition duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] max-[700px]:h-9 max-[700px]:w-9 max-[430px]:h-8 max-[430px]:w-8"
                >
                  <svg
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 max-[430px]:h-4 max-[430px]:w-4"
                    aria-hidden="true"
                  >
                    <path
                      d="M12 21C15.5 16.8 18 14.1 18 10.5C18 7.18 15.31 4.5 12 4.5C8.69 4.5 6 7.18 6 10.5C6 14.1 8.5 16.8 12 21Z"
                      stroke="currentColor"
                      stroke-width="1.4"
                    />
                    <circle
                      cx="12"
                      cy="10.5"
                      r="2.2"
                      stroke="currentColor"
                      stroke-width="1.4"
                    />
                  </svg>
                </div>

                <div class="min-w-0 flex flex-col gap-1">
                  <span
                    class="font-['Montserrat',sans-serif] text-[9px] font-semibold tracking-[0.2em] text-[#8e6937] max-[430px]:text-[7px]"
                  >
                    {{ language === 'ar' ? 'المكان' : 'LIEU' }}
                  </span>

                  <strong
                    class="break-words font-['Montserrat',sans-serif] text-[12px] font-medium text-[#4d3b2d] max-[700px]:text-[11px] max-[430px]:text-[9.5px]"
                  >
                    {{
                      language === 'ar'
                        ? 'غير متوفر حاليًا'
                        : 'Non disponible pour le moment'
                    }}
                  </strong>
                </div>
              </div>

              <!-- Date -->
              <div
                class="info-row flex min-w-0 items-center gap-4 border-b border-[#241b15]/[0.11] py-[17px] max-[700px]:gap-3 max-[430px]:gap-2.5 max-[430px]:py-[14px]"
              >
                <div
                  class="info-icon flex h-10 w-10 shrink-0 items-center justify-center border border-[#241b15]/[0.18] text-[#8e6937] transition duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] max-[700px]:h-9 max-[700px]:w-9 max-[430px]:h-8 max-[430px]:w-8"
                >
                  <svg
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 max-[430px]:h-4 max-[430px]:w-4"
                    aria-hidden="true"
                  >
                    <rect
                      x="3.5"
                      y="5"
                      width="17"
                      height="15"
                      rx="1"
                      stroke="currentColor"
                      stroke-width="1.4"
                    />
                    <path
                      d="M7.5 3.5V7M16.5 3.5V7M3.5 9H20.5"
                      stroke="currentColor"
                      stroke-width="1.4"
                    />
                  </svg>
                </div>

                <div class="min-w-0 flex flex-col gap-1">
                  <span
                    class="font-['Montserrat',sans-serif] text-[9px] font-semibold tracking-[0.2em] text-[#8e6937] max-[430px]:text-[7px]"
                  >
                    {{ language === 'ar' ? 'التاريخ' : 'DATE' }}
                  </span>

                  <strong
                    class="break-words font-['Montserrat',sans-serif] text-[12px] font-medium text-[#4d3b2d] max-[700px]:text-[11px] max-[430px]:text-[9.5px]"
                  >
                    {{
                      language === 'ar'
                        ? '15 جويلية 2030'
                        : '15 JUILLET 2030'
                    }}
                  </strong>
                </div>
              </div>

              <!-- Time -->
              <div
                class="info-row flex min-w-0 items-center gap-4 border-b border-[#241b15]/[0.11] py-[17px] max-[700px]:gap-3 max-[430px]:gap-2.5 max-[430px]:py-[14px]"
              >
                <div
                  class="info-icon flex h-10 w-10 shrink-0 items-center justify-center border border-[#241b15]/[0.18] text-[#8e6937] transition duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] max-[700px]:h-9 max-[700px]:w-9 max-[430px]:h-8 max-[430px]:w-8"
                >
                  <svg
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 max-[430px]:h-4 max-[430px]:w-4"
                    aria-hidden="true"
                  >
                    <circle
                      cx="12"
                      cy="12"
                      r="8.5"
                      stroke="currentColor"
                      stroke-width="1.4"
                    />
                    <path
                      d="M12 7V12L15.5 14"
                      stroke="currentColor"
                      stroke-width="1.4"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                </div>

                <div class="min-w-0 flex flex-col gap-1">
                  <span
                    class="font-['Montserrat',sans-serif] text-[9px] font-semibold tracking-[0.2em] text-[#8e6937] max-[430px]:text-[7px]"
                  >
                    {{ language === 'ar' ? 'الوقت' : 'HEURE' }}
                  </span>

                  <strong
                    class="break-words font-['Montserrat',sans-serif] text-[12px] font-medium text-[#4d3b2d] max-[700px]:text-[11px] max-[430px]:text-[9.5px]"
                  >
                    {{
                      language === 'ar'
                        ? 'ابتداءً من 19:30'
                        : 'À partir de 19:30'
                    }}
                  </strong>
                </div>
              </div>

            </div>

            <!-- Map (placeholder) -->
            <div class="mt-[27px] block max-[430px]:mt-5">
              <div
                class="relative h-[300px] overflow-hidden border border-[#241b15]/[0.18] bg-[#eee7da] shadow-[0_25px_65px_rgba(70,48,28,0.08),inset_0_0_40px_rgba(142,105,55,0.05)] max-[700px]:h-[270px] max-[430px]:h-[220px]"
              >

                <!-- Decorative map background -->
                <div class="map-background">
                  <div class="map-road road-one"></div>
                  <div class="map-road road-two"></div>
                  <div class="map-road road-three"></div>
                  <div class="map-road road-four"></div>

                  <div class="map-block block-one"></div>
                  <div class="map-block block-two"></div>
                  <div class="map-block block-three"></div>
                  <div class="map-block block-four"></div>
                  <div class="map-block block-five"></div>

                  <div class="map-circle map-circle-one"></div>
                  <div class="map-circle map-circle-two"></div>
                </div>

                <!-- Map center -->
                <div
                  class="absolute left-1/2 top-1/2 z-[5] flex min-w-0 -translate-x-1/2 -translate-y-1/2 flex-col items-center"
                >
                  <div class="map-pulse"></div>

                  <div
                    class="map-marker relative flex h-[66px] w-[66px] shrink-0 items-center justify-center rounded-full bg-[#8e6937] text-[#f8f4ec] shadow-[0_12px_35px_rgba(112,85,54,0.22)] max-[700px]:h-[58px] max-[700px]:w-[58px] max-[430px]:h-[50px] max-[430px]:w-[50px]"
                  >
                    <svg
                      viewBox="0 0 24 24"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-[27px] w-[27px] max-[700px]:h-6 max-[700px]:w-6 max-[430px]:h-5 max-[430px]:w-5"
                      aria-hidden="true"
                    >
                      <path
                        d="M12 21C15.5 16.8 18 14.1 18 10.5C18 7.18 15.31 4.5 12 4.5C8.69 4.5 6 7.18 6 10.5C6 14.1 8.5 16.8 12 21Z"
                        stroke="currentColor"
                        stroke-width="1.4"
                      />
                      <circle
                        cx="12"
                        cy="10.5"
                        r="2.2"
                        stroke="currentColor"
                        stroke-width="1.4"
                      />
                    </svg>
                  </div>

                  <span
                    class="mt-[18px] max-w-[calc(100vw-100px)] whitespace-nowrap border border-[#241b15]/[0.15] bg-[#fffdf8]/80 px-[13px] py-[7px] text-center font-['Montserrat',sans-serif] text-[9px] font-semibold tracking-[0.18em] text-[#705536] max-[700px]:mt-3 max-[430px]:px-2.5 max-[430px]:py-1.5 max-[430px]:text-[7px] max-[430px]:tracking-[0.1em]"
                  >
                    {{
                      language === 'ar'
                        ? 'المكان غير متوفر'
                        : 'LIEU NON DISPONIBLE'
                    }}
                  </span>
                </div>

                <!-- Compass -->
                <div
                  class="absolute right-[22px] top-[22px] flex h-[38px] w-[38px] flex-col items-center justify-center border border-[#241b15]/[0.18] font-['Montserrat',sans-serif] text-[9px] text-[#8e6937] opacity-70 max-[430px]:right-3 max-[430px]:top-3 max-[430px]:h-7 max-[430px]:w-7 max-[430px]:text-[7px]"
                  aria-hidden="true"
                >
                  <span>N</span>

                  <div
                    class="mt-[2px] h-[7px] w-[7px] rotate-45 border-l border-t border-[#8e6937] max-[430px]:h-1.5 max-[430px]:w-1.5"
                  ></div>
                </div>

                <!-- Map decorative border -->
                <div
                  class="pointer-events-none absolute inset-[14px] border border-[#241b15]/[0.1] max-[430px]:inset-2.5"
                ></div>

              </div>
            </div>

            <!-- Google Maps button (disabled) -->
            <div
              class="mt-[14px] flex min-h-[44px] w-full items-center justify-center gap-[9px] border border-[#241b15]/[0.12] bg-transparent px-[18px] py-[13px] text-center font-['Montserrat',sans-serif] text-[10px] font-semibold leading-[1.5] tracking-[0.12em] text-[#8e6937] opacity-40 max-[430px]:mt-3 max-[430px]:gap-1.5 max-[430px]:px-3 max-[430px]:py-2.5 max-[430px]:text-[8px] max-[430px]:tracking-[0.06em]"
            >
              <svg
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
                class="h-4 w-4 shrink-0 max-[430px]:h-3.5 max-[430px]:w-3.5"
                aria-hidden="true"
              >
                <path
                  d="M12 21C15.5 16.8 18 14.1 18 10.5C18 7.18 15.31 4.5 12 4.5C8.69 4.5 6 7.18 6 10.5C6 14.1 8.5 16.8 12 21Z"
                  stroke="currentColor"
                  stroke-width="1.4"
                />
                <circle
                  cx="12"
                  cy="10.5"
                  r="2.2"
                  stroke="currentColor"
                  stroke-width="1.4"
                />
              </svg>

              <span class="min-w-0">
                {{
                  language === 'ar'
                    ? 'الموقع غير متوفر حاليًا'
                    : 'EMPLACEMENT NON DISPONIBLE'
                }}
              </span>
            </div>

          </article>


          <!-- ===================================================
               EVENT 2 — LOCATION NOT AVAILABLE
          ==================================================== -->

          <article
            class="location-info-wrapper relative min-w-0 overflow-hidden border border-[#241b15]/[0.18] bg-[#f3ede2]/95 px-[42px] py-[48px] shadow-[0_25px_65px_rgba(70,48,28,0.07),inset_0_0_50px_rgba(142,105,55,0.025)] backdrop-blur-[12px] transition duration-1000 ease-[cubic-bezier(0.22,1,0.36,1)] hover:-translate-y-1 hover:border-[#241b15]/[0.24] max-[700px]:px-[25px] max-[700px]:py-[42px] max-[430px]:px-4 max-[430px]:py-8"
          >

            <div
              class="pointer-events-none absolute inset-[13px] border border-[#241b15]/[0.09] max-[430px]:inset-[10px]"
            ></div>

            <!-- Top ornament -->
            <div
              class="mb-[25px] flex items-center justify-center gap-2.5 max-[430px]:mb-5"
            >
              <span
                class="h-px w-[34px] bg-[#241b15]/[0.3] max-[430px]:w-[25px]"
              ></span>

              <div
                class="info-ornament h-[10px] w-[10px] rotate-45 border border-[#241b15]"
              ></div>

              <span
                class="h-px w-[34px] bg-[#241b15]/[0.3] max-[430px]:w-[25px]"
              ></span>
            </div>

            <!-- Label -->
            <span
              class="block text-center font-['Montserrat',sans-serif] text-[10px] font-semibold tracking-[0.22em] text-[#8e6937] max-[430px]:text-[8px] max-[430px]:tracking-[0.12em]"
            >
              {{
                language === 'ar'
                  ? 'عقد القران'
                  : 'CÉRÉMONIE DU MARIAGE'
              }}
            </span>

            <!-- Title -->
            <h3
              class="mt-[14px] text-center font-['Cormorant_Garamond',Georgia,serif] text-[clamp(2.2rem,4vw,3.2rem)] font-medium leading-none text-[#30241c] max-[430px]:mt-3 max-[430px]:text-[1.85rem] max-[430px]:leading-[1.1]"
            >
              {{
                language === 'ar'
                  ? 'مكان الحفل غير متوفر حاليًا'
                  : 'Le lieu de l’événement n’est pas encore disponible'
              }}
            </h3>

            <!-- Information rows -->
            <div
              class="info-list mt-[30px] border-t border-[#241b15]/[0.11] max-[430px]:mt-6"
            >

              <!-- Venue -->
              <div
                class="info-row flex min-w-0 items-center gap-4 border-b border-[#241b15]/[0.11] py-[17px] max-[700px]:gap-3 max-[430px]:gap-2.5 max-[430px]:py-[14px]"
              >
                <div
                  class="info-icon flex h-10 w-10 shrink-0 items-center justify-center border border-[#241b15]/[0.18] text-[#8e6937] transition duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] max-[700px]:h-9 max-[700px]:w-9 max-[430px]:h-8 max-[430px]:w-8"
                >
                  <svg
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 max-[430px]:h-4 max-[430px]:w-4"
                    aria-hidden="true"
                  >
                    <path
                      d="M4 20H20M6 20V9L12 4L18 9V20M9 20V14H15V20M8 10H8.01M12 10H12.01M16 10H16.01"
                      stroke="currentColor"
                      stroke-width="1.4"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                </div>

                <div class="min-w-0 flex flex-col gap-1">
                  <span
                    class="font-['Montserrat',sans-serif] text-[9px] font-semibold tracking-[0.2em] text-[#8e6937] max-[430px]:text-[7px]"
                  >
                    {{ language === 'ar' ? 'المكان' : 'LIEU' }}
                  </span>

                  <strong
                    class="break-words font-['Montserrat',sans-serif] text-[12px] font-medium text-[#4d3b2d] max-[700px]:text-[11px] max-[430px]:text-[9.5px]"
                  >
                    {{
                      language === 'ar'
                        ? 'غير متوفر حاليًا'
                        : 'Non disponible pour le moment'
                    }}
                  </strong>
                </div>
              </div>

              <!-- Date -->
              <div
                class="info-row flex min-w-0 items-center gap-4 border-b border-[#241b15]/[0.11] py-[17px] max-[700px]:gap-3 max-[430px]:gap-2.5 max-[430px]:py-[14px]"
              >
                <div
                  class="info-icon flex h-10 w-10 shrink-0 items-center justify-center border border-[#241b15]/[0.18] text-[#8e6937] transition duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] max-[700px]:h-9 max-[700px]:w-9 max-[430px]:h-8 max-[430px]:w-8"
                >
                  <svg
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 max-[430px]:h-4 max-[430px]:w-4"
                    aria-hidden="true"
                  >
                    <rect
                      x="3.5"
                      y="5"
                      width="17"
                      height="15"
                      rx="1"
                      stroke="currentColor"
                      stroke-width="1.4"
                    />
                    <path
                      d="M7.5 3.5V7M16.5 3.5V7M3.5 9H20.5"
                      stroke="currentColor"
                      stroke-width="1.4"
                    />
                  </svg>
                </div>

                <div class="min-w-0 flex flex-col gap-1">
                  <span
                    class="font-['Montserrat',sans-serif] text-[9px] font-semibold tracking-[0.2em] text-[#8e6937] max-[430px]:text-[7px]"
                  >
                    {{ language === 'ar' ? 'التاريخ' : 'DATE' }}
                  </span>

                  <strong
                    class="break-words font-['Montserrat',sans-serif] text-[12px] font-medium text-[#4d3b2d] max-[700px]:text-[11px] max-[430px]:text-[9.5px]"
                  >
                    {{
                      language === 'ar'
                        ? '16 جويلية 2030'
                        : '16 JUILLET 2030'
                    }}
                  </strong>
                </div>
              </div>

              <!-- Time -->
              <div
                class="info-row flex min-w-0 items-center gap-4 border-b border-[#241b15]/[0.11] py-[17px] max-[700px]:gap-3 max-[430px]:gap-2.5 max-[430px]:py-[14px]"
              >
                <div
                  class="info-icon flex h-10 w-10 shrink-0 items-center justify-center border border-[#241b15]/[0.18] text-[#8e6937] transition duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] max-[700px]:h-9 max-[700px]:w-9 max-[430px]:h-8 max-[430px]:w-8"
                >
                  <svg
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 max-[430px]:h-4 max-[430px]:w-4"
                    aria-hidden="true"
                  >
                    <circle
                      cx="12"
                      cy="12"
                      r="8.5"
                      stroke="currentColor"
                      stroke-width="1.4"
                    />
                    <path
                      d="M12 7V12L15.5 14"
                      stroke="currentColor"
                      stroke-width="1.4"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                </div>

                <div class="min-w-0 flex flex-col gap-1">
                  <span
                    class="font-['Montserrat',sans-serif] text-[9px] font-semibold tracking-[0.2em] text-[#8e6937] max-[430px]:text-[7px]"
                  >
                    {{ language === 'ar' ? 'الوقت' : 'HEURE' }}
                  </span>

                  <strong
                    class="break-words font-['Montserrat',sans-serif] text-[12px] font-medium text-[#4d3b2d] max-[700px]:text-[11px] max-[430px]:text-[9.5px]"
                  >
                    21:00 — 22:00
                  </strong>
                </div>
              </div>

            </div>

            <!-- Map (placeholder) -->
            <div class="mt-[27px] block max-[430px]:mt-5">
              <div
                class="relative h-[300px] overflow-hidden border border-[#241b15]/[0.18] bg-[#eee7da] shadow-[0_25px_65px_rgba(70,48,28,0.08),inset_0_0_40px_rgba(142,105,55,0.05)] max-[700px]:h-[270px] max-[430px]:h-[220px]"
              >

                <!-- Decorative map background -->
                <div class="map-background">
                  <div class="map-road road-one"></div>
                  <div class="map-road road-two"></div>
                  <div class="map-road road-three"></div>
                  <div class="map-road road-four"></div>

                  <div class="map-block block-one"></div>
                  <div class="map-block block-two"></div>
                  <div class="map-block block-three"></div>
                  <div class="map-block block-four"></div>
                  <div class="map-block block-five"></div>

                  <div class="map-circle map-circle-one"></div>
                  <div class="map-circle map-circle-two"></div>
                </div>

                <!-- Map center -->
                <div
                  class="absolute left-1/2 top-1/2 z-[5] flex min-w-0 -translate-x-1/2 -translate-y-1/2 flex-col items-center"
                >
                  <div class="map-pulse"></div>

                  <div
                    class="map-marker relative flex h-[66px] w-[66px] shrink-0 items-center justify-center rounded-full bg-[#8e6937] text-[#f8f4ec] shadow-[0_12px_35px_rgba(112,85,54,0.22)] max-[700px]:h-[58px] max-[700px]:w-[58px] max-[430px]:h-[50px] max-[430px]:w-[50px]"
                  >
                    <svg
                      viewBox="0 0 24 24"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-[27px] w-[27px] max-[700px]:h-6 max-[700px]:w-6 max-[430px]:h-5 max-[430px]:w-5"
                      aria-hidden="true"
                    >
                      <path
                        d="M12 21C15.5 16.8 18 14.1 18 10.5C18 7.18 15.31 4.5 12 4.5C8.69 4.5 6 7.18 6 10.5C6 14.1 8.5 16.8 12 21Z"
                        stroke="currentColor"
                        stroke-width="1.4"
                      />
                      <circle
                        cx="12"
                        cy="10.5"
                        r="2.2"
                        stroke="currentColor"
                        stroke-width="1.4"
                      />
                    </svg>
                  </div>

                  <span
                    class="mt-[18px] max-w-[calc(100vw-100px)] whitespace-nowrap border border-[#241b15]/[0.15] bg-[#fffdf8]/80 px-[13px] py-[7px] text-center font-['Montserrat',sans-serif] text-[9px] font-semibold tracking-[0.16em] text-[#705536] max-[700px]:mt-3 max-[430px]:px-2.5 max-[430px]:py-1.5 max-[430px]:text-[7px] max-[430px]:tracking-[0.08em]"
                  >
                    {{
                      language === 'ar'
                        ? 'المكان غير متوفر'
                        : 'LIEU NON DISPONIBLE'
                    }}
                  </span>
                </div>

                <!-- Compass -->
                <div
                  class="absolute right-[22px] top-[22px] flex h-[38px] w-[38px] flex-col items-center justify-center border border-[#241b15]/[0.18] font-['Montserrat',sans-serif] text-[9px] text-[#8e6937] opacity-70 max-[430px]:right-3 max-[430px]:top-3 max-[430px]:h-7 max-[430px]:w-7 max-[430px]:text-[7px]"
                  aria-hidden="true"
                >
                  <span>N</span>

                  <div
                    class="mt-[2px] h-[7px] w-[7px] rotate-45 border-l border-t border-[#8e6937] max-[430px]:h-1.5 max-[430px]:w-1.5"
                  ></div>
                </div>

                <!-- Map decorative border -->
                <div
                  class="pointer-events-none absolute inset-[14px] border border-[#241b15]/[0.1] max-[430px]:inset-2.5"
                ></div>

              </div>
            </div>

            <!-- Google Maps button (disabled) -->
            <div
              class="mt-[14px] flex min-h-[44px] w-full items-center justify-center gap-[9px] border border-[#241b15]/[0.12] bg-transparent px-[18px] py-[13px] text-center font-['Montserrat',sans-serif] text-[10px] font-semibold leading-[1.5] tracking-[0.10em] text-[#8e6937] opacity-40 max-[430px]:mt-3 max-[430px]:gap-1.5 max-[430px]:px-3 max-[430px]:py-2.5 max-[430px]:text-[8px] max-[430px]:tracking-[0.04em]"
            >
              <svg
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
                class="h-4 w-4 shrink-0 max-[430px]:h-3.5 max-[430px]:w-3.5"
                aria-hidden="true"
              >
                <path
                  d="M12 21C15.5 16.8 18 14.1 18 10.5C18 7.18 15.31 4.5 12 4.5C8.69 4.5 6 7.18 6 10.5C6 14.1 8.5 16.8 12 21Z"
                  stroke="currentColor"
                  stroke-width="1.4"
                />
                <circle
                  cx="12"
                  cy="10.5"
                  r="2.2"
                  stroke="currentColor"
                  stroke-width="1.4"
                />
              </svg>

              <span class="min-w-0">
                {{
                  language === 'ar'
                    ? 'الموقع غير متوفر حاليًا'
                    : 'EMPLACEMENT NON DISPONIBLE'
                }}
              </span>
            </div>

          </article>

        </div>

        <!-- =====================================================
             BOTTOM DECORATION
        ====================================================== -->

        <div
          class="location-footer mt-[55px] text-center max-[700px]:mt-10 max-[430px]:mt-8"
        >

          <div class="flex items-center justify-center gap-[13px] max-[430px]:gap-2">
            <span
              class="h-px w-[50px] bg-[#241b15]/[0.3] max-[430px]:w-[32px]"
            ></span>

            <div
              class="footer-diamond flex h-3 w-3 items-center justify-center border border-[#241b15] max-[430px]:h-2.5 max-[430px]:w-2.5"
            >
              <i class="h-1 w-1 bg-[#241b15]"></i>
            </div>

            <span
              class="h-px w-[50px] bg-[#241b15]/[0.3] max-[430px]:w-[32px]"
            ></span>
          </div>

          <p
            class="mx-auto mt-4 max-w-[600px] font-['Montserrat',sans-serif] text-[10px] font-semibold leading-[1.8] tracking-[0.18em] text-[#8e6937] max-[430px]:mt-3 max-[430px]:max-w-[300px] max-[430px]:text-[8px] max-[430px]:leading-[1.8] max-[430px]:tracking-[0.07em]"
          >
            {{
              language === 'ar'
                ? 'نتطلع للقائكم ومشاركتكم فرحتنا في هاتين المناسبتين'
                : 'Nous avons hâte de vous retrouver et de partager notre bonheur avec vous lors de ces deux moments'
            }}
          </p>

        </div>

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

const props = defineProps({
  language: {
    type: String,
    default: 'fr',
  },
})

const sectionRef = ref(null)
const isVisible = ref(false)

/* =========================================================
   INTERSECTION OBSERVER
========================================================= */

let observer = null

onMounted(() => {
  if (!sectionRef.value) return

  observer = new IntersectionObserver(
    ([entry]) => {
      isVisible.value = entry.isIntersecting
    },
    {
      threshold: 0.18,
    },
  )

  observer.observe(sectionRef.value)
})

onBeforeUnmount(() => {
  observer?.disconnect()
})
</script>


<style scoped>
/* ============================================================
   BASE
============================================================ */

.location-section {
  isolation: isolate;
}

/* ============================================================
   AMBIENT LIGHTS
============================================================ */

.location-glow {
  position: absolute;
  border-radius: 9999px;
  pointer-events: none;
  filter: blur(100px);
  will-change: transform;
}

.glow-one {
  width: 420px;
  height: 420px;
  top: -170px;
  right: -120px;
  background: rgba(155, 117, 63, 0.12);
  animation: locationGlowOne 22s ease-in-out infinite;
}

.glow-two {
  width: 380px;
  height: 380px;
  bottom: -160px;
  left: -100px;
  background: rgba(112, 85, 54, 0.09);
  animation: locationGlowTwo 25s ease-in-out infinite;
}

@keyframes locationGlowOne {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }

  50% {
    transform: translate3d(-45px, 45px, 0);
  }
}

@keyframes locationGlowTwo {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }

  50% {
    transform: translate3d(50px, -40px, 0);
  }
}

/* ============================================================
   PATTERN
============================================================ */

.location-pattern {
  position: absolute;
  inset: -10%;
  opacity: 0.045;

  background-image:
    linear-gradient(
      90deg,
      transparent 46%,
      #241b15 47%,
      #241b15 49%,
      transparent 50%
    ),
    linear-gradient(
      0deg,
      transparent 46%,
      #241b15 47%,
      #241b15 49%,
      transparent 50%
    );

  background-size: 90px 90px;
  transform: rotate(3deg);

  animation: locationPatternMove 42s linear infinite;
}

@keyframes locationPatternMove {
  from {
    background-position: 0 0;
  }

  to {
    background-position: 90px 90px;
  }
}

/* ============================================================
   GRID
============================================================ */

.location-grid {
  position: absolute;
  inset: 0;
  opacity: 0.055;

  background-image:
    radial-gradient(
      rgba(36, 27, 21, 0.45) 0.7px,
      transparent 0.7px
    );

  background-size: 32px 32px;

  animation: gridMove 34s linear infinite;
}

@keyframes gridMove {
  from {
    transform: translate3d(0, 0, 0);
  }

  to {
    transform: translate3d(32px, 32px, 0);
  }
}

/* ============================================================
   ORBITS
============================================================ */

.location-orbit {
  position: absolute;
  width: 170px;
  height: 170px;
  border: 1px solid rgba(36, 27, 21, 0.09);
  border-radius: 50%;
  pointer-events: none;
}

.orbit-one {
  top: 17%;
  left: -70px;
  animation: orbitFloatOne 24s ease-in-out infinite;
}

.orbit-two {
  right: -70px;
  bottom: 15%;
  width: 210px;
  height: 210px;
  animation: orbitFloatTwo 28s ease-in-out infinite;
}

@keyframes orbitFloatOne {
  0%,
  100% {
    transform: rotate(0deg) scale(1);
  }

  50% {
    transform: rotate(10deg) scale(1.035);
  }
}

@keyframes orbitFloatTwo {
  0%,
  100% {
    transform: rotate(0deg) scale(1);
  }

  50% {
    transform: rotate(-12deg) scale(1.03);
  }
}

/* ============================================================
   FLOATING DIAMONDS
============================================================ */

.floating-diamond {
  position: absolute;
  width: 10px;
  height: 10px;
  border: 1px solid rgba(36, 27, 21, 0.3);
  transform: rotate(45deg);
  pointer-events: none;
}

.location-diamond-one {
  top: 26%;
  left: 13%;
  animation: locationDiamondOne 18s ease-in-out infinite;
}

.location-diamond-two {
  top: 43%;
  right: 9%;
  animation: locationDiamondTwo 21s ease-in-out infinite;
}

.location-diamond-three {
  bottom: 18%;
  left: 22%;
  animation: locationDiamondThree 19s ease-in-out infinite;
}

@keyframes locationDiamondOne {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(45deg);
  }

  50% {
    transform: translate3d(10px, -8px, 0) rotate(90deg);
  }
}

@keyframes locationDiamondTwo {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(45deg);
  }

  50% {
    transform: translate3d(-9px, 10px, 0) rotate(90deg);
  }
}

@keyframes locationDiamondThree {
  0%,
  100% {
    transform: translate3d(0, 0, 0) rotate(45deg);
  }

  50% {
    transform: translate3d(8px, -10px, 0) rotate(135deg);
  }
}

/* ============================================================
   DOTS
============================================================ */

.floating-dot {
  position: absolute;
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: #241b15;
  opacity: 0.3;
  pointer-events: none;
}

.location-dot-one {
  top: 20%;
  right: 24%;
  animation: locationDot 14s ease-in-out infinite;
}

.location-dot-two {
  top: 65%;
  left: 10%;
  animation: locationDot 17s ease-in-out infinite 1s;
}

.location-dot-three {
  right: 22%;
  bottom: 23%;
  animation: locationDot 15s ease-in-out infinite 2s;
}

.location-dot-four {
  top: 34%;
  left: 25%;
  animation: locationDot 18s ease-in-out infinite 1.5s;
}

@keyframes locationDot {
  0%,
  100% {
    transform: translateY(0);
    opacity: 0.2;
  }

  50% {
    transform: translateY(-9px);
    opacity: 0.42;
  }
}

/* ============================================================
   FRAME CORNERS
============================================================ */

.frame-corner {
  position: absolute;
  width: 38px;
  height: 38px;
}

.frame-corner::before,
.frame-corner::after {
  content: "";
  position: absolute;
  background: #241b15;
  opacity: 0.55;
}

.frame-corner::before {
  width: 38px;
  height: 1px;
}

.frame-corner::after {
  width: 1px;
  height: 38px;
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
   HEADER REVEAL
============================================================ */

.location-label {
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

.location-active .location-label {
  opacity: 1;
  transform: translateY(0);
}

.location-label span:not(:nth-child(2)) {
  width: 32px;
  height: 1px;
  background: rgba(36, 27, 21, 0.28);
}

.location-intro {
  color: #705536;
  font-family: "Montserrat", sans-serif;
  font-size: 10px;
  letter-spacing: 0.25em;

  opacity: 0;
  transform: translateY(18px);

  transition:
    opacity 1.1s cubic-bezier(0.22, 1, 0.36, 1) 0.15s,
    transform 1.1s cubic-bezier(0.22, 1, 0.36, 1) 0.15s;
}

.location-active .location-intro {
  opacity: 1;
  transform: translateY(0);
}

.location-title {
  color: #30241c;
  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: clamp(2.5rem, 6vw, 4.5rem);
  font-weight: 500;
  line-height: 1;

  opacity: 0;
  transform: translateY(22px);

  transition:
    opacity 1.35s cubic-bezier(0.22, 1, 0.36, 1) 0.28s,
    transform 1.35s cubic-bezier(0.22, 1, 0.36, 1) 0.28s;
}

.location-active .location-title {
  opacity: 1;
  transform: translateY(0);
}

.location-description {
  color: #685545;
  font-family: "Montserrat", sans-serif;
  font-size: 13px;
  line-height: 1.9;

  opacity: 0;
  transform: translateY(18px);

  transition:
    opacity 1.1s cubic-bezier(0.22, 1, 0.36, 1) 0.42s,
    transform 1.1s cubic-bezier(0.22, 1, 0.36, 1) 0.42s;
}

.location-active .location-description {
  opacity: 1;
  transform: translateY(0);
}

.location-divider {
  opacity: 0;
  transform: scaleX(0.6);

  transition:
    opacity 1.1s ease 0.56s,
    transform 1.1s cubic-bezier(0.22, 1, 0.36, 1) 0.56s;
}

.location-active .location-divider {
  opacity: 1;
  transform: scaleX(1);
}

.location-divider span {
  width: 60px;
  height: 1px;
  background: rgba(36, 27, 21, 0.28);
}

.location-divider div {
  width: 9px;
  height: 9px;
  border: 1px solid #241b15;
  transform: rotate(45deg);

  animation: locationDivider 8s ease-in-out infinite;
}

@keyframes locationDivider {
  0%,
  100% {
    transform: rotate(45deg) scale(1);
  }

  50% {
    transform: rotate(90deg) scale(1.12);
  }
}

/* ============================================================
   MAP REVEAL
============================================================ */

.map-wrapper {
  opacity: 0;
  transform: translateX(-45px);

  transition:
    opacity 1.3s cubic-bezier(0.22, 1, 0.36, 1) 0.7s,
    transform 1.45s cubic-bezier(0.22, 1, 0.36, 1) 0.7s;
}

.location-active .map-wrapper {
  opacity: 1;
  transform: translateX(0);
}

/* ============================================================
   MAP BACKGROUND
============================================================ */

.map-background {
  position: absolute;
  inset: 0;
  opacity: 0.62;

  background:
    linear-gradient(
      25deg,
      transparent 35%,
      rgba(142, 105, 55, 0.07) 36%,
      rgba(142, 105, 55, 0.07) 37%,
      transparent 38%
    ),
    linear-gradient(
      140deg,
      transparent 42%,
      rgba(112, 85, 54, 0.075) 43%,
      rgba(112, 85, 54, 0.075) 44%,
      transparent 45%
    );

  background-size: 130px 130px;

  animation: mapBackgroundMove 34s linear infinite;
}

@keyframes mapBackgroundMove {
  from {
    background-position: 0 0;
  }

  to {
    background-position: 130px -130px;
  }
}

.map-road {
  position: absolute;
  height: 1px;
  background: rgba(112, 85, 54, 0.16);
  transform-origin: left center;
}

.road-one {
  width: 130%;
  top: 30%;
  left: -10%;
  transform: rotate(12deg);
}

.road-two {
  width: 120%;
  top: 67%;
  left: -5%;
  transform: rotate(-9deg);
}

.road-three {
  width: 95%;
  top: 48%;
  left: 5%;
  transform: rotate(55deg);
}

.road-four {
  width: 80%;
  top: 25%;
  left: 30%;
  transform: rotate(-58deg);
}

.map-block {
  position: absolute;
  border: 1px solid rgba(112, 85, 54, 0.1);
  background: rgba(255, 253, 248, 0.2);
}

.block-one {
  width: 100px;
  height: 65px;
  top: 14%;
  left: 14%;
  transform: rotate(12deg);
}

.block-two {
  width: 75px;
  height: 90px;
  top: 56%;
  left: 18%;
  transform: rotate(-8deg);
}

.block-three {
  width: 120px;
  height: 70px;
  top: 20%;
  right: 13%;
  transform: rotate(-17deg);
}

.block-four {
  width: 80px;
  height: 65px;
  right: 17%;
  bottom: 13%;
  transform: rotate(12deg);
}

.block-five {
  width: 60px;
  height: 50px;
  bottom: 28%;
  left: 45%;
  transform: rotate(24deg);
}

.map-circle {
  position: absolute;
  border-radius: 50%;
  border: 1px dashed rgba(142, 105, 55, 0.13);
}

.map-circle-one {
  width: 250px;
  height: 250px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.map-circle-two {
  width: 340px;
  height: 340px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* ============================================================
   MAP CENTER
============================================================ */

.map-pulse {
  position: absolute;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  border: 1px solid rgba(142, 105, 55, 0.18);

  animation: mapPulse 4.8s ease-out infinite;
}

@keyframes mapPulse {
  0% {
    transform: scale(0.55);
    opacity: 0.55;
  }

  100% {
    transform: scale(1.75);
    opacity: 0;
  }
}

.map-marker {
  animation: markerFloat 5s ease-in-out infinite;
}

@keyframes markerFloat {
  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-5px);
  }
}

/* ============================================================
   INFO CARD
============================================================ */

.location-info-wrapper {
  opacity: 0;
  transform: translateX(45px);

  transition:
    opacity 1.3s cubic-bezier(0.22, 1, 0.36, 1) 0.9s,
    transform 1.45s cubic-bezier(0.22, 1, 0.36, 1) 0.9s;
}

.location-active .location-info-wrapper {
  opacity: 1;
  transform: translateX(0);
}

.info-text {
  color: #685545;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  line-height: 1.9;
}

.info-row:hover .info-icon {
  transform: translateY(-3px);
  background: rgba(36, 27, 21, 0.035);
}

.info-ornament {
  animation: infoOrnament 8s linear infinite;
}

@keyframes infoOrnament {
  from {
    transform: rotate(45deg);
  }

  to {
    transform: rotate(405deg);
  }
}

/* ============================================================
   FOOTER
============================================================ */

.location-footer {
  opacity: 0;
  transform: translateY(18px);

  transition:
    opacity 1.1s cubic-bezier(0.22, 1, 0.36, 1) 1.35s,
    transform 1.1s cubic-bezier(0.22, 1, 0.36, 1) 1.35s;
}

.location-active .location-footer {
  opacity: 1;
  transform: translateY(0);
}

.footer-diamond {
  animation: footerDiamond 10s linear infinite;
}

@keyframes footerDiamond {
  from {
    transform: rotate(45deg);
  }

  to {
    transform: rotate(405deg);
  }
}

/* ============================================================
   ARABIC
============================================================ */

[dir="rtl"] .location-section {
  font-family: "Tahoma", "Arial", sans-serif;
}

[dir="rtl"] .location-title,
[dir="rtl"] .location-info-wrapper h3 {
  font-family: "Amiri", "Noto Naskh Arabic", serif;
}

[dir="rtl"] .location-description,
[dir="rtl"] .info-text {
  line-height: 2.15;
}

[dir="rtl"] .info-row {
  text-align: right;
}

/* ============================================================
   TABLET
============================================================ */

@media (max-width: 950px) {
  .location-layout {
    max-width: 720px;
    margin: 0 auto;
  }

  .location-info-wrapper {
    transform: translateY(40px);
  }

  .location-active .location-info-wrapper {
    transform: translateY(0);
  }

  .location-pattern,
  .location-grid {
    pointer-events: none;
  }
}

/* ============================================================
   MOBILE
============================================================ */

@media (max-width: 700px) {
  .location-label {
    font-size: 9px;
  }

  .location-label span:not(:nth-child(2)) {
    width: 25px;
  }

  .location-header {
    margin-bottom: 45px;
  }

  .location-title {
    font-size: 2.7rem;
    line-height: 1.1;
  }

  .location-description {
    font-size: 12px;
    line-height: 1.9;
  }

  .location-intro {
    line-height: 1.9;
  }

  .location-divider {
    gap: 8px;
  }

  .location-divider span {
    width: 45px;
  }

  .map-circle-one {
    width: 180px;
    height: 180px;
  }

  .map-circle-two {
    width: 250px;
    height: 250px;
  }

  .location-orbit {
    opacity: 0.45;
  }

  .location-glow {
    opacity: 0.7;
  }

  .floating-diamond,
  .floating-dot {
    opacity: 0.35;
  }

  .location-info-wrapper {
    min-width: 0;
  }
}

/* ============================================================
   SMALL MOBILE
============================================================ */

@media (max-width: 430px) {
  .location-header {
    margin-bottom: 34px;
  }

  .location-label {
    gap: 8px;
    font-size: 8px;
    letter-spacing: 0.16em;
  }

  .location-label span:not(:nth-child(2)) {
    width: 20px;
  }

  .location-intro {
    max-width: 320px;
    margin-left: auto;
    margin-right: auto;
    font-size: 9px;
    line-height: 1.9;
    letter-spacing: 0.12em;
  }

  .location-title {
    padding: 0 4px;
    font-size: clamp(2rem, 9.5vw, 2.35rem);
    line-height: 1.12;
  }

  .location-description {
    max-width: 310px;
    padding: 0 4px;
    font-size: 10.5px;
    line-height: 1.9;
  }

  [dir="rtl"] .location-title {
    line-height: 1.4;
  }

  [dir="rtl"] .location-description,
  [dir="rtl"] .info-text {
    line-height: 2;
  }

  .location-divider {
    margin-top: 20px;
    gap: 8px;
  }

  .location-divider span {
    width: 34px;
  }

  .location-divider div {
    width: 8px;
    height: 8px;
  }

  .location-info-wrapper {
    min-width: 0;
  }

  .info-text {
    font-size: 11px;
    line-height: 1.8;
  }

  .info-row {
    min-width: 0;
  }

  .info-row span {
    font-size: 7px;
  }

  .info-row strong {
    min-width: 0;
    overflow-wrap: anywhere;
  }

  .map-circle-one {
    width: 145px;
    height: 145px;
  }

  .map-circle-two {
    width: 205px;
    height: 205px;
  }

  .map-pulse {
    width: 75px;
    height: 75px;
  }

  .floating-diamond {
    opacity: 0.28;
  }

  .floating-dot {
    opacity: 0.22;
  }

  .location-orbit {
    opacity: 0.25;
  }

  .location-glow {
    opacity: 0.5;
  }

  .location-pattern {
    opacity: 0.025;
  }

  .location-grid {
    opacity: 0.035;
  }

  .frame-corner {
    width: 28px;
    height: 28px;
  }

  .frame-corner::before {
    width: 28px;
  }

  .frame-corner::after {
    height: 28px;
  }

  .location-footer {
    padding-bottom: 16px;
  }
}

/* ============================================================
   VERY SMALL PHONES
============================================================ */

@media (max-width: 360px) {
  .location-intro {
    font-size: 8.5px;
    letter-spacing: 0.08em;
  }

  .location-title {
    font-size: 2rem;
  }

  .location-description {
    font-size: 10px;
  }

  .location-info-wrapper {
    padding-left: 14px;
    padding-right: 14px;
  }

  .info-row {
    gap: 8px;
  }

  .info-icon {
    width: 29px;
    height: 29px;
  }

  .info-row strong {
    font-size: 9px;
  }

  .map-marker {
    width: 46px;
    height: 46px;
  }

  .map-marker svg {
    width: 18px;
    height: 18px;
  }

  .location-footer p {
    max-width: 280px;
    font-size: 7.5px;
    letter-spacing: 0.04em;
  }
}

/* ============================================================
   REDUCED MOTION
============================================================ */

@media (prefers-reduced-motion: reduce) {
  .location-glow,
  .location-pattern,
  .location-grid,
  .location-orbit,
  .floating-diamond,
  .floating-dot,
  .location-divider div,
  .map-background,
  .map-pulse,
  .map-marker,
  .info-ornament,
  .footer-diamond {
    animation: none !important;
  }

  .location-header *,
  .map-wrapper,
  .location-info-wrapper,
  .location-footer {
    transition: none !important;
  }
}
</style>