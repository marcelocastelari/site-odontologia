<template>
    <div class="">
        <div class="back">
            <div class="flex justify-between ">
                <div></div>
                <div class="flex md:text-xl md:mt-16 border-b-2 border-yellow-500 ">
                    <h2
                        class="hidden md:block text-yellow-900 md:p-2 md:mr-6 hover:bg-yellow-500 hover:text-white md:mb-2 cursor-pointer text-center">
                        Home</h2>
                    <h2
                        class="hidden md:block md::ml-6 text-yellow-900 md:p-2 hover:bg-yellow-500 hover:text-white md:mb-2 cursor-pointer text-center">
                        Quem somos</h2>
                    <h2
                        class="hidden md:block md:ml-6 text-yellow-900 md:p-2 hover:bg-yellow-500 hover:text-white md:mb-2 cursor-pointer text-center ">
                        Tratamentos</h2>
                    <h2
                        class="hidden md:block md:ml-6 md:mr-32 text-yellow-900 md:p-2 hover:bg-yellow-500 hover:text-white md:mb-2 cursor-pointer text-center">
                        Contato</h2>
                </div>
            </div>
            <div>
                <div class="hidden md:block md:text-6xl md:h-32 md:ml-96 md:mt-20 text-neutral-600">
                    <h1 class="md:w-96 h1"></h1>
                    <TypeWriter />
                </div>
            </div>

            <div class="md:hidden md:flex md:justify-center ">
                <img class="md:hidden w-10 mt-6 ml-2" src="../assets/menu-aberto.png" @click="menuOpen" alt="">
                <div id="menu-area" class="block md:hidden">
                    <div class="mr-6 grid justify-items-end">
                    <img class="w-3 mt-6 justify-items-end" src="../assets/x.png" @click="menuOpen" alt="">
                </div>
                <div class="mt-12 space-y-4 text-and ml-8 text-lg  text-yellow-800">
                <p class="underline decoration-yellow-500 underline-offset-[10px]">Home</p>
                <p class="underline decoration-yellow-500 underline-offset-[10px]">Quem somos</p>
                <p class="underline decoration-yellow-500 underline-offset-[10px]">Tratamentos</p>
                <p class="underline decoration-yellow-500 underline-offset-[10px]">Contatos</p>
                </div>
            </div>
            </div>

        </div>
        <div class="md:hidden p-1 bg-mobile">
            <h1 class="text-xl font-semibold text-center mt-12 ml-10 mr-10 mb-6 text-white ">TRANSFORMANDO SORRISOS PARA
                UMA VIDA MAIS FELIZ</h1>
            <h4 class="ml-1 text-white text-center">Temos o tratamento que você precisa! Clareamento, implantes
                dentários, próteses, ortodontia, estética e clinica geral.<br />

            </h4>
            <div class="flex justify-center md:justify-end md:mr-64">
                <button
                    class="w-52 h-9 mt-10 bg-yellow-500 md:w-64 md:h-12 text-white font-bold md:text-xl md:bg-yellow-900 rounded-lg md:mt-32 justify-end hover:opacity-70 ">Agende
                    sua consulta</button>
            </div>
        </div>
    </div>




</template>

<script>
import TypeWriter from './TypeWriter.vue';

export default {
    components: {
        TypeWriter,
    },

    methods: {
        menuOpen() {
            let menuArea = document.getElementById("menu-area")

            if (menuArea.style.width == '200px') {
                menuArea.style.width = '0'
            }
            else {
                menuArea.style.width = '200px'
            }
        },




    },

}


</script>

<style scoped>
img {
    z-index: 41;
    position: absolute;
}

#menu-area {
    width: 0px;
    height: 100%;
    background-color:#eee;
    transition: all ease .5s;
    font-family: arial;
    top: 0;
    position: absolute;
    overflow: hidden;
    z-index: 99;
}

.back {
    background: linear-gradient(rgba(46, 33, 0, 0.2), rgba(39, 29, 2, 0.2)), url('../assets/sorriso3.jpg');
    background-position: top;
    background-size: cover;
    height: 700px;
}

.h1 {
    font-family: 'Poppins';
}

@media only screen and (max-width: 600px) {
    .back {
        background: #fff;
        background-position: top;
        background-size: cover;
        size: 100%;
        height: 110px;
    }

    .bg-mobile {
        background: linear-gradient(rgba(51, 51, 49, 0.9), rgba(81, 81, 80, 0.9)),
            url('../assets/sorriso2.jpg');
        background-position: top;
        background-size: cover;
        height: 350px;

    }

}
</style>