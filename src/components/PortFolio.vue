<template>
  <ul>
    <li
      v-for="projet in projets"
      :key="projet.id"
      class="portfolio"
      v-show="projet.actif"
    >
      <section>
        <div class="img-presentation">
          <picture>
            <source
              :srcset="'/img/' + projet.image + '-1.webp'"
              type="image/webp"
            />
            <source
              :srcset="'/img/' + projet.image + '-1.jpg'"
              type="image/jpeg"
            />
            <img :src="'/img/' + projet.image + '-1.jpg'" :alt="projet.titre" />
          </picture>
        </div>
        <div class="msg">
          <p v-if="projet.url !== ''">
            <a :href="projet.url" :title="projet.url" target="_blank">
              {{ projet.message }}
            </a>
          </p>
          <p v-else>{{ projet.message }}</p>
          <div class="picto-plus">
            <a v-on:click="box(projet.nbImg, projet.image)">
              <img src="/img/magnifying-glass-plus-solid.svg" />
            </a>
          </div>
        </div>

        <h3>{{ projet.titre }}</h3>
        <p class="description">{{ projet.description }}</p>
        <fieldset>
          <legend>Prestation</legend>
          <ul>
            <li
              v-for="(prestation, index) in projet.prestations"
              :key="index"
              class="etiquette"
            >
              {{ prestation }}
            </li>
          </ul>
        </fieldset>
        <fieldset>
          <legend>Stack</legend>
          <ul>
            <li
              v-for="(stack, index) in projet.stacks"
              :key="index"
              class="etiquette"
            >
              {{ stack }}
            </li>
          </ul>
        </fieldset>
      </section>
    </li>
  </ul>
</template>

