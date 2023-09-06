<template>
    <div class="dialog" v-if="show" @click.stop="hideDialog">
        <form class="dialogContent" @click.stop>
            <div class="dialogTitle">Оставить заявку</div>
            <div class="dialogText">Мы перезвоним вам в самое ближайшее<br/> время, чтобы обсудить подробности<br/> вашего проекта.</div>
            <div class="dialogText">Отправьте свой номер в графе "тема"</div>
            <a href="https://mail.google.com/mail/?view=cm&fs=1&to=bazinga010100@gmail.com"><button class="dialogButton" type="button">Оставить заявку</button></a>
        </form>
        
    </div>
</template>
<script>
export default {
    props:{
        show: {
            type: Boolean,
            default: true
        }
    },
    data(){
        return{
            theNumber: ''
        }
    },
    methods:{
        hideDialog(){
            this.$emit('update:show', false)
        }

    }
}
</script>
<style>
.dialog{
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    background-color: rgba(0,0,0,0.5);
    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
}
.dialogContent{
    margin: auto;
    background: white;
    border-radius: 32px;
    padding: 65px 72px;
    display: flex;
    flex-direction: column;
    gap: 32px;
    align-items: center;
}
 .dialogTitle{
    color: #000;
font-size: 32px;
font-style: normal;
font-weight: 600;
line-height: 40px; /* 125% */
letter-spacing: -0.32px;
 }   
 .dialogText{
    color: #000;
text-align: center;
font-size: 16px;
font-style: normal;
font-weight: 500;
line-height: 26px; /* 162.5% */
 }
 .dialogInput{
    align-self: stretch;
    display: flex;
padding: var(--spacing-l, 16px) 24px;
align-items: center;
gap: var(--spacing-s, 8px);
border-radius: var(--rounding-m, 10px);
border: 1px solid rgba(0, 0, 0, 0.20);
 }
 .dialogButton{
    display: flex;
width: 324px;
padding: var(--spacing-l, 16px) 24px;
justify-content: space-between;
align-items: center;
border-radius: 48px;
background: #000;
color: #FAFAFA;
font-size: 18px;
font-style: normal;
font-weight: 600;
line-height: 32px; /* 177.778% */
justify-content: center;
align-items: center;
border: none;
 }
 .dialogButton:hover{
    background-color: rgb(79, 79, 79);}
</style>