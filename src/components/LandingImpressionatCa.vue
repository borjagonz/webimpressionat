<template>
  <div class="landing">
    <header class="hero">
      <div class="overlay">
<nav :class="['navbar', { scrolled: isScrolled }]">

  <img
    class="logo"
    src="../assets/Logo-Impressionat.png"
    alt="LogoImpressionat"
  >

  <button class="hamburger" @click="toggleMenu">
    ☰
  </button>

  <div :class="['navlinks', { open: menuOpen }]">

    <a
      href="#services"
      class="call-button"
      @click="menuOpen = false"
    >
      Serveis
    </a>

    <p>|</p>

    <a
      href="#contacta"
      class="call-button"
      @click="menuOpen = false"
    >
      Contacta
    </a>

    <p>|</p>

    <a
      href="#galeria"
      class="call-button"
      @click="menuOpen = false"
    >
      Qui som
    </a>

  </div>

</nav>
        <div class="hero-content">
          <a class="badge" href="#reviews"><span class="badge-span">★</span>4,7 · 100 Ressenyes</a>

          <h2>Vols Imprimir?</h2>

          <p>
            Impressió professional, enquadernacions, currículums,
            fotocòpies i molt més amb un tracte proper i amable.
          </p>

          <div class="hero-buttons">
  <a
    :href="whatsappLink"
    target="_blank"
    rel="noopener noreferrer"
    class="primary-btn"
  >
    WhatsApp 💬
  </a>

            <a
              href="#info"
              class="secondary-btn"
            >
              Com arribar            </a>
          </div>
        </div>
      </div>
    </header>

    <section id="services" class="services">
      <h3>Què fem?</h3>

      <div class="cards">
        <div class="card">
          <img class="card-img" src="../assets/impressions.svg" alt="impressions">
          <h4>Impressions</h4>
          <p>
            Posters, flyers, roll-ups, tríptics, targetes, adhesius, i molt més.
          </p>
        </div>

        <div class="card">
          <img class="card-img" src="../assets/enquadernacions.svg" alt="enquadernacions">
          <h4>Enquadernacions</h4>
          <p>
            Llibres, tesis, revistes, dossiers i documents perfectament acabats.
          </p>
        </div>

        <div class="card">
          <img class="card-img" src="../assets/fotocopies.svg" alt="fotocopies">
          <h4>Fotocòpies</h4>
          <p>
            Servei ràpid, econòmic i molt eficient per al teu dia a dia.
          </p>
        </div>

        <div class="card">
          <img class="card-img" src="../assets/curriculums.svg" alt="curriculums">
          <h4>Currículums</h4>
          <p>
            Impressió professional per causar una gran primera impressió.
          </p>
        </div>
        <div class="card">
                        <img class="card-img" src="../assets/plastificats.svg" alt="plastificats">
          <h4>Plastificats</h4>
          <p>
            Per molts tipus de formats, amb diferents acabats a la teva mida.
          </p>
        </div>

      </div>
    </section>

<section id="contacta" class="contact">
<div class="contact-content">

  <div class="contact-text">
    <h3>Contacta'ns</h3>

    <p>
Contacta amb nosaltres per demanar-nos un pressupost o resoldre qualsevol dubte. Estarem encantats d’ajudar-te.
    </p>
  </div>

<form class="contact-form" @submit.prevent="sendEmail">

  <div class="form-grid">

    <div class="form-left">
      <input
        v-model="name"
        type="text"
        placeholder="Nom"
        required
      >

      <input
        v-model="email"
        type="email"
        placeholder="Correu electrònic"
        required
      >
    </div>

    <div class="form-right">
      <textarea
        v-model="message"
        rows="8"
        placeholder="Explica'ns què necessites..."
        required
      ></textarea>
    </div>

  </div>

  <button type="submit">
    Enviar missatge
  </button>

</form>

</div>
</section>

    <section id="galeria" class="galeria">
        <h3>Coneix-nos</h3>
        <p>
        Impressionat és una copisteria de barri situada al cor de Gràcia, especialitzada en impressions, enquadernacions i solucions gràfiques amb acabats professionals. Apostem per un tracte proper, ràpid i de qualitat perquè cada client se senti com a casa.
        </p>
        <div>
