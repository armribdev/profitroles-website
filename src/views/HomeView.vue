<template>
  <div class="events">
    <section class="association">
      <h1 class="association-title">L'association</h1>
      <div class="wrapper">
        <img class="association-image" src="@/assets/logo.svg" />
        <p class="association-description">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ipsa impedit quos asperiores earum voluptatem nulla sit laboriosam maxime velit consequuntur quam quis, blanditiis, enim optio dignissimos cumque architecto. Autem, asperiores!
        </p>
      </div>
    </section>
    <section class="workshop">
      <h2 class="workshop-title">Pièce</h2>
      <div class="wrapper">
        <img class="workshop-image" src="@/assets/logo.svg" />
        <p class="workshop-description">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. In aut facere quia dolores facilis fugiat perferendis obcaecati beatae incidunt quae quod ipsam, dolorum non quas rem sunt sapiente earum corrupti.
        </p>
      </div>
    </section>
    <section class="workshop">
      <h2 class="workshop-title">Atelier drame</h2>
      <div class="wrapper">
        <img class="workshop-image" src="@/assets/logo.svg" />
        <p class="workshop-description">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. In aut facere quia dolores facilis fugiat perferendis obcaecati beatae incidunt quae quod ipsam, dolorum non quas rem sunt sapiente earum corrupti.
        </p>
      </div>
    </section>
    <section class="workshop">
      <h2 class="workshop-title">Improvisation</h2>
      <div class="wrapper">
        <img class="workshop-image" src="@/assets/logo.svg" />
        <p class="workshop-description">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. In aut facere quia dolores facilis fugiat perferendis obcaecati beatae incidunt quae quod ipsam, dolorum non quas rem sunt sapiente earum corrupti.
        </p>
      </div>
    </section>
    <section class="workshop">
      <h2 class="workshop-title">Impro longue</h2>
      <div class="wrapper">
        <img class="workshop-image" src="@/assets/logo.svg" />
        <p class="workshop-description">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. In aut facere quia dolores facilis fugiat perferendis obcaecati beatae incidunt quae quod ipsam, dolorum non quas rem sunt sapiente earum corrupti.
        </p>
      </div>
    </section>
    <section class="workshop">
      <h2 class="workshop-title">Ouvertures au Théâtre à Moustaches</h2>
      <div class="wrapper">
        <img class="workshop-image" src="@/assets/logo.svg" />
        <p class="workshop-description">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. In aut facere quia dolores facilis fugiat perferendis obcaecati beatae incidunt quae quod ipsam, dolorum non quas rem sunt sapiente earum corrupti.
        </p>
      </div>
    </section>
    <section class="workshop">
      <h2 class="workshop-title">Divers</h2>
      <div class="wrapper">
        <p class="workshop-description">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. In aut facere quia dolores facilis fugiat perferendis obcaecati beatae incidunt quae quod ipsam, dolorum non quas rem sunt sapiente earum corrupti.
        </p>
      </div>
    </section>  
  </div>
</template>

<style scoped>
h1, h2 {
  text-align: center;
}


section .wrapper{
  display: flex;
  flex-direction: column;
  align-items: center;
}

section .wrapper img {
  max-height: 600px;
  max-width: 600px;
  margin: auto;
}

.workshop {
  margin-top: 3em;
}

.workshop-description {
  margin-top: 1.5em;
}



@media (min-width: 1024px) {
  .workshop-description {
    margin-top: 0;
  }

  .workshop:nth-child(2n) .workshop-description {
    margin-left: 1.5em;
  }

  .workshop:nth-child(2n) .wrapper {
    flex-direction: row;
  }

  .workshop:nth-child(2n+1) .workshop-description {
    margin-right: 1.5em;
  }

  .workshop:nth-child(2n+1) .wrapper {
    flex-direction: row-reverse;
  }

  .workshop:last-child .workshop-description {
    margin: 0;
  }

}
</style>