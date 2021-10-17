<template>
  <section class="intro section section-pad bg-cover" id="intro">
    <div class="copy container">
      <a class="logo appear">
        <img src="@/assets/images/logo.svg" />
      </a>
      <div class="marquee mix-difference">
        <span>{{ marqueeAnimation }}</span>
      </div>
      <div class="mix-difference appear">
        <p>
          Held in the beautiful San Bernadino, CA, the first annual FIFTY Music
          Festival is an unmissable event. Over the course of 3 days, we invite
          the rising stars in music from 50 different countries all over the
          world for a unique, cultural extravaganza.
        </p>
      </div>
    </div>
    <a href="#day-1" class="js-scroll scroll-to scroll-to-intro"></a>
  </section>

  <section class="section section-pad day day-1" id="day-1">
    <div class="container center">
      <h3 class="date">
        Friday Nov 10
      </h3>
      <ul class="lineup">
        <li>
          <h2>
            Natti Natasha
          </h2>
          <p>
            Argentina
          </p>
        </li>

        <li>
          <h2>
            Post Malone
          </h2>
          <p>
            United States
          </p>
        </li>
        <li>
          <h2>
            Shirley Setia
          </h2>
          <p>
            New Zealand / India
          </p>
        </li>
        <li>
          <h2>
            Axwell /\ Ingrosso
          </h2>
          <p>
            Sweden
          </p>
        </li>
        <li>
          <p>
            …and more TBA
          </p>
        </li>
      </ul>
    </div>
    <span class="shape circle"></span>
    <span class="shape circle"></span>
    <span class="shape circle"></span>
    <span class="shape circle"></span>
    <span class="shape circle"></span>
    <span class="shape circle"></span>
    <span class="shape circle"></span>
    <span class="shape circle"></span>

    <a href="#day-2" class="js-scroll scroll-to"></a>
  </section>

  <section class="section section-pad day day-2" id="day-2">
    <div class="container center">
      <h3 class="date">
        Saturday Nov 11
      </h3>
      <ul class="lineup">
        <li>
          <h2>
            Kyary Pamyu Pamyu
          </h2>
          <p>
            Japan
          </p>
        </li>
        <li>
          <h2>
            Stella Mwangi
          </h2>
          <p>
            Kenya / Norway
          </p>
        </li>
        <li>
          <h2>
            Wizkid
          </h2>
          <p>
            Nigeria
          </p>
        </li>
        <li>
          <h2>
            Stormzy
          </h2>
          <p>
            UK
          </p>
        </li>
        <li>
          <p>
            …and more TBA
          </p>
        </li>
      </ul>
    </div>
    <span class="shape squiggle"></span>
    <span class="shape squiggle"></span>
    <span class="shape squiggle"></span>
    <span class="shape squiggle"></span>
    <span class="shape squiggle"></span>
    <span class="shape squiggle"></span>
    <span class="shape squiggle"></span>
    <span class="shape squiggle"></span>
    <a href="#day-3" class="js-scroll scroll-to"></a>
  </section>

  <section class="section section-pad day day-3 bg-cover" id="day-3">
    <div class="container center">
      <h3 class="date">
        Sunday Nov 12
      </h3>
      <ul class="lineup">
        <li>
          <h2>
            Swet Shop Boys
          </h2>
          <p>
            UK / US
          </p>
        </li>
        <li>
          <h2>
            Christine and the Queens
          </h2>
          <p>
            France
          </p>
        </li>
        <li>
          <h2>
            Ryan McGeady
          </h2>
          <p>
            Scotland
          </p>
        </li>
        <li>
          <h2>
            Die Antwoord
          </h2>
          <p>
            South Africa
          </p>
        </li>
        <li>
          <p>
            …and more TBA
          </p>
        </li>
      </ul>
    </div>
    <a href="#register" class="js-scroll scroll-to"></a>
  </section>

  <section class="section" id="register">
    <div class="register section-pad">
      <div class="container">
        <div class="eyes"></div>
        <div class="form">
          <h2 class="lunch-medium">
            Register for festival updates
          </h2>
          <form action="" method="post" id="subForm" class="sign-up">
            <input
              placeholder="Enter your email"
              id="fieldEmail"
              name=""
              type="email"
              required
              class="email-input"
            />
            <input type="submit" value="Submit" class="submit" />
          </form>
        </div>
        <div class="hand"></div>
      </div>
    </div>
    <footer class="footer section-pad">
      <div class="container">
        <img src="@/assets/images/logo.svg" />
        <p>
          <a class="js-scroll button" href="#intro">
            ↑ Back to top
          </a>
        </p>
      </div>
    </footer>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import "@/assets/css/shapes.css";
import "@/assets/css/viewport.css";

const inView = require("in-view");

