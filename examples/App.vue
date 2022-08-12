<template>
  <div id="app">
      <ButtonView></ButtonView>
    <DialogView></DialogView>
    <StepView></StepView>
  </div>
</template>


<script>
import ButtonView from "./components/buttons/buttonView.vue";
import DialogView from "./components/dialogs/dialogView.vue";
import StepView from "./components/steps/stepView.vue";
export default {
  name: 'App',
  components: {
    ButtonView, DialogView, StepView
  }
}
</script>


<style>
</style>
