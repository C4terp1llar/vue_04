<template>
  <div class="card card-w70">
    <template
        v-if="infoBlocks.length"
    >
      <component
        v-for="infoBlock in infoBlocks"
        :key="infoBlock.id"
        :is="'resume-' + infoBlock.type"
        :value="infoBlock.value"
      >

      </component>
    </template>

    <h3 v-else>Добавьте блок, чтобы увидеть результат</h3>
  </div>
</template>

<script>
import resumeText from "@/components/resume-components/resume-text.vue";
import resumeTitle from "@/components/resume-components/resume-title.vue";
import resumeSubtitle from "@/components/resume-components/resume-subtitle.vue";
import resumeAvatar from "@/components/resume-components/resume-avatar.vue";

export default {
  components: {
    resumeText, resumeTitle, resumeSubtitle, resumeAvatar
  },
  props: {
    infoBlocks: Array
  }
}
</script>

<style lang="">

</style>