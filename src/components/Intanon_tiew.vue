<template>
  <div class="col" v-for="(n) in travellist" :key="n">
    <div class="name">
      <h3>{{ n.name }}</h3>
    </div>
    <div class="tipark">
      <RouterLink to="/intanon_tipak">ที่พัก</RouterLink> /
      <RouterLink to="/intanon_tiew">สถานที่เที่ยว</RouterLink>
    </div>
  </div>
    <h3>สถานที่เที่ยวใกล้ๆ</h3>
  <div class="col" v-for="(near, index) in neartravel" :key="index">
      <div class="name">
        <div class="name">
        <img :src="near.img" style="width: 80%;" alt="รูปภาพ 1">
        <img :src="near.img2" style="width: 80%;" alt="รูปภาพ 2">
        <h4>{{ near.name }}</h4>
      </div>
      <div class="titravel">
        <p>{{ near.text_box }}</p>
        <p>สถานที่ : {{ near.Location }}</p>
        <p>เบอร์ติดต่อ : {{ near.phone }}</p>
        <p>ราคา :{{ near.Price }}</p>
        <p>เวลา : {{ near.time }}</p>
        <p>Facebook : <a :href="near.link">{{ near.Facebook }}</a></p>
        <p>พิกัด : <a :href="near.place">{{ near.place }}</a></p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const travellist=ref([
{name: 'ดอยอินทนนท์', img:"https://www.reviewchiangmai.com/wp-content/uploads/2022/06/doi-inthanon-1536x1024.jpg", quantity: 0 ,
text_box:'เดินทางโดยสวัสดิภาพ'
}])

