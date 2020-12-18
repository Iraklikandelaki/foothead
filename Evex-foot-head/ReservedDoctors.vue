<template>

<div class="reserved-doctors" >

<div class="cancel-modal">
   
       <transition name="fade">
<div class="overlay" v-if="showModal" @click="modalToggle"></div>
   </transition>
   
    
        <transition name="slideup">
<div class="actual-modal" v-if="showModal">
<div class="modal-title">
<div class="title-row">
  <span>ვიზიტის გაუქმება</span>
  <div class="x-icon" @click="modalToggle">
  
    <IconCancel></IconCancel>
  </div>
</div>
<div class="time-row">
  <img :src="require(`@/assets/img/clock.svg`)">
  <span>30 წუთიანი ვიზიტი</span>  
</div>

</div>

<div class="reserve-info">
  <div class="doctor-info">
    <div class="name-div">
      <img :src="require(`@/assets/img/Mask Group 12@2x.png`)">
      <div class="spans">
        <span>ვახო მშვიდობაძე</span>
        <span>ოფთალმოლოგი</span>
      </div>
      
    </div>
    <div class="credentials-div">
      <span>კლინიკა</span>
      <span>დიდუბის პოლიკლინიკა</span>
      <span>იღებს პაციენტებს</span>
      <span>18 წლიდან</span>
      <span>ატარებს კვლევებს</span>
      <span>რეფრაქტომეტრია, ტონომეტრია, ბიომიკროსკოპია, უცხო სხეულების ამოღება</span>
      <span>არ ატარებს კვლევებს</span>
      <span>საცრემლე არხების გახსნა</span>
    </div>

    <div class="credentials-div sm">
      <div class="accordion-title" @click="toggleReserve">
        <span>ექიმზე ინფორმაცია</span>
        <img :src="require(`@/assets/img/drop-arrow1.svg`)">
      </div>
       <div :class="{'active':showReserve}" class="reserve-content">
    <span>კლინიკა</span>
      <span>დიდუბის პოლიკლინიკა</span>
      <span>იღებს პაციენტებს</span>
      <span>18 წლიდან</span>
      <span>ატარებს კვლევებს</span>
      <span>რეფრაქტომეტრია, ტონომეტრია, ბიომიკროსკოპია, უცხო სხეულების ამოღება</span>
      <span>არ ატარებს კვლევებს</span>
      <span>საცრემლე არხების გახსნა</span>
     
    </div>
      
    </div>


  </div>


  
  <div class="patient-info">
      <div class="name-div">
        <div class="spans">
        <span>დემეტრე მ.</span>
        <span>პაციენტი</span>
      </div>
      </div>
      <div class="credentials-div">
        <span>ჯავშნის პერიოდი</span>
        <span>ოთხშაბათი, დეკემბერი 24, 13:30</span>
      </div>


     


  </div>
</div>

<div class="modal-footer">
<div class="foot-title">
  <span>ნამდვილად გსურთ ვიზიტის გაუქმება?</span>
</div>

<div class="buttons">
<div class="btn-1">
  <div class="x-icon">
  <IconCancel></IconCancel>
  </div>
</div>
<div class="btn-2">
  <span>გაუქმება</span>
</div>
</div>


</div>

</div>
    </transition>
</div>


<div class="container note-container">
<div class="note-momma">
<div class="ekimo-note">
  <img :src="require(`@/assets/img/ekimo-logo-white-on-red.svg`)">
  <span>ჯავშნის გაუქმება შესაძლებელია მხოლოდ EKIMO-ს აპლიკაციით</span>
</div>
<router-link to="/">
<div class="go-back-btn">
  <div class="arrow">
    <img :src="require(`@/assets/img/arrow-to-left.svg`)">
  </div>
  <span>უკან</span>
</div>
</router-link>

</div>
</div>

<div class="container reserved-container">

  <div class="row row-header">
    <div class="col clinic">
      <span>კლინიკა</span>
      
      </div>
    <div class="col speciality">
      <span>
      ექიმის სპეციალობა
      </span>
      </div>
    <div class="col name">
      <span>ექიმის სახელი და გვარი</span>
      
      </div>
    <div class="col time">
      <span>დრო</span>

    </div>
    <div class="col date">
      <span>თარიღი</span>
          
    
      </div>
    <div class="col status">
      <span>სტატუსი</span>
      </div>
    <div class="col cancel">
      
      <span>ჯავშნის გაუქმება</span>
      </div>
  </div>
