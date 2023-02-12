<template>
  <a class="button" :href="url">
    {{ title }}
  </a>
</template>

<script>
export default {
    name: "Button",
    data() {
        return {
            
        }
    },
    props: {
        title: Text,
        url: Text
    }
}
</script>

<style lang="scss" scoped>
    a.button:link, a:visited {
        color: #fff;
        background: linear-gradient(94.45deg, #B47AEA 18.27%, #FFC4EB 101.24%);
        padding: 12px 20px;
        text-decoration: none;
        font-size: 20px;
        font-weight: 500;
    }
</style>