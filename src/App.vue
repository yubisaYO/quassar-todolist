<template>
  <router-view />
</template>

<script>
import { defineComponent } from "vue";
import "./css/app.scss";

export default defineComponent({
  name: "App",
});
</script>

<style>
.text-strikethrough {
  text-decoration: line-through ;
}
</style>
