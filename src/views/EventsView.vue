<template>
  <div class="events">
    <!-- <p>Découvrez nos prochaines représentations...</p>
    <EventCardList :events="events"/> -->
    <p>
      Nous sommes en train de mettre le site à jour pour nos représentations de
      P23.
    </p>
    <p>
      En attendant, venez découvrir notre actualité sur notre page
      <a href="https://www.facebook.com/leo.profitroles.9">Facebook</a> !
    </p>
  </div>
</template>

<script>
import EventCardList from "@/components/EventCardList.vue";

export default {
  components: {
    EventCardList,
  },
  data: function () {
    return {
      events: [
        {
          name: "Le Faux Misanthrope",
          type: "pièce",
          dateTime: new Date("2022-09-05 15:45:00"),
          ticketingURL: "https://assos.utc.fr/woolly/ventes/",
          ticketingOpen: true,
          posterFilename: "faux-mysanthrope.png",
          description: "Franchement, vous avez raté un truc...",
        },
        {
          name: "Profit'Soirée",
          type: "cabaret",
          dateTime: new Date("2022-11-13 20:00:00"),
          ticketingURL:
            "https://www.helloasso.com/associations/pole-artistique-et-evenementiel-de-l-utc/evenements/profit-soiree-un-spectacle-d-exception-1?fbclid=IwAR3D1__UtFk-uQSmYazmxCLfspz3vqBzV0D9h1DNa4d0PscpwBkaaa-THeY",
          ticketingOpen: true,
          posterFilename: "profit-soiree.jpg",
          description:
            "De l’impro, du thé, des gâteaux : qu’est-ce qui pourrait mal se passer ce soir ? \
          Fous rires devant nos sketches, suspense insoutenable devant nos improvisations : \
          vraiment, ça sera sûrement “un spectacle d’exception”... Non ?",
        },
        {
          name: "Longueur d'Avance",
          type: "longform",
          dateTime: new Date("2022-11-26 14:45:00"),
          ticketingURL:
            "https://www.helloasso.com/associations/pole-artistique-et-evenementiel-de-l-utc/evenements/longueur-d-avance",
          ticketingOpen: true,
          description:
            "Deux spectacles pour le prix d’un ! Plongez dans une épopée de 45 minutes totalement improvisée. \
          Qui sait où le destin va mener nos joueurs ? En première partie, assistez à une comédie dramatique en format court, \
          mais intense.",
        },
        {
          name: "Le Bal des Voleurs",
          type: "pièce",
          dateTime: new Date("2022-12-03 14:45:00"),
          ticketingURL:
            "https://www.helloasso.com/associations/pole-artistique-et-evenementiel-de-l-utc/evenements/le-bal-des-voleurs-une-piece-de-jean-anouilh",
          ticketingOpen: true,
          description:
            "Vichy, terrain de jeu de bien nombreuses manigances : \
          les pickpockets ne manquent pas à l’appel, et un malicieux trio parvient à s’immiscer chez une famille fortunée ! \
          Un véritable bal s’anime alors, dont chacun vient malmener la chorégraphie…",
        },
        {
          name: "Longueur d'Avance",
          type: "longform",
          dateTime: new Date("2022-12-04 20:00:00"),
          ticketingURL:
            "https://www.helloasso.com/associations/pole-artistique-et-evenementiel-de-l-utc/evenements/longueur-d-avance",
          ticketingOpen: true,
          description:
            "Deux spectacles pour le prix d’un ! Plongez dans une épopée de 45 minutes totalement improvisée. \
          Qui sait où le destin va mener nos joueurs ? En première partie, assistez à une comédie dramatique en format court, \
          mais intense.",
        },
        {
          name: "Le Bal des Voleurs",
          type: "pièce",
          dateTime: new Date("2022-12-10 14:45:00"),
          ticketingURL:
            "https://www.helloasso.com/associations/pole-artistique-et-evenementiel-de-l-utc/evenements/le-bal-des-voleurs-une-piece-de-jean-anouilh",
          ticketingOpen: true,
          description:
            "Vichy, terrain de jeu de bien nombreuses manigances : \
          les pickpockets ne manquent pas à l’appel, et un malicieux trio parvient à s’immiscer chez une famille fortunée ! \
          Un véritable bal s’anime alors, dont chacun vient malmener la chorégraphie…",
        },
        {
          name: "Profit'Soirée",
          type: "cabaret",
          dateTime: new Date("2022-12-14 19:45:00"),
          ticketingURL:
            "https://www.helloasso.com/associations/pole-artistique-et-evenementiel-de-l-utc/evenements/profit-soiree-2",
          ticketingOpen: true,
          description:
            "Ho, ho, ho, joyeux Noël ! On est un peu en avance, \
          mais on vous offre non pas seulement de l’improvisation, mais aussi des sketches* ! \
          Vous avez manqué la première ? Au rattrapage : tout est I-NÉ-DIT ! </br>\
          <em style='text-align: right;font-size: .5em;display:block;'>*aucun comédien n’a été maltraité pendant la préparation de ce spectacle</em>",
        },
      ],
    };
  },
};
</script>

<style scoped>
.events {
  margin: auto;
  text-align: center;
  padding: 1rem;
}

p {
  margin: 1.5em 0 0.5em;
}

a {
  opacity: 0.8;
}

a:hover {
  opacity: 1;
}
</style>