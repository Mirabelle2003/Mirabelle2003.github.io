<template>
    
    <div class="code-display">
      <pre><p class="code">Code</p>{{ code }}</pre>
      <div class="copy-button-container">
        <button @click="copyCode">Copier</button>
        <div v-if="showSuccess" class="success-message">
          Code copié !
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        code: '',
        showSuccess: false
      };
    },
    props: {
      initialCode: String // Propriété pour le code source à afficher
    },
    methods: {
      copyCode() {
        const textarea = document.createElement('textarea');
        textarea.value = this.code;
        document.body.appendChild(textarea);
        textarea.select();
        document.execCommand('copy');
        document.body.removeChild(textarea);
  
        this.showSuccess = true;
        setTimeout(() => {
          this.showSuccess = false;
        }, 2000);
      }
    },
    watch: {
      initialCode(newValue) {
        this.code = newValue;
      }
    },
    created() {
      this.code = this.initialCode;
    }
  };
  </script>
  
  <style>
.code-display {
    margin-top: 10px;
  background-color: #f4f4f4;
  padding: 5px;
  border: 1px solid #ddd;
  max-width: 70%; 
  /* margin: 0 auto; Centrer horizontalement */
}

.code{
    font-weight: bold;
    font-size: 15px;
}
  
  .copy-button-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  
  button {
    margin-top: 5px;
  }
  
  .success-message {
    background-color: rgba(93, 92, 92, 0.329);
    font-size: 12px;
    padding:3px;
    padding-right:120px;
    padding-left:120px;
    color: green;
    margin-left: 5px;
    display: inline;
  }
  </style>
  





<!-- 
   <template>
  <div class="code-display-container">
    <div class="code-display">
      <pre>{{ code }}</pre>
      <div class="copy-button-container">
        <button @click="copyCode">Copier</button>
        <div v-if="showSuccess" class="success-message">
          <p>Code copié !</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      code: '',
      showSuccess: false
    };
  },
  props: {
    initialCode: String // Propriété pour le code source à afficher
  },
  methods: {
    copyCode() {
      const textarea = document.createElement('textarea');
      textarea.value = this.code;
      document.body.appendChild(textarea);
      textarea.select();
      document.execCommand('copy');
      document.body.removeChild(textarea);

      this.showSuccess = true;
      setTimeout(() => {
        this.showSuccess = false;
      }, 2000);
    }
  },
  watch: {
    initialCode(newValue) {
      this.code = newValue;
    }
  },
  created() {
    this.code = this.initialCode;
  }
};
</script>

<style>
/* Stylisez votre composant de code ici */
.code-display-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.code-display {
  background-color: #f4f4f4;
  padding: 15px;
  border: 1px solid #ddd;
  width: fit-content; /* Utilisation de fit-content */
  max-width: 80%; /* Limite la largeur pour éviter une largeur excessive */
}

.copy-button-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 10px;
}

button {
  margin-top: 5px;
}

.success-message {
  font-size: 12px;
  color: green;
  margin-left: 5px;
  display: inline;
}
</style> -->
