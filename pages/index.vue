<template>
    <div class="min-h-screen bg-gradient-to-b from-gray-900 to-gray-800 text-gray-100 font-sans">
        <!-- Navbar -->
        <nav class="fixed top-0 w-full z-50 bg-gray-900/90 backdrop-blur-md border-b border-gray-800 py-4 px-6">
            <div class="max-w-7xl mx-auto flex justify-between items-center">
                <a href="#home" class="text-xl font-bold flex items-center" @click.prevent="scrollToSection('home')">
                    <div
                        class="w-8 h-8 rounded-full bg-gradient-to-r from-indigo-500 to-purple-600 mr-2 flex items-center justify-center">
                        <span class="text-white font-bold">P</span>
                    </div>
                    <span
                        class="bg-gradient-to-r from-indigo-400 to-purple-500 bg-clip-text text-transparent">Portfolio</span>
                </a>

                <div class="hidden md:flex space-x-8">
                    <a v-for="link in navLinks" :key="link.id" :href="link.href"
                        @click.prevent="scrollToSection(link.href.substring(1))"
                        class="nav-link text-slate-300 hover:text-white transition-all duration-300 relative group">
                        {{ link.label }}
                        <div
                            class="absolute bottom-0 left-0 w-0 h-0.5 bg-gradient-to-r from-indigo-500 to-purple-600 transition-all duration-300 group-hover:w-full">
                        </div>
                    </a>
                </div>

                <button @click="toggleTheme" class="p-2 rounded-full bg-gray-800 hover:bg-gray-700 transition-colors">
                    <i :class="darkMode ? 'fas fa-sun text-yellow-400' : 'fas fa-moon text-indigo-400'"></i>
                </button>
            </div>
        </nav>

        <!-- Main Content -->
        <main>
            <!-- Hero Section -->
            <section id="home" class="min-h-screen flex items-center justify-center relative overflow-hidden pt-16">
                <div class="absolute inset-0 z-0">
                    <div
                        class="absolute top-20 left-1/4 w-64 h-64 bg-purple-500 rounded-full filter blur-3xl opacity-20 animate-pulse">
                    </div>
                    <div
                        class="absolute bottom-20 right-1/4 w-72 h-72 bg-indigo-500 rounded-full filter blur-3xl opacity-20 animate-pulse">
                    </div>
                    <div
                        class="absolute top-1/3 right-1/3 w-48 h-48 bg-pink-500 rounded-full filter blur-3xl opacity-15 animate-pulse animation-delay-2000">
                    </div>
                </div>

                <div class="relative z-10 text-center space-y-8 max-w-4xl px-4">
                    <div class="animate-fade-in">
                        <div class="inline-block mb-6">
                            <div class="bg-gradient-to-r from-indigo-500 to-purple-600 p-1 rounded-full animate-float">
                                <div class="bg-gray-900 rounded-full p-1">
                                    <img src="https://images.unsplash.com/photo-1534030347209-467a5b0ad3e6?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&h=300&q=80"
                                        alt="Profile"
                                        class="w-32 h-32 rounded-full object-cover border-4 border-gray-800">
                                </div>
                            </div>
                        </div>

                        <div class="mb-6">
                            <span
                                class="inline-block px-4 py-1 bg-gray-800 text-indigo-400 rounded-full text-sm font-medium mb-4">
                                Développeur Full-Stack
                            </span>
                            <h1 class="text-5xl md:text-6xl font-bold mb-4 animate-slide-up">
                                Bonjour, je suis <span
                                    class="bg-gradient-to-r from-indigo-400 to-purple-500 bg-clip-text text-transparent">Fred</span>
                            </h1>
                            <p class="text-xl text-gray-300 max-w-2xl mx-auto animate-slide-up animation-delay-100">
                                Je transforme des idées en expériences digitales exceptionnelles
                            </p>
                        </div>

                        <div class="mt-10 flex justify-center gap-4 animate-slide-up animation-delay-200">
                            <button @click="scrollToSection('contact')"
                                class="px-8 py-3 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-full font-medium shadow-lg shadow-indigo-500/30 hover:shadow-indigo-500/50 transition-all transform hover:scale-105">
                                Me contacter
                            </button>
                            <button @click="scrollToSection('projects')"
                                class="px-8 py-3 rounded-full font-medium border border-gray-700 bg-gray-800/50 hover:bg-gray-800 transition-all">
                                Voir mes projets
                            </button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- À propos -->
            <section id="about" class="py-24 relative">
                <div class="absolute top-0 left-0 w-full h-16 bg-gradient-to-b from-gray-900 to-transparent z-10"></div>
                <div class="max-w-7xl mx-auto px-6 relative z-20">
                    <div class="text-center mb-16">
                        <div class="inline-flex items-center justify-center mb-4">
                            <div class="w-16 h-px bg-gradient-to-r from-transparent via-indigo-500 to-transparent">
                            </div>
                            <span class="px-4 text-indigo-400 font-medium">À propos</span>
                            <div class="w-16 h-px bg-gradient-to-r from-transparent via-indigo-500 to-transparent">
                            </div>
                        </div>
                        <h2 class="text-4xl font-bold">
                            Mon parcours et <span
                                class="bg-gradient-to-r from-indigo-400 to-purple-500 bg-clip-text text-transparent">passion</span>
                        </h2>
                    </div>

                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                        <div class="flex justify-center animate-slide-right">
                            <div class="relative">
                                <div
                                    class="absolute -inset-4 bg-gradient-to-r from-indigo-500 to-purple-600 rounded-2xl rotate-6 opacity-30 animate-pulse">
                                </div>
                                <div
                                    class="relative bg-gray-800 rounded-2xl overflow-hidden border border-gray-700 p-6">
                                    <div class="flex items-start space-x-6">
                                        <div class="flex-shrink-0">
                                            <div
                                                class="w-16 h-16 rounded-full bg-gradient-to-r from-indigo-500 to-purple-600 flex items-center justify-center">
                                                <i class="fas fa-code text-white text-2xl"></i>
                                            </div>
                                        </div>
                                        <div>
                                            <h3 class="text-xl font-semibold mb-2">Expert en développement</h3>
                                            <p class="text-gray-400">
                                                Plus de 7 ans d'expérience dans la création d'applications web modernes
                                                et performantes.
                                            </p>
                                        </div>
                                    </div>

                                    <div class="flex items-start space-x-6 mt-8">
                                        <div class="flex-shrink-0">
                                            <div
                                                class="w-16 h-16 rounded-full bg-gradient-to-r from-pink-500 to-purple-500 flex items-center justify-center">
                                                <i class="fas fa-paint-brush text-white text-2xl"></i>
                                            </div>
                                        </div>
                                        <div>
                                            <h3 class="text-xl font-semibold mb-2">Design & UX</h3>
                                            <p class="text-gray-400">
                                                Passionné par la création d'interfaces utilisateur élégantes et
                                                intuitives.
                                            </p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="animate-slide-left">
                            <div class="bg-gray-800/50 backdrop-blur-sm border border-gray-700 rounded-2xl p-8">
                                <h3 class="text-2xl font-semibold mb-6">Mon histoire</h3>
                                <p class="text-gray-300 mb-6">
                                    Développeur Full-Stack passionné, je me spécialise dans la création d'applications
                                    web modernes avec Vue.js, Nuxt.js et Node.js.
                                    Mon parcours m'a permis de travailler sur divers projets allant des startups aux
                                    grandes entreprises.
                                </p>
                                <p class="text-gray-300 mb-6">
                                    J'accorde une importance particulière à la qualité du code, aux performances et à
                                    l'expérience utilisateur.
                                    Mon objectif est de créer des solutions qui allient élégance et fonctionnalité.
                                </p>

                                <div class="mt-10">
                                    <div class="flex justify-between items-center mb-6">
                                        <h4 class="text-xl font-semibold">Mes compétences clés</h4>
                                        <span class="text-indigo-400 font-medium">En savoir plus</span>
                                    </div>
                                    <div class="grid grid-cols-2 gap-4">
                                        <div v-for="skill in keySkills" :key="skill" class="flex items-center">
                                            <div class="w-2 h-2 rounded-full bg-indigo-500 mr-3"></div>
                                            <span class="text-gray-300">{{ skill }}</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Projets -->
            <section id="projects" class="py-24 bg-gradient-to-br from-gray-900 to-gray-800">
                <div class="max-w-7xl mx-auto px-6">
                    <div class="text-center mb-16">
                        <div class="inline-flex items-center justify-center mb-4">
                            <div class="w-16 h-px bg-gradient-to-r from-transparent via-indigo-500 to-transparent">
                            </div>
                            <span class="px-4 text-indigo-400 font-medium">Projets</span>
                            <div class="w-16 h-px bg-gradient-to-r from-transparent via-indigo-500 to-transparent">
                            </div>
                        </div>
                        <h2 class="text-4xl font-bold mb-4">
                            Mes <span
                                class="bg-gradient-to-r from-indigo-400 to-purple-500 bg-clip-text text-transparent">réalisations</span>
                        </h2>
                        <p class="text-gray-400 max-w-2xl mx-auto">Découvrez une sélection de mes projets récents</p>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <div v-for="(project, index) in projects" :key="project.id"
                            class="bg-gray-800/50 backdrop-blur-sm border border-gray-700 rounded-2xl overflow-hidden transition-all duration-300 hover:border-indigo-500 group"
                            :class="`animate-fade-in animation-delay-${(index % 3) * 100}`">
                            <div class="relative overflow-hidden h-60">
                                <img :src="project.image" :alt="project.title"
                                    class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110" />
                                <div class="absolute inset-0 bg-gradient-to-t from-gray-900 to-transparent"></div>
                                <div class="absolute top-4 right-4">
                                    <span class="px-3 py-1 bg-indigo-500 rounded-full text-xs font-medium">{{
                                        project.category }}</span>
                                </div>
                            </div>

                            <div class="p-6">
                                <div class="flex justify-between items-start mb-3">
                                    <h3 class="text-xl font-bold group-hover:text-indigo-400 transition-colors">{{
                                        project.title }}</h3>
                                    <i
                                        class="fas fa-arrow-up-right-from-square text-gray-500 group-hover:text-indigo-400 transition-colors"></i>
                                </div>
                                <p class="text-gray-400 mb-4">{{ project.description }}</p>

                                <div class="flex flex-wrap gap-2 mb-5">
                                    <span v-for="tech in project.technologies" :key="tech"
                                        class="px-3 py-1 bg-gray-700 rounded-full text-xs">
                                        {{ tech }}
                                    </span>
                                </div>

                                <div class="flex justify-between">
                                    <button class="text-indigo-400 hover:text-indigo-300 transition-colors">
                                        Voir le projet
                                    </button>
                                    <button
                                        class="text-gray-400 hover:text-gray-300 transition-colors flex items-center">
                                        <i class="fab fa-github mr-2"></i>
                                        Code
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Formulaire de Contact Premium -->
            <section id="contact" class="py-24 relative">
                <div class="max-w-5xl mx-auto px-6">
                    <div class="text-center mb-16">
                        <div class="inline-flex items-center justify-center mb-4">
                            <div class="w-16 h-px bg-gradient-to-r from-transparent via-indigo-500 to-transparent">
                            </div>
                            <span class="px-4 text-indigo-400 font-medium">Contact</span>
                            <div class="w-16 h-px bg-gradient-to-r from-transparent via-indigo-500 to-transparent">
                            </div>
                        </div>
                        <h2 class="text-4xl font-bold mb-4">
                            Travaillons <span
                                class="bg-gradient-to-r from-indigo-400 to-purple-500 bg-clip-text text-transparent">ensemble</span>
                        </h2>
                        <p class="text-gray-400 max-w-2xl mx-auto">Discutons de votre projet et voyons comment je peux
                            vous aider</p>
                    </div>

                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
                        <div class="animate-slide-right">
                            <div class="bg-gray-800/50 backdrop-blur-sm border border-gray-700 rounded-2xl p-8 h-full">
                                <h3 class="text-2xl font-semibold mb-6">Informations</h3>

                                <div class="space-y-6 mb-10">
                                    <div class="flex items-start">
                                        <div class="p-3 bg-indigo-500/10 rounded-lg mr-4">
                                            <i class="fas fa-envelope text-indigo-400 text-xl"></i>
                                        </div>
                                        <div>
                                            <h4 class="font-medium text-gray-300">Email</h4>
                                            <p class="text-gray-400">contact@monportfolio.com</p>
                                        </div>
                                    </div>

                                    <div class="flex items-start">
                                        <div class="p-3 bg-purple-500/10 rounded-lg mr-4">
                                            <i class="fas fa-map-marker-alt text-purple-400 text-xl"></i>
                                        </div>
                                        <div>
                                            <h4 class="font-medium text-gray-300">Localisation</h4>
                                            <p class="text-gray-400">Paris, France</p>
                                        </div>
                                    </div>

                                    <div class="flex items-start">
                                        <div class="p-3 bg-blue-500/10 rounded-lg mr-4">
                                            <i class="fas fa-phone text-blue-400 text-xl"></i>
                                        </div>
                                        <div>
                                            <h4 class="font-medium text-gray-300">Téléphone</h4>
                                            <p class="text-gray-400">+33 6 12 34 56 78</p>
                                        </div>
                                    </div>
                                </div>

                                <div class="mt-10">
                                    <h4 class="font-medium text-gray-300 mb-4">Suivez-moi</h4>
                                    <div class="flex space-x-4">
                                        <button
                                            class="p-3 bg-gray-700/50 hover:bg-indigo-500/20 hover:text-indigo-400 rounded-lg transition-colors">
                                            <i class="fab fa-linkedin-in text-xl"></i>
                                        </button>
                                        <button
                                            class="p-3 bg-gray-700/50 hover:bg-purple-500/20 hover:text-purple-400 rounded-lg transition-colors">
                                            <i class="fab fa-github text-xl"></i>
                                        </button>
                                        <button
                                            class="p-3 bg-gray-700/50 hover:bg-blue-500/20 hover:text-blue-400 rounded-lg transition-colors">
                                            <i class="fab fa-twitter text-xl"></i>
                                        </button>
                                        <button
                                            class="p-3 bg-gray-700/50 hover:bg-pink-500/20 hover:text-pink-400 rounded-lg transition-colors">
                                            <i class="fab fa-dribbble text-xl"></i>
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="animate-slide-left">
                            <div
                                class="bg-gradient-to-br from-gray-800 to-gray-900 border border-gray-700 rounded-2xl p-8 relative overflow-hidden">
                                <div
                                    class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-indigo-500 to-purple-600">
                                </div>

                                <h3 class="text-2xl font-semibold mb-6">Envoyez un message</h3>

                                <form class="space-y-6">
                                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                        <div>
                                            <label class="block text-gray-300 mb-2">Votre nom</label>
                                            <div class="relative">
                                                <input type="text"
                                                    class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 focus:border-indigo-500 focus:ring-1 focus:ring-indigo-500 outline-none transition-all"
                                                    placeholder="John Doe">
                                                <div class="absolute inset-y-0 right-0 flex items-center pr-3">
                                                    <i class="fas fa-user text-gray-500"></i>
                                                </div>
                                            </div>
                                        </div>

                                        <div>
                                            <label class="block text-gray-300 mb-2">Votre email</label>
                                            <div class="relative">
                                                <input type="email"
                                                    class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 focus:border-indigo-500 focus:ring-1 focus:ring-indigo-500 outline-none transition-all"
                                                    placeholder="john@example.com">
                                                <div class="absolute inset-y-0 right-0 flex items-center pr-3">
                                                    <i class="fas fa-envelope text-gray-500"></i>
                                                </div>
                                            </div>
                                        </div>
                                    </div>

                                    <div>
                                        <label class="block text-gray-300 mb-2">Sujet</label>
                                        <div class="relative">
                                            <input type="text"
                                                class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 focus:border-indigo-500 focus:ring-1 focus:ring-indigo-500 outline-none transition-all"
                                                placeholder="Demande de projet">
                                            <div class="absolute inset-y-0 right-0 flex items-center pr-3">
                                                <i class="fas fa-tag text-gray-500"></i>
                                            </div>
                                        </div>
                                    </div>

                                    <div>
                                        <label class="block text-gray-300 mb-2">Votre message</label>
                                        <div class="relative">
                                            <textarea
                                                class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 h-32 focus:border-indigo-500 focus:ring-1 focus:ring-indigo-500 outline-none transition-all resize-none"
                                                placeholder="Décrivez votre projet..."></textarea>
                                            <div class="absolute top-3 right-0 flex items-center pr-3">
                                                <i class="fas fa-pen text-gray-500"></i>
                                            </div>
                                        </div>
                                    </div>

                                    <button
                                        class="w-full bg-gradient-to-r from-indigo-600 to-purple-600 rounded-lg px-6 py-4 font-medium shadow-lg shadow-indigo-500/30 hover:shadow-indigo-500/50 transition-all transform hover:scale-[1.02] mt-4">
                                        Envoyer le message
                                    </button>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </main>

        <!-- Footer -->
        <footer class="border-t border-gray-800 py-10">
            <div class="max-w-7xl mx-auto px-6">
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <div class="mb-6 md:mb-0">
                        <div class="flex items-center">
                            <div
                                class="w-8 h-8 rounded-full bg-gradient-to-r from-indigo-500 to-purple-600 flex items-center justify-center">
                                <span class="text-white font-bold">P</span>
                            </div>
                            <span
                                class="text-xl font-bold bg-gradient-to-r from-indigo-400 to-purple-500 bg-clip-text text-transparent ml-2">Portfolio</span>
                        </div>
                        <p class="text-gray-500 mt-2">Créateur d'expériences numériques exceptionnelles</p>
                    </div>

                    <div class="flex space-x-6">
                        <a v-for="link in navLinks" :key="`footer-${link.id}`" :href="link.href"
                            @click.prevent="scrollToSection(link.href.substring(1))"
                            class="text-gray-500 hover:text-gray-300 transition-colors">
                            {{ link.label }}
                        </a>
                    </div>
                </div>

                <div class="mt-10 pt-6 border-t border-gray-800 text-center text-gray-500 text-sm">
                    <p>&copy; {{ new Date().getFullYear() }} Fred AGNILO. Tous droits réservés.</p>
                </div>
            </div>
        </footer>

        <!-- Scroll to top -->
        <button v-if="showScrollTop" @click="scrollToTop"
            class="fixed bottom-8 right-8 rounded-full p-3 bg-gradient-to-r from-indigo-600 to-purple-600 shadow-lg shadow-indigo-500/30 hover:shadow-indigo-500/50 transition-all">
            <i class="fas fa-arrow-up text-white"></i>
        </button>
    </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

