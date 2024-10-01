<template>
  <div>
    <h1>childrent component: {{ props.infoComponentProps }}</h1>
    <h3>{{ props.userNameProps }}, {{ props.ageProps }}</h3>
    <h2>san pham: {{ props.productProps }}</h2>
    <h1>{{ props.countProps }}</h1>
  </div>
</template>

<script  setup>
const props = defineProps(["userNameProps", "ageProps","userInfoProps","infoComponentProps","productProps", "countProps", "idProps"])
console.log(props);


</script>

<style>

</style>