<div class="carousel-wrapper">
  <button class="carousel-btn left" @click="prevSlide">
    ←
  </button>

  <div class="carousel-track">

    <img
      :src="images[(currentSlide - 1 + images.length) % images.length]"
      class="side-image left-image"
      alt=""
    >

<transition :name="direction === 'next' ? 'slide-next' : 'slide-prev'">      <img
        :key="images[currentSlide]"
        :src="images[currentSlide]"
        alt="Galeria Impressionat"
        class="carousel-image"
      >
    </transition>

    <img
      :src="images[(currentSlide + 1) % images.length]"
      class="side-image right-image"
      alt=""
    >

  </div>

  <button class="carousel-btn right" @click="nextSlide">
    →
  </button>
</div>

<div class="dots">
  <span
    v-for="(image, index) in images"
    :key="index"
    :class="['dot', { active: currentSlide === index }]"
    @click="currentSlide = index"
  ></span>
</div>
</div>
    </section>


    
    <section id="reviews" class="reviews">
      <h3>Què diu la gent</h3>

      <div class="review-grid">
        <div class="review-card1">
          <p>
            “Excel·lent servei, tracte molt amable i molt bons preus.”
          </p>

          <span>★★★★★</span>
        </div>

        <div class="review-card2">
          <p>
            “La qualitat de la impressió és boníssima.”
          </p>

          <span>★★★★★</span>
        </div>

        <div class="review-card3">
          <p>
            “Professionals, seriosos i molt amables.”
          </p>

          <span>★★★★★</span>
        </div>
      </div>
    </section>

    <section id="info" class="info">
      <div class="info-box">
        <h3>Troba'ns</h3>

        <p>
          📍 Carrer del Penedès, 10, Gràcia, Barcelona <br>
          🚆 Metro L3-L5 Diagonal, L3 Fontana, L4 Joanic i Verdaguer <br>
          📞 +34 699 69 95 51 <br> 
          📧 impressionat20@gmail.com <br> <br>
          🕒 Horaris: <br>
          · Dilluns 11:00–14:30 i 16:30–20:00<br>
          · Dimarts i Dimecres 10:30–14:30 i 17:00–20:00 <br>
          · Dijous 10:30–14:00 i 17:00–20:00 <br>
          · Divendres 10:30–14:30 i 17:00–19:30 <br>
          · Dissabtes i Diumenges tancat
        </p>

      </div>
        <div class="map">
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d11971.049997007447!2d2.158261196872279!3d41.40096389784573!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x12a4a3e3d1bb8b49%3A0x297c4316eee086a6!2sImpressionat%20Copisteria!5e0!3m2!1ses!2ses!4v1778265730472!5m2!1ses!2ses" 
            width="100%" 
            height="350"
            style="border:0;" 
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade">
            </iframe>
        </div>
    </section>

    <footer>
      <div class="footer-text"><p>
        © 2026 Impressionat Copisteria · Barcelona
      </p></div>
      <div class="footer-links">
        <a class="footer-link" href="">Avís Legal</a>
        <a class="footer-link" href="">Politica de Cookies</a>
        <a class="footer-link" href="">Politica de Privacitat</a>
      </div>
    </footer>
  </div>
</template>

<script>
import foto1 from "../assets/impressionat-1.jpg"
import foto2 from "../assets/impressionat-2.jpg"
import foto3 from "../assets/impressionat-3.jpg"
import foto4 from "../assets/impressionat-4.jpg"

export default {
  data() {
    return {
      whatsappLink: "https://wa.me/34699699551",

      isScrolled: false,

      menuOpen: false,

      currentSlide: 0,

      direction: "next",

      images: [
        foto1,
        foto2,
        foto3,
        foto4
      ],

      name: "",
      email: "",
      message: "",
    }
  },

  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 0
    },

    toggleMenu() {
      this.menuOpen = !this.menuOpen
    },

    nextSlide() {
      this.direction = "next"

      this.currentSlide =
        (this.currentSlide + 1) % this.images.length
    },

    prevSlide() {
      this.direction = "prev"

      this.currentSlide =
        (this.currentSlide - 1 + this.images.length) %
        this.images.length
    },

    sendEmail() {
      const subject = `Nou missatge de ${this.name}`

      const body =
`Nom: ${this.name}

Email: ${this.email}

Missatge:
${this.message}`

      window.location.href =
        `mailto:borjagonz@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`
    }
  },

  mounted() {
    window.addEventListener("scroll", this.handleScroll)
  },

  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll)
  }
}
</script>


