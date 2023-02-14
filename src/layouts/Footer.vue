<template>
  <footer>
    <a href="http://rohit.nl" target="_blank">
        Created with <span class="text-gradient">❤</span> by Rohit.
    </a>
  </footer>
</template>

<script>
export default {
    name: "Footer"
}
</script>

<style lang="scss" scoped>
    footer {
        background-color: #27332F;
        text-align: center;
        padding: 6px;
        a:link, a:visited {
            color: #fff;
            text-decoration: none;
            .text-gradient {      
                background-image: var(--accent-gradient);
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
                background-size: 400%;
                background-position: 0%;
            }
        }
    }
</style>