// Données réactives
const darkMode = ref(true)
const showScrollTop = ref(false)
const navLinks = ref([
  { id: 1, label: 'Accueil', href: '#home' },
  { id: 2, label: 'À propos', href: '#about' },
  { id: 3, label: 'Projets', href: '#projects' },
  { id: 4, label: 'Contact', href: '#contact' },
])
const keySkills = ref([
  'Développement Frontend',
  'Architecture Backend',
  'Design UI/UX',
  'Optimisation SEO',
  'Responsive Design',
  'Intégration continue',
])
const projects = ref([
  {
    id: 1,
    title: 'Plateforme E-commerce',
    description: 'Solution complète avec gestion de produits, panier et paiement sécurisé.',
    image: 'https://images.unsplash.com/photo-1607082350899-7e105aa886ae?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&h=600&q=80',
    category: 'Full-Stack',
    technologies: ['Vue.js', 'Nuxt.js', 'Node.js', 'MongoDB'],
  },
  {
    id: 2,
    title: 'Dashboard Analytics',
    description: 'Tableau de bord de données avec visualisations interactives en temps réel.',
    image: 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&h=600&q=80',
    category: 'Frontend',
    technologies: ['Vue.js', 'D3.js', 'Tailwind CSS', 'GraphQL'],
  },
  {
    id: 3,
    title: 'Application Mobile',
    description: 'Application cross-platform pour la gestion de tâches et de projets.',
    image: 'https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&h=600&q=80',
    category: 'Mobile',
    technologies: ['React Native', 'Firebase', 'Redux', 'TypeScript'],
  },
])

