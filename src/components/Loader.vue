<template>
    
    <div id="loader" class="loader-container">
        <span class="loader-14"></span>
    </div>

</template>

<script>
export default {
    name: 'Header',
    data(){
        return {
            
        }
    }
}
</script>

<style lang="scss" scoped>

    .loader-14 {
        width : 15em;
        height: 15em;
        display: block;
        position: absolute;
        top: 40%;
        left: 45%;
        z-index: 100000;
    }
    .loader-14::after , .loader-14::before {
    content: '';
        width : 15em;
        height: 15em;
        border-radius: 50%;
        border: 15px solid rgba(0, 149, 135, 100);
        position: absolute;
        left:0;
        top: 0;
        animation: animloader14 0.6s linear infinite;
    }

    .loader-14::after {
        animation-delay: 0.3s;
    }

    @keyframes animloader14 {
        0% { transform: scale(0); opacity: 1;}
        100% { transform: scale(1); opacity: 0;}
    }

</style>