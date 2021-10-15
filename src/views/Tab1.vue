<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Cadastro</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <div class="container">
        <div class="bg">
          <ion-col>
            <div class="avatar">
              <ion-fab-button href="/tabs/tab2">
                <ion-icon :icon="personCircle"></ion-icon>
              </ion-fab-button>
            </div>
            <ion-item class="item">
              <ion-label position="floating">Descrição</ion-label>
              <ion-input type="text" v-model="inputDescricao"></ion-input>
            </ion-item>
            <ion-item class="item">
              <ion-label position="floating">Tipo da receita</ion-label>
              <ion-input
                type="text"
                v-model="inputReceita"
                required="true"
              ></ion-input>
            </ion-item>
            <ion-item class="item">
              <ion-label position="floating">Valor</ion-label>
              <ion-input type="number" v-model="inputValor"></ion-input>
            </ion-item>
            <ion-item class="item">
              <ion-label position="floating">Data</ion-label>
              <ion-input type="date" v-model="inputData"></ion-input>
            </ion-item>

            <ion-button @click="salvarInformacoes">Salvar</ion-button>
            <h6>
              Tipo da Receita: {{ receita }} |  Valor:
              {{ valor }} | Descrição: {{descricao}} | Data: {{ data }} 
            </h6> 
          </ion-col>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { personCircle } from "ionicons/icons";
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
  IonFabButton,
  IonButton,
  IonIcon,
} from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "Tab1",
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
    IonFabButton,
    IonButton,
    IonIcon,
  },
  methods: {
    salvarInformacoes() {
      const receita = this.inputReceita;
      this.receita = receita;
      const valor = this.inputValor;
      this.valor = valor;
      const descricao = this.inputDescricao;
      this.descricao = descricao;
      const data = this.inputData;
      this.data = data
      
    },
  },
  data() {
    return {
      inputReceita: "",
      receita: "",
      inputValor: "",
      valor: "",
      inputDescricao:"",
      descricao:"",
      inputData: "",
      data: "",
    };
  },
  setup() {
    return {
      personCircle,
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
.avatar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0px 0px 20px 0px;
}
ion-icon {
  width: 100%;
  height: 100%;
}
</style>