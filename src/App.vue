<template>
  <div class="container column">
    <!--    Блок с контролом-->
    <app-control
      @change="updateResult"
    >

    </app-control>

    <!--Блок с резюме    -->
    <app-result
      :infoBlocks="update"
    >

    </app-result>

  </div>
</template>

<script>
import AppControl from './components/AppControl.vue';
import AppResult from './components/AppResult.vue';

export default {
  data(){
    return{
      update: []
    }
  },
  methods: {
    updateResult(data){
      this.update.push(data);
    }
  },
  components: {
    'app-control': AppControl,
    'app-result': AppResult
  }
}
</script>

<style>
  .avatar {
    display: flex;
    justify-content: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>
