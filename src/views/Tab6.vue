<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Info Sistema</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <div class="container">
        <div class="bg">
          <h1>GERENCIAMENTO FINANCEIRO APP </h1>
          <h6> © 2021 FACULDADE BOM JESUS IELUSC </h6>
          <h1> gerfinanciamento@gmail.com </h1>
          <h6> Version : 1.0.87 </h6>
          <h6> Desenvolvedores do Projeto: </h6>
          <h6> * MATHEUS TEIXEIRA MELO </h6>
          <h6> * BIANCA CAPISTRANO LAZZARIS</h6>
          <h6> * LUCAS LEONI </h6>
          <h6> * ALEXANDRE SALVADOR  </h6>
            <h2> ESTE APP UTILIZA A TECNOLOGIA IONIC : </h2>
            <h1> </h1>
            <h2> https://ionicframework.com/docs </h2>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
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
