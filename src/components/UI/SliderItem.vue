<template>
    <div class="seventhContnentBox">
        <img :src="require('@/assets/imgs/'+itemData.img)" alt="worker">
        <div class="seventhName">Аскар Байтасов</div>
        <div class="seventhDol">Видеограф, 6 лет опыта</div>
    </div>
    
</template>
<script>
export default {
    props:{
        itemData:{
            type: Object,
            default: ()=>{}
        }
    }
}
</script>
<style>
    
</style>