<script>
export default {
  name: "PortFolio",

  data() {
    return {
      projets: [
        {
          id: 100,
          image: "happyvisio",
          titre: "HappyVisio",
          description: "Site institutionnel.",
          url: "",
          prestations: ["WebDesign Responsive", "UI - UX", "Front-end"],
          stacks: ["Figma", "Photoshop", "Illustrator"],
          actif: true,
          nbImg: 4,
          message: "En cours",
        },
        {
          id: 95,
          image: "latelierroseetnoir",
          titre: "L'atelier rose & noir",
          description: "Site de Julie Mourier, Directrice Artistique.",
          url: "https://latelierroseetnoir.fr",
          prestations: ["Intégration", "Développement", "SEO"],
          stacks: ["WordPress", "GeneratePress"],
          actif: true,
          nbImg: 4,
          message: "latelierroseetnoir.fr",
        },
        {
          id: 90,
          image: "book",
          titre: "Book",
          description: "Présentation de mes travaux.",
          url: "https://book.bdelanls.fr",
          prestations: ["Intégration", "Développement"],
          stacks: ["HTML5", "CSS3", "Vue.js", "Javascript"],
          actif: false,
          nbImg: 2,
          message: "book.bdelanls.fr",
        },
        {
          id: 85,
          image: "dwwm",
          titre: "DWWM",
          description:
            "Projet pour la certification de développeur web et web mobile.",
          url: "https://dwwm.bdelanls.fr",
          prestations: [
            "Cahier des charges",
            "Charte graphique",
            "Wireframe",
            "WebDesign Responsive",
            "Mobile First",
            "Front-end",
            "Back-end",
            "Intégration",
            "SEO",
          ],
          stacks: [
            "Adobe XD",
            "HTML5",
            "CSS3",
            "Sass",
            "Javascript",
            "Symfony",
            "MySQL",
            "PHP",
            "Twig",
            "Ajax",
          ],
          actif: true,
          nbImg: 3,
          message: "dwwm.bdelanls.fr",
        },
        {
          id: 80,
          image: "lidiatobola",
          titre: "Lidia Tobola",
          description: "Site de la guitariste Lidia Tobola.",
          url: "https://www.lidiatobola.fr",
          prestations: [
            "WebDesign Responsive",
            "Intégration",
            "Développement",
            "SEO",
          ],
          stacks: ["WordPress", "GeneratePress"],
          actif: true,
          nbImg: 3,
          message: "www.lidiatobola.fr",
        },
        {
          id: 75,
          image: "melodix",
          titre: "Mélodix",
          description: "École de musique pour adulte.",
          url: "https://melodix.fr",
          prestations: ["Maintenance", "Intégration", "SEO"],
          stacks: ["WordPress", "GeneratePress", "Elementor"],
          actif: true,
          nbImg: 1,
          message: "melodix.fr",
        },
        {
          id: 70,
          image: "antonin",
          titre: "Antonin Seigneuric",
          description: "Galeries de sculptures sur bois.",
          url: "https://www.antonin-seigneuric.com",
          prestations: ["Maintenance", "Intégration", "SEO"],
          stacks: ["WordPress"],
          actif: true,
          nbImg: 5,
          message: "www.antonin-seigneuric.com",
        },
        {
          id: 65,
          image: "etheldavid",
          titre: "Ethel David",
          description:
            "Présentation et portfolio des projets de la graphiste indépendante Ethel David.",
          url: "https://www.etheldavid.fr",
          prestations: ["Développement", "Intégration", "SEO"],
          stacks: ["WordPress"],
          actif: true,
          nbImg: 3,
          message: "www.etheldavid.fr",
        },
        {
          id: 60,
          image: "lacoste-pressroom",
          titre: "Lacoste Press Room",
          description:
            "Présentation des actualités et des nouvelles collections de Lacoste à l'attention des journalistes.",
          url: "",
          prestations: ["Développement", "Intégration", "Mise à jour", "SEO"],
          stacks: ["HTML", "CSS", "JQuery", "K2 Server"],
          actif: true,
          nbImg: 3,
          message: "Le site n'existe plus",
        },
        {
          id: 55,
          image: "ev",
          titre: "Entrepreneur Venture",
          description: "Société de gestion.",
          url: "",
          prestations: ["Intégration", "Responsive", "SEO"],
          stacks: ["WordPress"],
          actif: true,
          nbImg: 4,
          message: "Cette version du site n'existe plus",
        },
        {
          id: 50,
          image: "ev-drupal",
          titre: "Entrepreneur Venture",
          description: "Première version du site Entrepreneur Venture.",
          url: "",
          prestations: ["Développement", "Intégration", "SEO"],
          stacks: ["HTML", "CSS", "Drupal 7"],
          actif: true,
          nbImg: 5,
          message: "Cette version du site n'existe plus",
        },
        {
          id: 45,
          image: "smart-treso",
          titre: "Smart Treso",
          description: "Société de financement de trésorerie.",
          url: "",
          prestations: ["Intégration", "SEO"],
          stacks: ["WordPress"],
          actif: true,
          nbImg: 2,
          message: "Le site n'existe plus",
        },
        {
          id: 40,
          image: "ccc",
          titre: "Ça c'est Carrefour !",
          description:
            "Galeries de photos et de vidéos pour des évènements Carrefour.",
          url: "",
          prestations: ["Intégration"],
          stacks: ["HTML", "CSS", "K2 Server"],
          actif: true,
          nbImg: 3,
          message: "Intranet, site inaccessible",
        },
        {
          id: 35,
          image: "crf-assurances",
          titre: "Carrefour Assurances",
          description: "Aide dans les démarches de déclarations d'assurances.",
          url: "",
          prestations: ["Intégration", "SEO"],
          stacks: ["HTML", "CSS", "Javascript"],
          actif: true,
          nbImg: 2,
          message: "Intranet, site inaccessible",
        },
        {
          id: 30,
          image: "tempeos",
          titre: "Tempeos",
          description: "Comité d’Entreprise Externalisé, site institutionnel.",
          url: "",
          prestations: ["Développement", "Intégration", "SEO"],
          stacks: ["HTML", "CSS", "Javascript", "PHP"],
          actif: true,
          nbImg: 3,
          message: "Cette version du site n'existe plus",
        },
        {
          id: 25,
          image: "tempeos-ce",
          titre: "Tempeos - le CE des PME",
          description:
            "Comité d’Entreprise Externalisé avec commande en ligne.",
          url: "",
          prestations: ["Intégration"],
          stacks: ["HTML", "CSS", "e-majine"],
          actif: true,
          nbImg: 1,
          message: "Cette version du site n'existe plus",
        },
      ],
    };
  },

  methods: {
    listeImages(nbImg, nomImg) {
      this.listeImg = "";
      for (let i = 1; i <= nbImg; i++) {
        this.listeImg += nomImg + "-" + i + ", ";
      }
      alert(this.listeImg);
    },

    box(nbImg, nomImg) {
      this.cheminCarousel = document.getElementById("carousel");
      this.cheminContentCarousel = document.getElementById("content-carousel");

      // récupère la liste des visuels
      this.arr_visuels = [];
      for (let i = 1; i <= nbImg; i++) {
        this.arr_visuels.push(nomImg + "-" + i);
      }
      // alert(this.arr_visuels);

      this.htmlCarousel = '<ul class="visuels">\n';
      for (let i = 0; i < this.arr_visuels.length; i++) {
        this.htmlCarousel += `<li>
         <picture>
         <source srcset="/img/${this.arr_visuels[i]}.webp type="image/webp">
         <source srcset="/img/${this.arr_visuels[i]}.jpg" type="image/jpeg"> 
         <img src="/img/${this.arr_visuels[i]}.jpg">
         </picture>
         </li>\n`;
      }
      this.htmlCarousel += `</ul>\n`;

      this.htmlCarousel += `<nav id="nav"><ul>`;
      for (let i = 0; i < this.arr_visuels.length; i++) {
        if (this.arr_visuels.length > 1) {
          this.htmlCarousel += `<li class="bt-${i}"
            v-on:click="affVisuel(${i})"> ${i + 1} </li>`;
        }
      }
      // bouton de fermeture de la fenêtre
      this.htmlCarousel += `<li class="close">X Fermer</li>`;

      this.htmlCarousel += `</ul>\n`;

      this.cheminCarousel.innerHTML = this.htmlCarousel;
      // ajouter une classe sur le premier li
      this.affVisuel(0);

      this.cheminCarousel.classList.add("actif");
      document.getElementById("content").classList.add("hide");

      // affiche le carousel au dessus
      this.cheminContentCarousel.setAttribute("style", "z-index: 1000;");

      // event
      this.btClose = document.querySelector(".close");
      this.btClose.addEventListener("click", () => {
        this.fermer();
      });

      for (let i = 0; i < this.arr_visuels.length; i++) {
        this.bt = document.querySelector(".bt-" + i);
        this.bt.addEventListener("click", () => {
          this.affVisuel(i);
        });
      }
    },

    affVisuel(num) {
      this.cheminCarouselLi = document
        .getElementById("carousel")
        .getElementsByTagName("li");
      this.cheminNavLi = document
        .getElementById("nav")
        .getElementsByTagName("li");

      for (let i = 0; i < this.cheminCarouselLi.length; i++) {
        this.cheminCarouselLi[i].classList.remove("actif");
      }
      this.cheminCarouselLi[num].classList.add("actif");
      this.cheminNavLi[num].classList.add("actif");
    },

    fermer() {
      document.getElementById("carousel").classList.remove("actif");
      document.getElementById("content").classList.remove("hide");

      // affiche le carousel en dessous
      this.cheminContentCarousel.setAttribute("style", "");
    },
  },

  computed: {},
};
</script>