export default defineComponent({
  name: "FiftyFestival",

  computed: {
    marqueeAnimation(): string {
      const title = "FIFTY Music Festival — November 10–12, Desert Valley";
      return new Array(50).fill(title).join(" — ");
    },
  },
  methods: {
    circleAnimation(): void {
      const circles = document.querySelectorAll(".circle");

      return circles.forEach((circle, index) => {
        circle.animate(
          [
            { transform: "scale(1)" },
            { transform: "scale(1.2)" },
            { transform: "scale(1)" },
          ],
          {
            delay: 300 * index,
            duration: 3000,
            iterations: Infinity,
          }
        );
      });
    },
    random(min: number, max: number): number {
      return Math.floor(Math.random() * (max - min + 1)) + min;
    },
    squiggleAnimation(): void {
      const squiggles = document.querySelectorAll(".squiggle");

      squiggles.forEach((squiggle, index) => {
        const randomNumber = this.random(0, 45);

        return squiggle.animate(
          [
            { transform: "rotate(0deg)" },
            { transform: `rotate(${randomNumber}deg)` },
            { transform: "rotate(0deg)" },
          ],
          {
            delay: 300 * index,
            duration: 5000,
            iterations: Infinity,
          }
        );
      });
    },
    sectionInViewport(): void {
      inView(".section")
        .on("enter", (section: any) => {
          section.classList.add("in-viewport");
        })
        .on("exit", (section: any) => {
          section.classList.remove("in-viewport");
        });
      inView.threshold(0.2);
      const sections = document.querySelectorAll(".section");

      return sections.forEach((section) => {
        const artists = section.querySelectorAll<HTMLElement>(".lineup li");
        const shapes = section.querySelectorAll<HTMLElement>(".shape");

        artists.forEach((artist, index) => {
          const delay = index * 100;
          artist.style.transitionDelay = delay + "ms";
        });

        shapes.forEach((shape, index) => {
          const delay = (artists.length + index) * 100;
          shape.style.transitionDelay = delay + "ms";
        });
      });
    },
    smoothScroll(): void {
      const scrollLinks = document.querySelectorAll(".js-scroll");

      return scrollLinks.forEach((link) => {
        link.addEventListener("click", (event) => {
          event.preventDefault();

          const href = link.getAttribute("href")!;
          document.querySelector(href)!.scrollIntoView({
            behavior: "smooth",
          });
        });
      });
    },
  },
  mounted() {
    this.sectionInViewport();
    this.circleAnimation();
    this.squiggleAnimation();
    this.smoothScroll();
  },
});
</script>

<style scoped>
.section {
  min-height: 100vh;
  display: flex;
}

.section-pad {
  padding-left: 5vw;
  padding-right: 5vw;
}

.container {
  max-width: 810px;
  margin: auto;
}

.intro {
  background-image: url("../assets/images/intro.jpg");
  color: #ffffff;
}

.intro p {
  font-size: 36px;
  line-height: 1.2;
}

.logo {
  display: block;
  text-align: center;
  margin-bottom: 32px;
  margin-left: auto;
  margin-right: auto;
  max-width: 112px;
}

.logo img {
  width: 100%;
}

.bg-cover {
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  50% {
    transform: translate(0);
  }
  100% {
    opacity: 1;
  }
}

.appear {
  opacity: 0;
  animation-name: fadeIn;
  animation-duration: 3s;
  animation-delay: 2s;
  animation-fill-mode: forwards;
}

.marquee {
  position: absolute;
  top: 3vh;
  left: 0;
  width: 100%;
  font-size: 5vw;
  line-height: 1;
  overflow: hidden;
  mix-blend-mode: difference;
}

@keyframes moveLeft {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-2000vw);
  }
}

.marquee span {
  animation: moveLeft 200s infinite;
  white-space: nowrap;
  display: block;
  position: relative;
}

.mix-difference {
  mix-blend-mode: difference;
}

.day-1 {
  background-color: #fd76a7;
}

.day-2 {
  background-color: #1bb190;
}

.day-3 {
  background-image: url("../assets/images/day-3.jpg");
}

.day {
  text-align: center;
  position: relative;
  overflow: hidden;
}

.day .container {
  position: relative;
  z-index: 2;
}

.lineup h2 {
  font-size: 56px;
  line-height: 1;
  margin-bottom: 6px;
}

.lineup p {
  font-size: 21px;
  margin-bottom: 24px;
}

.date {
  font-size: 28px;
  color: #ffeecf;
  margin-bottom: 48px;
  line-height: 1;
}

.scroll-to {
  position: absolute;
  left: 50%;
  bottom: 3vh;
  width: 64px;
  height: 32px;
  background-image: url("../assets/images/down-arrow.svg");
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  transform: translateX(-50%);
}

.scroll-to-intro {
  background-image: url("../assets/images/down-arrow-light.svg");
}
</style>
