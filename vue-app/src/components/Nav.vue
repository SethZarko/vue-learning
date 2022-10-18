<template>
    <div class="nav-container">
        <header>
            <nav>
                <img src="../assets/logo.png" alt="">
                <i class="fa-solid fa-bars"></i>
                <ul>
                    <li><a href="#/">Home</a></li>
                    <li><a href="#/about">About</a></li>
                    <li><a href="#/services">Services</a></li>
                    <li><a href="#/contact">Contact</a></li>
                </ul>
            </nav>
        </header>
        <component :is="currentView" />
    </div>
</template>

<script>
import Home from './Home.vue'
import About from './About.vue'
import Services from './Services.vue'
import Contact from './Contact.vue'

const routes = {
  '/': Home,
  '/about': About,
  '/services': Services,
  '/contact': Contact,
}

export default {
    name: 'Nav-comp',

    data() {
        return {
        currentPath: window.location.hash
        }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/']
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
		this.currentPath = window.location.hash
	})
  }
}
</script>

<style scoped>
    header {
        width: 100%;
        padding: 2em;
        background: black;
        margin-bottom: 2em;
    }

    ul {
        display: flex;
        align-items: center;
        justify-content: space-between;
        width: 50%;
        position: absolute;
        right: 50px;
        top: 30px;
    }

    li {
        list-style-type: none;
    }

    a {
        color: white;
        text-decoration: none;
        font-size: 1.25rem;
    }

    img {
        display: block;
        height: 30px;
    }

    .fa-bars {
        color: white;
        font-size: 2rem;
        position: absolute;
        right: 40px;
        top: 30px;
        cursor: pointer;
    }

    @media (min-width: 769px) {
        .fa-bars {
            display: none;
        }
    }

    @media (max-width: 768px) {
        ul {
            display: none;
        }
    }
</style>