<style>
main > ul {
  display: flex;
  flex-wrap: wrap;
  padding: 0;
}
main > ul > li {
  width: 100%;
  list-style-type: none;
  margin: 0.35em;
  padding: 0.5em;
  background: #202020;
}

p.intro {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 0.9em;
  color: #ccc;
  padding-left: 6px;
}

/* section */
.portfolio section {
  display: flex;
  flex-direction: column;
}
.portfolio picture {
  display: flex;
}
.portfolio section img {
  width: 100%;
}
.portfolio a:hover {
  text-decoration: underline;
}
.portfolio .msg {
  background-color: #ff3456;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.portfolio .msg p {
  margin: 5px;
  font-size: 0.9rem;
}
.portfolio .msg p a {
  color: #fff;
  text-decoration: none;
}
.portfolio .msg p a:hover {
  text-decoration: underline;
}
.portfolio .picto-plus a {
  background-color: #fff;
  width: 25px;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}
.portfolio .picto-plus a:hover {
  background-color: #ffcc00;
  cursor: pointer;
}
.portfolio .msg img {
  height: 20px;
  width: 20px;
}
.portfolio h3 {
  margin: 18px 0 10px 0;
  font-size: 1.2rem;
  font-weight: 300;
}
.portfolio .description {
  font-size: 0.9rem;
  line-height: 140%;
  font-weight: 300;
  color: #ccc;
}
.portfolio fieldset {
  border-top: 1px solid #ccc;
  margin: 20px 0 10px 0;
}
.portfolio fieldset legend {
  margin: 0 auto 10px auto;
  padding: 0 10px;
  font-size: 0.8rem;
  font-weight: 300;
}
.portfolio fieldset ul {
  display: flex;
  flex-wrap: wrap;
}
.portfolio .etiquette {
  background-color: #666;
  font-size: 0.9rem;
  font-weight: 300;
  padding: 3px 15px;
  margin: 5px 5px 5px 0;
  border-radius: 10px;
}

#carousel {
  position: absolute;
  max-width: 800px;
  padding: 10px;
  background-color: #fff;
  margin: auto;
  display: none;
  border-radius: 5px;
}
#carousel.actif {
  display: block;
  align-self: center;
}
#carousel ul {
  display: flex;
  list-style-type: none;
  padding: 0;
  margin: 0;
}
#carousel ul.visuels > li {
  display: none;
}
#carousel ul.visuels > li.actif {
  display: block;
}
#carousel ul.visuels > li img {
  width: 100%;
}
#carousel nav {
  margin-top: 5px;
  border-top: 1px solid #ccc;
}
#carousel nav ul {
  display: flex;
  justify-content: center;
  margin: 10px 0 0 0;
}
#carousel nav li {
  background-color: #ccc;
  border-radius: 20px;
  padding: 5px 8px;
  margin: 0 4px;
  font-size: 0.8em;
}
#carousel nav li:hover {
  background-color: #ddd;
  cursor: pointer;
}
#carousel nav li.actif {
  background: #999;
}

/* Medium devices (tablets, 768px and up) */
@media only screen and (min-width: 768px) {
  main > ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
  main > ul > li {
    width: 280px;
    flex-grow: 1;
  }
  #carousel {
    padding: 20px;
    width: 90%;
    box-shadow: -5px 5px 8px rgba(0, 0, 0, 0.5);
  }
}
</style>
