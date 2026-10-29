<template>

    <div class="relative h-dvh w-full overflow-hidden bg-black">

        <!-- Fond animé -->
        <div class="absolute inset-0">
            <Grainient
                :colors="['#0b0618', '#2e1065', '#7c3aed', '#c4b5fd', '#f5f3ff']"
                :angle="150"
                :bands="1"
                :softness="1"
                :silk="0.4"
            />
        </div>

        <!-- Présentation, au-dessus du fond -->
        <section
            class="relative z-10 mx-auto flex h-full max-w-6xl flex-col items-center justify-center gap-12 px-6 pt-24 text-white md:flex-row md:justify-between md:gap-16"
        >

            <!-- Texte de présentation -->
            <div class="flex max-w-xl flex-col items-center gap-6 text-center md:items-start md:text-left">

                

                <h1 class="flex flex-wrap items-center justify-center gap-[0.2em] text-4xl font-black md:justify-start md:text-6xl">
                    <span>Je suis</span>
                    <RotatingText
                        ref="rotator"
                        :loop="false"
                        :texts="['curieux', 'motivé', 'un gangster', 'Mathys']"
                        effect="drop"
                        highlight
                        highlight-color="#7c3aed"
                        :stagger-duration="0.04"
                        split-level-class="overflow-hidden pb-1"
                        @next="onNext"
                    />
                </h1>

                <p class="text-lg/relaxed text-white/80 md:text-xl/relaxed">
                    Développeur fullstack, je conçois des applications web modernes,
                    du back-end jusqu'à l'interface. J'aime le code propre, les
                    interfaces soignées et les projets qui ont du sens.
                </p>

                <div class="flex flex-wrap justify-center gap-3 md:justify-start">
                    <a
                        href="#work"
                        class="rounded-full bg-white px-6 py-3 font-semibold text-violet-950 shadow-lg transition hover:bg-violet-100"
                    >
                        Voir mes projets
                    </a>
                    <a
                        href="#contact"
                        class="rounded-full px-6 py-3 font-semibold ring-1 ring-white/40 backdrop-blur-md transition hover:bg-white/10"
                    >
                        Me contacter
                    </a>
                </div>

                <ul class="flex flex-wrap justify-center gap-2 text-sm text-white/70 md:justify-start">
                    <li v-for="tech in stack" :key="tech" class="rounded-full bg-white/5 px-3 py-1 ring-1 ring-white/10">
                        {{ tech }}
                    </li>
                </ul>

            </div>

            <!-- Carte de profil -->
            <div class="hero-card shrink-0">
                <div class="hero-card__float">
                    <ProfileCard />
                </div>
            </div>

        </section>

    </div>

</template>

<script lang="ts" setup>

    import Grainient from '~/components/ui/grainient/Grainient.vue';
    import ProfileCard from '../ProfileCard.vue';

    import RotatingText from '~/components/ui/rotating-text/RotatingText.vue';

    const stack = ['Vue.js', 'TypeScript', 'Tailwind CSS', 'Node.js'];

    function onNext(index: number) {
        console.log('now showing', index);
    }

</script>

<style scoped>
    /* Carte penchée en 3D, qui se redresse au survol */
    .hero-card {
        perspective: 1200px;
    }

    .hero-card__float {
        transform: rotateY(-14deg) rotateX(6deg) rotateZ(4deg);
        transition: transform 0.6s cubic-bezier(0.16, 1, 0.3, 1);
        animation: hero-card-float 6s ease-in-out infinite;
        filter: drop-shadow(0 30px 40px rgba(46, 16, 101, 0.55));
    }

    .hero-card:hover .hero-card__float {
        transform: rotateY(0deg) rotateX(0deg) rotateZ(0deg);
        animation-play-state: paused;
    }

    /* Léger flottement de haut en bas */
    @keyframes hero-card-float {
        0%, 100% { translate: 0 0; }
        50%      { translate: 0 -14px; }
    }

    @media (prefers-reduced-motion: reduce) {
        .hero-card__float {
            animation: none;
        }
    }
</style>
