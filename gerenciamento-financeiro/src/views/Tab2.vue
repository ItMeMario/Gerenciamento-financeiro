<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Despesas</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Despesas</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <div class="container">
        <div class="bg">
          <ion-col>
            <ion-item class="item">
              <ion-label position="floating">Valor da Despesa</ion-label>
              <ion-input
                type="number"
                min="0.01"
                step="0.01"
                v-model="inputValorDespesa"
              ></ion-input>
            </ion-item>
            <ion-item class="item">
              <ion-label position="floating">Nome da Despesa</ion-label>
              <ion-input
                type="text"
                v-model="inputNomeDespesa"
              ></ion-input>
            </ion-item>
            <ion-item class="item">
              <ion-label>Data da Despesa</ion-label>
              <ion-input
                type="date"
                display-format="DD MMMM YYYY"
                v-model="inputDataDespesa"
              ></ion-input>
            </ion-item>
            <ion-button @click="salvarInformacoes">Salvar</ion-button>
            <h6>
               Valor: {{ valor }} | Nome: {{ Nome }} | Data: {{ data }}
            </h6>
          </ion-col>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">

import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
//import ExploreContainer from '@/components/ExploreContainer.vue';

export default  {
  name: 'Tab2',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage }
=======
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonCol,
  IonItem,
  IonLabel,
  IonInput,
  IonButton,
} from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "Tab2",
  components: {
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonPage,
    IonCol,
    IonItem,
    IonLabel,
    IonInput,
    IonButton,
  },
  methods: {
    salvarInformacoes() {
      const valor = this.inputValorDespesa;
      const valorFormatado = valor.replace(".", ",");
      this.valor = valorFormatado;
      const Nome = this.inputNomeDespesa;
      this.Nome = Nome;
      const data = this.inputDataDespesa;
      const ano = data.slice(0, 4);
      const mes = data.slice(5, 7);
      const dia = data.slice(8, 10);
      const dataFormatada = `${dia}/${mes}/${ano}`;
      this.data = dataFormatada;
    },
  },
  data() {
    return {
      inputTipoDespesa: "",
      tipo: "",
      inputValorDespesa: "",
      valor: "",
      inputNomeDespesa: "",
      Nome: "",
      inputDataDespesa: "",
      data: "",
    };
  },
});
</script>

<style scoped>
.container {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #dfe6e9;
}
.bg {
  padding: 20px;
  border-radius: 5px;
  background-color: #b2bec3;
}
.item {
  margin: 0px 0px 40px 0px;
}
</style>