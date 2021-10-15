<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Investimentos</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <div class="container">
        <div class="bg">
          <ion-col>
            <ion-item class="item">
              <ion-label>Tipo do Investimento</ion-label>
              <ion-select
                placeholder="Selecione"
                ok-text="Ok"
                cancel-text="Cancelar"
                v-model="inputTipoInvestimento"
              >
                <ion-select-option value="Ações">Ações</ion-select-option>
                <ion-select-option value="Poupança">Poupança</ion-select-option>
                <ion-select-option value="Previdência Privada"
                  >Previdência Privada</ion-select-option
                >
                <ion-select-option value="Renda Fixa"
                  >Renda Fixa</ion-select-option
                >
                <ion-select-option value="Tesouro Direto"
                  >Tesouro Direto</ion-select-option
                >
              </ion-select>
            </ion-item>
            <ion-item class="item">
              <ion-label position="floating">Valor do Investimento</ion-label>
              <ion-input
                type="number"
                min="0.01"
                step="0.01"
                v-model="inputValorInvestimento"
              ></ion-input>
            </ion-item>
            <ion-item class="item">
              <ion-label position="floating">Fonte do Investimento</ion-label>
              <ion-input
                type="text"
                v-model="inputFonteInvestimento"
              ></ion-input>
            </ion-item>
            <ion-item class="item">
              <ion-label>Data do Investimento</ion-label>
              <ion-input
                type="date"
                display-format="DD MMMM YYYY"
                v-model="inputDataInvestimento"
              ></ion-input>
            </ion-item>
            <ion-button @click="salvarInformacoes">Salvar</ion-button>
            <h6>
              Tipo: {{ tipo }} | Valor: {{ valor }} | Fonte: {{ fonte }} | Data:
              {{ data }}
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
  name: 'Tab3',
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
  IonSelect,
  IonSelectOption,
  IonInput,
  IonButton,
} from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "Tab3",
  components: {
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonPage,
    IonCol,
    IonItem,
    IonLabel,
    IonSelect,
    IonSelectOption,
    IonInput,
    IonButton,
  },
  methods: {
    salvarInformacoes() {
      const tipo = this.inputTipoInvestimento;
      this.tipo = tipo;
      const valor = this.inputValorInvestimento;
      const valorFormatado = valor.replace(".", ",");
      this.valor = valorFormatado;
      const fonte = this.inputFonteInvestimento;
      this.fonte = fonte;
      const data = this.inputDataInvestimento;
      const ano = data.slice(0, 4);
      const mes = data.slice(5, 7);
      const dia = data.slice(8, 10);
      const dataFormatada = `${dia}/${mes}/${ano}`;
      this.data = dataFormatada;
    },
  },
  data() {
    return {
      inputTipoInvestimento: "",
      tipo: "",
      inputValorInvestimento: "",
      valor: "",
      inputFonteInvestimento: "",
      fonte: "",
      inputDataInvestimento: "",
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
