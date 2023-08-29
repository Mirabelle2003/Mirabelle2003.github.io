<template>
    <div>
        <p>La directive v-bind permet de lier dynamiquement les attributs HTML à des valeurs de données.</p>
        <a v-bind:href="linkURL">Cliquez ici</a>
        <code-display :initial-code="sanmpleCodeBind"></code-display>
    </div>

    <div>
        <p>
          La directive v-model permet de créer une liaison bidirectionnelle entre un élément de formulaire et une variable.
        </p>
        <input v-model="message" placeholder="Saisissez un message" />
      <p>Message saisi : {{ message }}</p>
      <code-display :initial-code="sanmpleCodeModel"></code-display>

      </div>
      <div>
        <p>Les directives v-if et v-else sont utilisées pour conditionner l'affichage d'éléments en fonction d'une expression booléenne</p>
        <p v-if="isUserLoggedIn">Bienvenue, {{ username }}</p>
        <p v-else>Veuillez vous connecter pour voir le contenu.</p>
        <code-display :initial-code="sanmpleCodeIf"></code-display>

      </div>
      <div>
        <p>
          La directive v-for permet d'itérer sur un tableau ou un objet et de générer du contenu répété.
        </p>
        <ul>
        <li v-for="(post, index) in posts" :key="index">{{ post.title }}</li>
      </ul>
      <code-display :initial-code="sanmpleCodeFor"></code-display>

      </div>
      <div>
        <p>La directive v-on permet d'écouter les événements et d'exécuter des méthodes en réponse.</p>
        <button v-on:click="Hello">Cliquez ici</button>
        <code-display :initial-code="sanmpleCodeOn"></code-display>

      </div>
      <div>
        <p>La directive v-show permet de conditionner l'affichage d'éléments en fonction d'une expression booléenne, mais les éléments restent présents dans le DOM.</p>
        <p v-show="showMessage">Ce message est visible.</p>
        <code-display :initial-code="sanmpleCodeShow"></code-display>

      </div>
</template>

<script setup>
    import {computed, ref} from 'vue';
    const linkURL=  ref("https://google.com");

    import CodeDisplay from './CodedisplayComponent.vue';

    const message = ref("");
  const isUserLoggedIn = true;
  const username = "Utilisateur";
  const posts = ref([
    { id: 1, title: 'La vie est belle' },
    { id: 2, title: 'Le monde est beau' },
    { id: 3, title: 'Le ciel est bleu' }
  ])
  function Hello(){
    alert("Bonjour !");
  }
  
  const showMessage = true;
  const sanmpleCodeBind = `
<template>
    <p>La directive v-bind permet de lier dynamiquement les attributs HTML à des valeurs de données.</p>
    <a v-bind:href="linkURL">Cliquez ici</a>
</template>


    `;

    const sanmpleCodeModel = `
    <template>
        <p>
          La directive v-model permet de créer une liaison bidirectionnelle entre un élément de formulaire et une variable.
        </p>
        <input v-model="message" placeholder="Saisissez un message" />
      <p>Message saisi : {{ message }}</p>
    </template>
    `;
    const sanmpleCodeIf = `
    <template>
        <p>Les directives v-if et v-else sont utilisées pour conditionner l'affichage d'éléments en fonction d'une expression booléenne</p>
        <p v-if="isUserLoggedIn">Bienvenue, {{ username }}</p>
        <p v-else>Veuillez vous connecter pour voir le contenu.</p>
    </template>
    `;
    const sanmpleCodeFor = `
    <template>
        <p>La directive v-for permet d'itérer sur un tableau ou un objet et de générer du contenu répété.</p>
        <ul>
            <li v-for="(post, index) in posts" :key="index">{{ post.title }}</li>
        </ul>
    </template>
    `;
    const sanmpleCodeOn = `
    <template>
        <p>La directive v-on permet d'écouter les événements et d'exécuter des méthodes en réponse.</p>
        <button v-on:click="Hello">Cliquez ici</button>
    </template>
    `;
    const sanmpleCodeShow = `
    <template>
        <p>La directive v-show permet de conditionner l'affichage d'éléments en fonction d'une expression booléenne, mais les éléments restent présents dans le DOM.</p>
        <p v-show="showMessage">Ce message est visible.</p>
    </template>
    `;
</script>