// Gestion du mode sombre
const toggleTheme = () => {
  darkMode.value = !darkMode.value
  if (darkMode.value) {
    document.documentElement.classList.add('dark')
  } else {
    document.documentElement.classList.remove('dark')
  }
}

// Gestion du scroll
const handleScroll = () => {
  showScrollTop.value = window.scrollY > 300
}

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
}

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    const start = window.pageYOffset
    const target = element.getBoundingClientRect().top + window.pageYOffset - 80
    const duration = 800
    const startTime = performance.now()

    const ease = (t) => {
      return t < 0.5 ? 4 * t * t * t : (t - 1) * (2 * t - 2) * (2 * t - 2) + 1
    }

    const animateScroll = (currentTime) => {
      const elapsed = currentTime - startTime
      const progress = Math.min(elapsed / duration, 1)
      const easedProgress = ease(progress)

      window.scrollTo(0, start + (target - start) * easedProgress)

      if (progress < 1) {
        requestAnimationFrame(animateScroll)
      }
    }

    requestAnimationFrame(animateScroll)
  }
}

// Initialisation des animations
const initAnimations = () => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('animate-visible')
        }
      })
    },
    { threshold: 0.1 }
  )

  document
    .querySelectorAll('.animate-fade-in, .animate-slide-up, .animate-slide-left, .animate-slide-right')
    .forEach((el) => {
      observer.observe(el)
    })
}

// Hooks de cycle de vie
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  handleScroll()
  document.documentElement.classList.add('dark') // Mode sombre par défaut
  initAnimations()
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

body {
    font-family: 'Inter', sans-serif;
}

.nav-link {
    position: relative;
    transition: all 0.3s ease;
}

.animate-float {
    animation: float 6s ease-in-out infinite;
}

.animate-fade-in {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

.animate-slide-up {
    opacity: 0;
    transform: translateY(40px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

.animate-slide-left {
    opacity: 0;
    transform: translateX(40px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

.animate-slide-right {
    opacity: 0;
    transform: translateX(-40px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

.animate-visible {
    opacity: 1;
    transform: translate(0, 0);
}

.animation-delay-100 {
    transition-delay: 0.1s;
}

.animation-delay-200 {
    transition-delay: 0.2s;
}

.animation-delay-300 {
    transition-delay: 0.3s;
}

@keyframes float {

    0%,
    100% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-15px);
    }
}

@media (max-width: 768px) {

    .animate-slide-left,
    .animate-slide-right {
        transform: translateY(30px);
    }

    .animate-visible {
        transform: translateY(0);
    }
}
</style>