<style scoped>



.landing {
  background-color: black;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 30px 10%;
  position: fixed;
  width: 100%;
  transition: all 0.5s ease;
  z-index: 1000;  
}

.navbar.scrolled {
  padding: 20px 10%;
  backdrop-filter: blur(20px);
  background-color: rgba(0,0,0,0.2);
}

.logo {
  height: 80px;
  transition: all 0.3s ease;
}

.navbar.scrolled .logo {
  height: 70px;
}

.navlinks {
  display: flex;
  gap: 10px;
  background-color: white;
  border-radius: 100px;
  padding: 0px 20px;
  align-items: center;
}

.navlinks p {
  color: rgb(223, 223, 223);
}

.hamburger {
  display: none;
  background: white;
  border: none;
  border-radius: 60px;
  width: 55px;
  height: 55px;
  bottom: 2px;
  font-size: 24px;
  cursor: pointer;
  z-index: 2000;
  transition: all 0.3s ease;
  align-content: center;
  text-decoration: none;
  color: black;
}

.hamburger:hover {
  scale: 1.05;
}

.hero {
  height: 100vh;
  background-image: url(../assets/hero-fons-2.png);
  background-size: cover;
  background-position: center;
}

.overlay {
  height: 100vh;
  color: white;
}

.hero-content {
  width: 100%;
  height: 100%;
  padding: 100px 10%;
  text-align: center;
  justify-content: center;
  justify-items: center;
  align-content: center;
}

.call-button {
  color: black;
  text-decoration: none;
  text-align: center;
  align-items: center;
  align-content: center;
  padding: 14px 12px;
  font-weight: 400;
  font-size: 18px;
  transition: all 0.3s ease;
}

.call-button:hover {
  color: #f11ac8;
}

.badge {
  background: #ffffff20;
  padding: 8px 18px;
  border-radius: 50px;
  backdrop-filter: blur(10px);
  display: flex;
  width: 235px;
  gap: 8px;
  font-weight: 400;
  font-size: 18px;
  align-items: center;
  text-decoration: none;
  color: white;
  transition: all 0.3s ease;
  border: 1px solid rgba(255,255,255, 0.2);
  margin: 0 auto;
  margin-bottom: 40px;
}

.badge:hover {
  scale: 110%;
  box-shadow: 0 0 30px rgba(255,255,255, 0.5);
}

.badge-span{
  color: #eef413;
  font-size: 21px;
  position: relative;
  bottom: 3px;
}

.hero-content h2 {
  font-family: 'Aloja', sans-serif;
  font-size: 120px;
  font-weight: 100;
  line-height: 1.1;
  margin-bottom: 50px;
}

.hero-content p {
  font-size: 24px;
  margin-bottom: 40px;
}

.hero-buttons {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  margin: 0 auto;
  justify-content: center;
  justify-items: center;
}

.primary-btn,
.secondary-btn {
  padding: 14px 28px;
  border-radius: 12px;
  text-decoration: none;
  font-weight: bold;
}

.primary-btn {
  background: white;
  color: black;
  align-content: center;
  border-radius: 100px;
  font-weight: 400;
  font-size: 18px;
  transition: all 0.3s ease;
}

.primary-btn:hover {
  scale: 110%;
  box-shadow: 0 0 30px rgba(255,255,255, 0.5);
}

.secondary-btn {
  border: 1px solid white;
  color: white;
  font-weight: 400;
  font-size: 18px;
  align-content: center;
  transition: all 0.3s ease;
  border-radius: 100px;
}

.secondary-btn:hover {
  scale: 110%;
  box-shadow: 0 0 30px rgba(255,255,255, 0.5);
}

.services {
  padding: 120px 0 0px 0;
  color: white;
  
}

.services h3,
.reviews h3,
.info h3 {
  font-size: 52px;
  margin-bottom: 80px;
  text-align: center;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  justify-content: center;
  padding: 0px 40px;
}

