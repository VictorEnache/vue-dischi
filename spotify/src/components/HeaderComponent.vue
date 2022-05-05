<template>
    <header id="main_header">
        <div class="logo">
            <img src="../assets/img/logo-spotify.png" alt="">
        </div>
    </header>
</template>

<script>
export default {
    name: 'HeaderComponent'
}
</script>

<style lang="scss">
 #main_header{
     padding: 10px 20px;
     background-color: #2E3A46;

     .logo{
         width: 50px;
         height: 50px;

         img{
             width: 100%;
             object-fit: cover;
         }
     }
 }
</style>