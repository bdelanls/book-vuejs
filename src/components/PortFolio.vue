<template>
  <ul>
    <li v-for="projet in projets" :key="projet.id" class="portfolio">
      <section>
        <div class="img-presentation">
          <picture>
            <p class="warning">En cours</p>
            <source :srcset="projet.image + '-1.webp'" type="image/webp" />
            <source :srcset="projet.image + '-1.jpg'" type="image/jpeg" />
            <img :src="projet.image + '-1.jpg'" alt="HappyVisio" />
          </picture>
        </div>

        <h3>{{ projet.titre }}</h3>
        <p class="description">{{ projet.description }}</p>
        <p class="infos"></p>
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
          image: "/img/happyvisio",
          titre: "HappyVisio",
          description: "Site institutionnel",
          url: "",
          prestations: ["WebDesign", "UI - UX"],
          stack: ["Figma", "Photoshop", "Illustrator"],
          carroussel: true,
          imgCarroussel: 4,
          message: "En cours",
        },
        {
          id: 99,
          image: "/img/latelierroseetnoir",
          titre: "L'atelier noir et rose",
          description: "Site de Julie Mourier, Directrice Artistique.",
          url: "https://latelierroseetnoir.fr",
          prestations: ["Intégration", "Développement"],
          stack: ["WordPress", "GeneratePress"],
          carroussel: true,
          imgCarroussel: 4,
          message: "latelierroseetnoir.fr",
        },
      ],
    };
  },

  methods: {},

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

.portfolio section img {
  width: 100%;
}
.portfolio a:hover {
  text-decoration: underline;
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
  p {
    font-size: 0.8em;
  }
  #carousel {
    padding: 20px;
    width: 90%;
    box-shadow: -5px 5px 8px rgba(0, 0, 0, 0.5);
  }
}

/* Large devices (desktops, 992px and up) */
@media only screen and (min-width: 992px) {
  main {
    margin-top: -10px;
  }
  h2 {
    font-weight: 300;
    font-size: 12em;
    position: absolute;
    z-index: -10;
    top: 148px;
    left: -269px;
    transform: rotateZ(-90deg);
  }
  h1 {
    font-weight: 400;
    font-size: 1.4em;
    margin: 0;
    padding: 5px 5px 5px 0;
    color: #303030;
    text-align: right;
    background-color: #202020;
  }
  header {
    position: absolute;
    left: -129px;
    width: 135px;
    top: 432px;
    display: block;
    text-align: right;
  }
  header img {
    margin: 10px 0 0 0;
  }
}
</style>