const neartravel=ref([
{ name: 'พระมหาธาตุนภเมทนีดล พระมหาธาตุนภพลภูมิสิริ' , 
  img: "https://s.isanook.com/tr/0/ud/284/1424571/1-1-768x512.jpg?ip/resize/w728/q80/jpg",
  img2: "https://dynamic-media-cdn.tripadvisor.com/media/photo-o/0d/91/4d/68/caption.jpg?w=1200&h=-1&s=1",
  text_box:'สักการะ พระมหาธาตุนภเมทนีดล และ พระมหาธาตุนภพลภูมิสิริ ที่ประดิษฐานอยู่บริเวณทางแยกของถนนก่อนขึ้นยอดดอยอินทนนท์ โดย พระมหาธาตุนภเมทนีดล นั้นจะเป็นสีน้ำตาล สัณฐานทรงระฆัง 8 เหลี่ยม ถือเป็นพระมหาสถูปเจดีย์องค์แรกที่ตั้งอยู่สูงที่สุดในไทย ส่วน พระมหาธาตุนภพลภูมิสิริ นั้นจะเป็นทรง 12 เหลี่ยม สีม่วงอมชมพู ประดับโมเสกแก้ว ด้านในนั้นเป็นที่ประดิษฐานพระบรมสารีริกธาตุ หากมีโอกาสเดินทางไปยังยอดดอยอินทนนท์แล้ว ก็อย่าลืมแวะไปชมความสวยงามของพระมหาธาตุทั้ง 2 องค์ด้วยนะคะ' ,
  Location:' อุทยานแห่งชาติดอยอินทนนท์ ตำบลบ้านหลวง อำเภอจอมทอง จังหวัดเชียงใหม่' ,
  place:'https://goo.gl/maps/nH77dzuFqm4tx9gr8',
  Price:' คนไทย ผู้ใหญ่ 50 บาท เด็ก 20 บาท , ต่างชาติ ผู้ใหญ่ 200 บาท เด็ก 100 บาท',
  time:'05.00-17.00 น.',
  phone: '05-335-5728',
  link:'https://www.facebook.com/profile.php?id=100068951658344',
  Facebook:'พระมหาธาตุนภเมทนีดล นภพลภูมิสิริ กองทัพอากาศ'
},
{ name:'กิ่วแม่ปาน' , 
  img: "https://www.gooutthailand.com/wp-content/uploads/2022/09/kew-mae-pan-1.jpg",
  img2:"https://f.ptcdn.info/923/010/000/1381748685-CH225443-o.jpg",
  text_box:'  ไปกอดอากาศหนาว ชมทะเลหมอกสุดปังอลังการที่ กิ่วแม่ปาน จุดชมพระอาทิตย์ขึ้น และจุดชมทะเลหมอกที่สวยงามมากที่สุดแห่งหนึ่งในประเทศไทย อีกทั้งยังมีเส้นทางเดินศึกษาธรรมชาติที่จะพาเราเดินชมธรรมชาติอุดมสมบูรณ์ภายใน อุทยานแห่งชาติดอยอินทนนท์ ในระยะทางประมาณ  3-5 กิโลเมตรด้วยค่ะ ตลอดทางเราก็จะได้พบกับพืชพรรณนานาชนิด น้ำตก และวิวสวยๆ ระหว่างการเดินทางบนสันเขา เมื่อมาถึงจุดชมวิวของกิ่วแม่ปาน เห็นภาพของพระมหาธาตุเจดีย์คู่ และแนวเขาที่ปกคลุมไปด้วยทะเลหมอกสีขาว ก็รู้สึกหายเหนื่อยในพริบตา' ,
  Location:'อุทยานแห่งชาติดอยอินทนนท์ บริเวณกิโลเมตรที่ 43 ของถนนจอมทอง-ดอยอินทนนท์ อำเภอจอมทอง สันป่าตอง และแม่แจ่ม จังหวัดเชียงใหม่' ,
  place:'https://goo.gl/maps/tfkjFPX4YGbzRWAC9',
  phone:'053286729',
  Price:'200 บาท',
  time:'06.00-16.00 น.',
  link:'https://www.facebook.com/profile.php?id=100069195128485',
  Facebook:'กิ่วแม่ปาน'
},
{ name: 'น้ำตกแม่ยะ' , 
  img: "https://th.bing.com/th/id/OIP.xzjL8YWdP66KU7pdhNKXPAHaEK?pid=ImgDet&rs=1",
  img2:"https://i.ytimg.com/vi/7dVvVMT1EAU/hq720.jpg",
  text_box:'น้ำตกขนาดใหญ่ที่สุดในอุทยานแห่งชาติดอยอินทนนท์ ด้วยความสูงกว่า 260 เมตร พร้อมกับสายน้ำที่ไหลลดหลั่นลงมาถึง 30 ชั้น ทำให้ที่นี่ได้รับการยกย่องให้เป็นหนึ่งในน้ำตกที่สวยที่สุดในประเทศไทยค่ะ พวกเราสามารถเที่ยวน้ำตกแม่ยะได้ตลอดทั้งปี แต่ช่วงฤดูฝนคือช่วงที่สวยที่สุด แถมธรรมชาติรอบด้านก็มีความร่มรื่นมากๆ ด้วย' ,
  Location:'อุทยานแห่งชาติดอยอินทนนท์ ตำบลบ้านหลวง อำเภอจอมทอง จังหวัดเชียงใหม่' ,
  place:'https://goo.gl/maps/xXBwe6fohXqXhu519',
  Price:'คนไทย ผู้ใหญ่ 50 บาท เด็ก 20 บาท, ต่างชาติ ผู้ใหญ่ 200 บาท เด็ก 100 บาท ',
  time:'08.00-17.00 น.',
  phone:'0-5328-6729',
  link:'https://www.facebook.com/pages/%E0%B8%99%E0%B9%89%E0%B8%B3%E0%B8%95%E0%B8%81%E0%B9%81%E0%B8%A1%E0%B9%88%E0%B8%A2%E0%B8%B0-%E0%B8%AD%E0%B8%B8%E0%B8%97%E0%B8%A2%E0%B8%B2%E0%B8%99%E0%B9%81%E0%B8%AB%E0%B9%88%E0%B8%87%E0%B8%8A%E0%B8%B2%E0%B8%95%E0%B8%B4%E0%B8%94%E0%B8%AD%E0%B8%A2%E0%B8%AD%E0%B8%B4%E0%B8%99%E0%B8%97%E0%B8%99%E0%B8%99%E0%B8%97%E0%B9%8C-%E0%B8%AD%E0%B8%B3%E0%B9%80%E0%B8%A0%E0%B8%AD%E0%B8%88%E0%B8%AD%E0%B8%A1%E0%B8%97%E0%B8%AD%E0%B8%87-%E0%B8%88%E0%B8%B1%E0%B8%87%E0%B8%AB%E0%B8%A7%E0%B8%B1%E0%B8%94%E0%B9%80%E0%B8%8A%E0%B8%B5%E0%B8%A2%E0%B8%87%E0%B9%83%E0%B8%AB%E0%B8%A1%E0%B9%88/103238131469125',
  Facebook:'น้ำตกแม่ยะ อุทยานแห่งชาติดอยอินทนนท์ อำเภอจอมทอง จังหวัดเชียงใหม่'
},
{ name: 'บ้านแม่กลางหลวง' , 
  img: "https://cms.dmpcdn.com/travel/2020/11/18/ccfd3850-297d-11eb-8c49-6ff1aae212a5_original.jpg",
  img2:"https://i.pinimg.com/originals/73/6a/df/736adf5f38f28e082a44a17b6e153a76.jpg",
  text_box:'จุดแวะพักก่อนไปเที่ยวกันต่อในดอยอินทนนท์ ตั้งอยู่บนลุ่มแม่น้ำแม่กลาง ซึ่งเป็นลุ่มแม่น้ำชั้นที่ 3 ของดอยอินทนนท์ และเป็นที่อยู่อาศัยของชาวปกาเกอะญอ ซึ่งส่วนใหญ่จะทำอาชีพทำไร่ทำนา ปลูกข้าว และปลูกกาแฟเป็นหลัก ตัวหมู่บ้านจึงรายล้อมไปด้วยนาขั้นบันได และไร่กาแฟ ซึ่งจะงดงามสุดๆ ในช่วงฤดูฝนและปลายฝนต้นหนาวค่ะ จะไปถ่ายรูปกับทุ่งนาแสนสวย หรือจิบกาแฟหอมกรุ่นก็ฟินทั้งคู่ 😊☕️' ,
  Location:'ตำบลบ้านหลวง อำเภอจอมทอง จังหวัดเชียงใหม่' ,
  place:'https://goo.gl/maps/ZSAi4tMmoER7DZ4E9',
  Price:'-',
  time:'เข้าชมได้ตลอดทั้งวัน',
  phone:'083 508 1282',
  link:'https://www.facebook.com/maekalngluang',
  Facebook:'วิสาหกิจชุมชนการท่องเที่ยวบ้านแม่กลางหลวง'
},
  
])
</script>

<style>

.card-img-top{
height: 100%;
padding: 25px;

}
.box_all{
justify-content: center;
align-items: center;
margin-left: 30%;
text-align: center
}

</style>
