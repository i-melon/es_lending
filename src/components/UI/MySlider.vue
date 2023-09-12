<template>
    <div class="wrapper">
        <div class="wrapperButtons">
            <button @click="prevSlide" class="sliderButton7"><svg xmlns="http://www.w3.org/2000/svg" width="25" height="24" viewBox="0 0 25 24" fill="none">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M13.1521 4.22804C12.7256 3.80159 12.0342 3.80159 11.6078 4.22804L4.60776 11.228C4.18131 11.6545 4.18131 12.3459 4.60776 12.7724L11.6078 19.7724C12.0342 20.1988 12.7256 20.1988 13.1521 19.7724C13.5785 19.3459 13.5785 18.6545 13.1521 18.228L8.01624 13.0922H19.3799C19.983 13.0922 20.4719 12.6033 20.4719 12.0002C20.4719 11.3971 19.983 10.9082 19.3799 10.9082H8.01624L13.1521 5.77236C13.5785 5.34591 13.5785 4.6545 13.1521 4.22804Z" fill="black"/>
              </svg>
            </button>
            <button @click="nextSlide" class="sliderButton7"><svg xmlns="http://www.w3.org/2000/svg" width="25" height="24" viewBox="0 0 25 24" fill="none">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M11.848 4.22804C12.2745 3.80159 12.9659 3.80159 13.3924 4.22804L20.3924 11.228C20.8188 11.6545 20.8188 12.3459 20.3924 12.7724L13.3924 19.7724C12.9659 20.1988 12.2745 20.1988 11.848 19.7724C11.4216 19.3459 11.4216 18.6545 11.848 18.228L16.9839 13.0922H5.6202C5.0171 13.0922 4.5282 12.6033 4.5282 12.0002C4.5282 11.3971 5.0171 10.9082 5.6202 10.9082H16.9839L11.848 5.77236C11.4216 5.34591 11.4216 4.6545 11.848 4.22804Z" fill="black"/>
              </svg>
            </button>
        </div>
        
        <div class="slider" :style="{'margin-left': '-'+(100*this.currentIndex)+'%'}">
            <SliderItem
                v-for="item in sliderData"
                :key="item.id"
                :itemData="item"
                
            />
            
        </div>
        
        
    </div>
</template>
<script>
import SliderItem from './SliderItem.vue'
export default {
    components:{
        SliderItem
    },
    data(){
        return{
            currentIndex: 0
        }
    },
    props:{
        sliderData: {
            type: Array,
            default: () => []
        }
    },
    methods:{
        prevSlide(){
            if (this.currentIndex > 0){
                this.currentIndex--
            }
            else{
                this.currentIndex = 1
            }
        },
        nextSlide(){
            this.currentIndex++
            if (this.currentIndex>1){
                this.currentIndex=0
            }
        }
    },
    
    
}
</script>
<style>
    .wrapper{
        overflow: hidden;
    }
    .slider{
        display:flex;
        transition: all ease .5s
    }
    .sliderButton7{
        position: absolute;
    }
    .wrapperButtons{
        align-self:stretch;
        display: flex;
        flex-direction: row;
        gap: 30px;
        justify-content: flex-end;
    }
</style>