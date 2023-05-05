<template lang="">
    <div>
       <div class="top-head">
        <li  class="about-link ">
          <router-link  :to="{ name: 'about' }"> Back</router-link>
        </li>
       
       </div>
       <div class="fetch-content">
        <Reservation :completeData ="fecthData" >
            <template v-slot:appbtn>
             <h3>
                deatils box
             </h3>
             
            
            </template>
            <template v-slot:appbtn-2>
                <button>view more</button>
            </template>
        </Reservation>
        <Reservation :completeData ="fecthData" >
            <template v-slot:appbtn>
            <h3>Details-box</h3>
            </template>
            <template v-slot:appbtn-2>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nesciunt consequatur optio necessitatibus, accusantium ipsam corrupti quae quo repudiandae et eos sit exercitationem consectetur saepe velit quibusdam ab quidem veritatis omnis.</p>
            </template>
        </Reservation>
        <Reservation :completeData ="fecthData" >
            <template v-slot:appbtn>
             <h3>
                deatils box
             </h3>
             
            
            </template>
            <template v-slot:appbtn-2>
                <button>view more</button>
            </template>
        </Reservation>
       </div>
    </div>
</template>
<script>
import Reservation from '../components/Reservation.vue';
export default {
    name:"Fetch",
    components:{
        Reservation,
    },
    data() {
        return{
            fecthData:{
                title: 'Title',
                disc: 'discrption for the title',
                btns: 'submit'
            },
        }
    }
}
</script>