<div class="row-doctors-momma lg-only" >
  <div class="row row-doctors">
    <div class="col clinic">
      <span>გლდანის პოლიკლინიკა</span>
      </div>
    <div class="col speciality">
   <span> ოფთალმოლოგი</span> 
      </div>
    <div class="col name">
      <img :src="require(`@/assets/img/Mask Group 12@2x.png`)">
      <span class="name-span">გიორგი აბულაძე</span>
      <div class="info-spans sm-only">
        <span>გიორგი აბულაძე</span>
        <span>ოფთალმოლოგი</span>
        <span>დიდუბის პოლიკლინიკა</span>
      </div>
      <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col time">
      <span>12:00 - 12:30</span>
      </div>
    <div class="col date">
      <span>11/08/2020</span>
          
    <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col status">
      <span>დაჯავშნილია</span>
      </div>
    <div class="col cancel" @click="modalToggle">
            <div class="cancel-child">
        <img :src="require(`@/assets/img/Icon material-cancel.svg`)">
      <span>გაუქმება</span>
            </div>
      </div>
  </div>
   

  <div class="row row-doctors">
    <div class="col clinic">
      <span>დიდუბის პოლიკლინიკა</span>
      </div>
    <div class="col speciality">
     <span>გინეკოლოგი</span>
      </div>
    <div class="col name">
      <img :src="require(`@/assets/img/Mask Group 15@2x.png`)" alt="">
      <span class="name-span">ვახო მშვიდობაძე</span>
      <div class="info-spans sm-only">
        <span>გიორგი აბულაძე</span>
        <span>ოფთალმოლოგი</span>
        <span>დიდუბის პოლიკლინიკა</span>
      </div>
      <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col time">
      <span>12:00 - 12:30</span>
      </div>
    <div class="col date">
      <span>11/08/2020</span>
          
    <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col status">
        <img :src="require(`@/assets/img/ekimo-logo-red.svg`)" class="ekimo-icon">
        
      <span>EKIMO-ს ჯავშანი</span>
      <div class="info-box">
        <img :src="require(`@/assets/img/Icon material-info.svg`)" class="i-icon">
      </div>
      </div>
    <div class="col cancel">
    
      <span></span>
      </div>
  </div>

  <div class="row row-doctors">
    <div class="col clinic">
      <span>გლდანის პოლიკლინიკა</span>
      </div>
    <div class="col speciality">
   <span> ოფთალმოლოგი</span> 
      </div>
    <div class="col name">
      <img :src="require(`@/assets/img/Mask Group 12@2x.png`)">
      <span class="name-span">გიორგი აბულაძე</span>
      <div class="info-spans sm-only">
        <span>გიორგი აბულაძე</span>
        <span>ოფთალმოლოგი</span>
        <span>დიდუბის პოლიკლინიკა</span>
      </div>
      <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col time">
      <span>12:00 - 12:30</span>
      </div>
    <div class="col date">
      <span>11/08/2020</span>
          
    <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col status">
      <span>დაჯავშნილია</span>
      </div>
    <div class="col cancel" @click="modalToggle">
            <div class="cancel-child">
        <img :src="require(`@/assets/img/Icon material-cancel.svg`)">
      <span>გაუქმება</span>
            </div>
      </div>
  </div>
   

  <div class="row row-doctors">
    <div class="col clinic">
      <span>დიდუბის პოლიკლინიკა</span>
      </div>
    <div class="col speciality">
     <span>გინეკოლოგი</span>
      </div>
    <div class="col name">
      <img :src="require(`@/assets/img/Mask Group 15@2x.png`)" alt="">
      <span class="name-span">ვახო მშვიდობაძე</span>
      <div class="info-spans sm-only">
        <span>გიორგი აბულაძე</span>
        <span>ოფთალმოლოგი</span>
        <span>დიდუბის პოლიკლინიკა</span>
      </div>
      <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col time">
      <span>12:00 - 12:30</span>
      </div>
    <div class="col date">
      <span>11/08/2020</span>
          
    <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col status">
        <img :src="require(`@/assets/img/ekimo-logo-red.svg`)" class="ekimo-icon">
        
      <span>EKIMO-ს ჯავშანი</span>
      <div class="info-box">
        <img :src="require(`@/assets/img/Icon material-info.svg`)" class="i-icon">
      </div>
      </div>
    <div class="col cancel">
    
      <span></span>
      </div>
  </div>


  <div class="row row-doctors">
    <div class="col clinic">
      <span>გლდანის პოლიკლინიკა</span>
      </div>
    <div class="col speciality">
   <span> ოფთალმოლოგი</span> 
      </div>
    <div class="col name">
      <img :src="require(`@/assets/img/Mask Group 12@2x.png`)">
      <span class="name-span">გიორგი აბულაძე</span>
      <div class="info-spans sm-only">
        <span>გიორგი აბულაძე</span>
        <span>ოფთალმოლოგი</span>
        <span>დიდუბის პოლიკლინიკა</span>
      </div>
      <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col time">
      <span>12:00 - 12:30</span>
      </div>
    <div class="col date">
      <span>11/08/2020</span>
          
    <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col status">
      <span>დაჯავშნილია</span>
      </div>
    <div class="col cancel" @click="modalToggle">
            <div class="cancel-child">
        <img :src="require(`@/assets/img/Icon material-cancel.svg`)">
      <span>გაუქმება</span>
            </div>
      </div>
  </div>
   

  <div class="row row-doctors">
    <div class="col clinic">
      <span>დიდუბის პოლიკლინიკა</span>
      </div>
    <div class="col speciality">
     <span>გინეკოლოგი</span>
      </div>
    <div class="col name">
      <img :src="require(`@/assets/img/Mask Group 15@2x.png`)" alt="">
      <span class="name-span">ვახო მშვიდობაძე</span>
      <div class="info-spans sm-only">
        <span>გიორგი აბულაძე</span>
        <span>ოფთალმოლოგი</span>
        <span>დიდუბის პოლიკლინიკა</span>
      </div>
      <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col time">
      <span>12:00 - 12:30</span>
      </div>
    <div class="col date">
      <span>11/08/2020</span>
          
    <div class="accordion-icon" @click="toggleAccordion">
        <span></span>    
        <span></span>    
    </div>
      </div>
    <div class="col status">
        <img :src="require(`@/assets/img/ekimo-logo-red.svg`)" class="ekimo-icon">
        
      <span>EKIMO-ს ჯავშანი</span>
      <div class="info-box">
        <img :src="require(`@/assets/img/Icon material-info.svg`)" class="i-icon">
      </div>
      </div>
    <div class="col cancel">
    
      <span></span>
      </div>
  </div>
   
  
 
    
  </div>


  <div class="row-doctors-momma sm-only " >
 
   <Accordion/>
  

   


 


    
  </div>

  
  
</div>
   
        
    </div>
</template>

<script>
import mainMixin from "@/mixins/main";
// import SlideUpDown from 'vue-slide-up-down'
import Accordion from "./Accordion";
import IconCancel from './IconCancel.vue';



export default{
  mixins: [mainMixin],
components: {
    Accordion,
  IconCancel
    
  },
  data(){

    return{
      show: false,
      showModal: false,
      showReserve: false
     
    }
  },
  computed:{
     
  },
  watch: {

  },
  methods: {
    toggleAccordion: function() {
      this.show = !this.show;
    },
    modalToggle: function() {
      this.showModal = !this.showModal;
      this.$root.$emit("modal-toggle");
      
      
    },
    toggleReserve: function() {
      this.showReserve = !this.showReserve;
    },
    heyFunc: function() {
      alert("mission accomplished");
      
    }
  },
  mounted() {
    

    this.$root.$on("modalToggle", () => {
      this.showModal = !this.showModal;
    })
  }
}
</script>

<style scoped>

.content {
  text-align: left;
  width: 100%;
  border-bottom: 1px solid black;
  
  transition: all ease-in-out .4s;
   opacity: 0;
  height: 0;
  width: 100%;
    
}

.content.active{
 opacity: 1;
  height: 100px;
}
</style>