.card {
  padding: 40px 50px 60px 50px;
  border-radius: 30px;
  text-align: center;
  background-color: #191919;
  transition: all 0.3s ease;
  min-width: 280px;
  max-width: 24%;
  height: 290px;
  align-items: center;
  align-content: center;
  border: 1px solid rgba(255,255,255, 0.2);
box-shadow: inset 0px 0px 50px rgba(0,0,0,0.3)
}

.card:hover {
  background-color: #f20eca;
  border: 1px solid rgba(255,255,255, 0.2);
}

.card-img {
  width: 95px;
  margin-bottom: 10px;
}

.card h4 {
  margin-bottom: 15px;
  font-size: 24px;
  color: white;
  font-weight: 400;
}

.card p{
  font-size: 16px;
  opacity: 0.8;
  color: white;
}

.galeria {
  color: white;
  padding: 120px 10% 0px 10%;
}

.galeria h3 {
  font-size: 52px;
  margin-bottom: 30px;
  text-align: center;
}

.galeria p{
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
  font-size: 20px;
  line-height: 1.5;
  opacity: 0.8;
}

.carousel-wrapper {
  position: relative;
  margin: 30px auto 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
}

.carousel-track {
  position: relative;
  width: 100%;
  height: 650px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.carousel-image {
  width: 500px;
  height: 560px;
  object-fit: cover;
  border-radius: 30px;
  z-index: 5;
  position: relative;
  box-shadow: 0 20px 60px rgba(0,0,0,0.5);
  border: 1px solid rgba(255,255,255, 0.5);
}

.side-image {
  position: absolute;
  width: 350px;
  height: 500px;
  object-fit: cover;
  border-radius: 30px;
  opacity: 0.3;
  transition: all 0.9s ease;
  filter: blur(1px);
  border: 1px solid rgba(255,255,255, 0.5);
}

.left-image {
  left: 120px;
}

.right-image {
  right: 120px;
}

.carousel-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  border: none;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: #f20eca;
  color: white;
  font-size: 24px;
  cursor: pointer;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
  z-index: 20;
}

.carousel-btn:hover {
  background: #f20eca;
  scale: 110%;
}

.carousel-btn.left {
  left: 10%;
}

.carousel-btn.right {
  right: 10%;
}

.slide-next-enter-active,
.slide-next-leave-active,
.slide-prev-enter-active,
.slide-prev-leave-active {
  transition: all 0.5s ease;
  position: absolute;
}

.slide-next-enter-from {
  opacity: 0;
  transform: translateX(120px) scale(0.95);
}

.slide-next-leave-to {
  opacity: 0;
  transform: translateX(-120px) scale(0.95);
}

.slide-prev-enter-from {
  opacity: 0;
  transform: translateX(-120px) scale(0.95);
}

.slide-prev-leave-to {
  opacity: 0;
  transform: translateX(120px) scale(0.95);
}

.dots {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-top: 30px;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #555;
  cursor: pointer;
  transition: all 0.3s ease;
}

.dot.active {
  background: white;
  transform: scale(1.25);
}

.reviews {
  color: white;
  padding: 120px 10% 0px 10%;
  margin: 0 auto;
}

.reviews p {
  font-size: 20px;
}

.reviews span {
  font-size: 28px;
}

.review-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  justify-content: center;
}

.review-card1 {
  background: #2ab9fd;
  color: black;
  padding: 50px;
  border-radius: 20px;
  text-align: center;
  min-width: 260px;
  max-width: 380px;
  height: 230px;
  transition: all 0.3s ease;
  align-content: center;
  border: 1px solid rgba(255,255,255, 0.2);
box-shadow: inset 0px 0px 50px rgba(0,0,0,0.3)
}

.review-card1:hover {
  background: white;
}

.review-card2 {
  background: #f11ac8;
  color: black;
  padding: 50px;
  border-radius: 20px;
  text-align: center;
  min-width: 250px;
  max-width: 380px;
  height: 230px;
  transition: all 0.3s ease;
  align-content: center;
  border: 1px solid rgba(255,255,255, 0.2);
box-shadow: inset 0px 0px 50px rgba(0,0,0,0.3)
}

.review-card2:hover {
  background: white;
}

