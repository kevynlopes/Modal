<template>
  <div class="flex flex-col items-center justify-center">
    <div class="p-8">
      <button
        @click="modal = !modal"
        class="bg-green-600 text-white rounded-lg p-4 font-bold"
      >
        Abrir modal
      </button>
    </div>
    <transition name="fade">
      <div v-if="modal" class="bg-white w-4/12 h-72 rounded-sm">
        <div class="flex justify-between p-6">
          <h2 class="font-semibold text-2xl">Titulo Modal</h2>
          <button @click="modal = false" class="font-bold p-3">X</button>
        </div>
        <hr />
        <div>
          <p class="p-4">
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dicta fuga
            neque non voluptas officiis, doloremque corporis ratione maiores ut
            a. Voluptatibus consequuntur inventore ullam quidem eos nihil
            exercitationem reprehenderit perspiciatis.
          </p>
        </div>
        <hr />
        <div class="flex justify-end gap-4 p-4">
          <button @click="modal = false" class="bg-red-500 p-2">Fechar</button>
          <button @click="alerta" class="bg-blue-400 p-2">
            Salvar Alterações
          </button>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      modal: false,
    };
  },
  methods: {
    alerta() {
      alert("Alterações salvas com sucesso!");
      this.modal = false;
    },
  },
};
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active em versões anteriores a 2.1.8 */ {
  opacity: 0;
}
body {
  background: gray;
}
</style>