.review-card3 {
  background: #eef413;
  color: black;
  padding: 50px;
  border-radius: 20px;
  text-align: center;
  min-width: 300px;
  max-width: 380px;
  height: 230px;
  transition: all 0.3s ease;
  align-content: center;
  border: 1px solid rgba(255,255,255, 0.2);
box-shadow: inset 0px 0px 50px rgba(0,0,0,0.3)
}

.review-card3:hover {
  background: white;
}

.contact {
  margin: 160px 0px 0px 0px;
  padding: 120px 10%;
  color: white;
  background: #191919;
  background-image: url(../assets/hero-fons-4.png);
  background-position: center;
  background-size: cover;
}

.contact-content {
  border-radius: 30px;
  max-width: 1200px;
  margin: 0 auto;
}

.contact-form {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.contact-text {
  text-align: center;
  max-width: 800px;
  margin: 0 auto 60px auto;
}

.contact-text h3 {
  font-size: 52px;
  margin-bottom: 30px;
}

.contact-text p {
  font-size: 20px;
  line-height: 1.5;
  opacity: 0.8;
}

.form-grid {
  display: flex;
  flex-direction: column;
  grid-template-columns: 1fr;
  gap: 30px;
  margin-bottom: 30px;
}

.form-left {
  display: flex;
  gap: 30px;
  width: 100%;
}

.form-right,
.form-right textarea {
  width: 100%;
}

.form-right textarea {
  min-height: 100%;
  font-family: 'Arimo';
}

.contact-form input,
.contact-form textarea {
  background: transparent;
  border: 1px solid rgba(255,255,255, 0.2);
box-shadow: inset 0px 0px 50px rgba(0,0,0,0.3);
  border-radius: 18px;
  padding: 18px 22px;
  color: white;
  font-size: 1rem;
  outline: none;
  transition: all 0.3s ease;
  resize: none;
  width: 100%;
}

.contact-form input:focus,
.contact-form textarea:focus {
  border-color: #f20eca;
  box-shadow: 0 0 20px rgba(242, 14, 202, 0.2);
}

.contact-form input::placeholder,
.contact-form textarea::placeholder {
  color: rgba(255,255,255,0.5);
}

.contact-form button {
  background: white;
  color: black;
  border: none;
  padding: 18px;
  border-radius: 100px;
  font-weight: 400;
  cursor: pointer;
  transition: all 0.3s ease;
  width: 200px;
  margin: 0 auto;
  align-content: center;
  font-size: 18px;
  transition: all 0.3s ease;
}

.contact-form button:hover {
  scale: 110%;
  box-shadow: 0 0 30px rgba(255,255,255, 0.5);}

.info {
  margin: 120px 10% 100px 10%;
  display: flex;
  justify-content: space-between;
  background: #191919;
  border-radius: 30px;
  align-items: center;
  border: 1px solid rgba(255,255,255, 0.2);
}

.info-box {
  padding: 60px 0px 60px 60px;
  text-align: left;
  color: white;
  width: 50%;
}

.info-box h3 {
  margin-bottom: 30px;
  text-align: left;
}

.info-box p {
  margin-top: 0px;
  font-size: 18px;
}

.map {
  width: 50%;
  padding: 60px;
}

footer {
  background: #191919;
  color: white;
  text-align: center;
  padding: 30px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 40px 10% 40px 10%;
}

.footer-links {
  display: flex;
  gap: 20px;
}

.footer-link {
  color: white;
  text-decoration: none;  
  transition: all 0.3s ease;
}

.footer-link:hover {
  color:#f20eca;
}

@media (max-width: 1100px) {
  .info {
  margin: 150px 10%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  border-radius: 30px;
  align-items: center;
}

.info-box {
  padding: 60px 60px 0px 60px;
  text-align: center;
  color: white;
  width: 100%;
}

.info-box h3 {
  text-align: center;
}

.map {
  width: 100%;
}

.footer {
  flex-wrap: wrap;
  gap: 30px;
}

.footer-text {
  width: 100%;
  margin: 0 auto;
}

.footer-links {
  width: 100%;
justify-content: center;
margin-top: 20px;
flex-wrap: wrap;
}
}

@media (max-width: 900px) {

  .hamburger {
    display: block;
  }

  .navlinks {
    position: absolute;
    top: 100%;
    right: 10%;
    flex-direction: column;
    align-items: center;
    gap: 0;
    background: white;
    border-radius: 24px;
    padding: 20px;
    width: 220px;

    opacity: 0;
    visibility: hidden;
    transform: translateY(-10px);

    transition: all 0.3s ease;
  }

  .navlinks.open {
    opacity: 1;
    visibility: visible;
    transform: translateY(0);
  }

  .navlinks p {
    display: none;
  }

  .call-button {
    width: 100%;
    padding: 16px 0;
  }
}

@media (max-width: 769px) {

  .navlinks {
    right: 5%;
  }

  .services h3{
    font-size: 44px;
  }

  .contact h3 {
    font-size: 44px;
  }

  .galeria h3 {
    font-size: 44px;
  }

  .reviews h3 {
    font-size: 44px;
  }

  .info h3 {
    font-size: 44px;
  }

  .logo {
    height: 65px;
  }

  .navbar.scrolled .logo {
    height: 65px;
  }

  .navbar.scrolled {
    padding: 30px 5%;

  }

  .hero-content h2 {
    font-size: 80px;
  }

  .navbar {
    padding: 30px 5%;
  }

  .hero-content {
    padding: 100px 5%;
  }

  .services,
  .reviews   {
    padding: 120px 40px;
  }

  .cards {
    padding: 0;
    width: 100%;
  }

  .galeria {
    padding: 120px 40px 0px 40px;
  }

  .carousel-track {
    height: 380px;
  }

  .carousel-image {
    width: 100%;
    max-width: 320px;
    height: 380px;
  }

  .side-image {
    display: none;
  }

  .carousel-btn.left {
    left: 10px;
  }

  .carousel-btn.right {
    right: 10px;
  }

  .carousel-btn {
    width: 45px;
    height: 45px;
  }

  .contact {
    padding: 120px 40px;
    margin: 0px;
}

.contact-content {
  flex-direction: column;
  padding: 50px 0px;
}
.form-left {
  display: flex;
  flex-wrap: wrap;
}

.form-left input {
  width: 100%;
}

.contact-text,
.contact-form {
  width: 100%;
}

.contact-text p {
  text-align: center;
}

.info{
  margin: 0px 40px 40px 40px;
}

.info-box {
  padding: 40px 40px 0px 40px;
}

.map {
  padding: 40px
}
}

@media (max-width: 550px){

  .navbar {
    padding: 30px;
  }
  .navlinks {
    right: 30px;
  }

.hero-buttons{
  flex-wrap: wrap;
  justify-content: center;
}

  .card {
    width: 100%;
    padding: 40px;
  }

  .services {
    padding: 100px 40px;
  }

  .cards {
    width: 100%;
  }
  .card{
    max-width: 100%;
  }

  .reviews {
    padding: 100px 40px;
  }
  .review-card1,
  .review-card2,
  .review-card3 {
    max-width: 100%;
    width: 100%;
    padding: 30px;
  }
  .reviews p {
    font-size: 20px;
  }
  .reviews span {
    font-size: 20px;
  }
  .info-box{
    padding: 30px 30px 0px 30px;
  }
  .map {
        padding: 30px;

  }

  .services h3{
    font-size: 36px;
  }

  .contact h3 {
    font-size: 36px;
  }

  .galeria h3 {
    font-size: 36px;
  }

  .reviews h3 {
    font-size: 36px;
  }

  .info h3 {
    font-size: 36px;
  }
}

@media (max-width: 451px){

  .navlinks {
    right: 25px;
  }

  .hero h2 {
    font-size: 56px;
    margin-bottom: 30px;
  }

  .hero p {
    font-size: 16px;
    margin-bottom: 30px;
  }
  .hero-content {
    padding: 80px 25px 60px 25px;
  }
  .badge {
    margin-bottom: 30px;
  }

  .logo{
    height: 60px;
  }
  .navbar.scrolled .logo {
    height: 60px;
  }
  
  .navbar {
  padding: 25px;
}
.navbar.scrolled{
  padding: 25px;
}

.services{
    padding: 80px 25px;
}
.contact {
    padding: 80px 25px;
}
.galeria {
    padding: 80px 25px;
}
.reviews {
    padding: 0px 25px 80px 25px;
}
.info {
      margin: 0px 25px 80px 25px;
}
}


</style>