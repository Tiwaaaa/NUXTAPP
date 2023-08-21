<template>
    <div class="card mt-3 container" style="width: 18rem;">
  <img :src="picture" class="card-img-top " style="border-radius: 400%;" >

  <div class="card-body">
    <p class="card-text">ชื่อ : {{ firstname }} </p>
    <p class="card-text">นามสกุล :{{ lastname }}</p>
    <p class="card-text">อายุ :{{ age }}</p>
    <p class="card-text">ที่อยู่ :{{ address }}</p>
    <button @click="showData">คลิกเพื่อดูข้อมูล</button>
    <button @click="increment(10)">เพิ่มค่า</button>
    <button @click="decrement(3)">ลดค่า</button>
  </div>
</div>

<div class="container ">
    <div class="row" style="margin-left: 200px;">
        <div class="col">
            <div class="card mb-5 mt-5" style="width: 18rem;">
                <p v-if="hobby.length===0">ไม่มีงานอดิเรก</p>
                <div v-else>
                    <ul class="list-group list-group-flush ">
                        <li class="list-group-item "  style="background-color: rgb(168, 155, 180);">Hobby</li>
                        <li class="list-group-item" v-for="item in hobby">{{ item }}</li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="col">
            <div class="card mb-5 mt-5" style="width: 18rem;">
                <ul class="list-group list-group-flush ">
                    <li class="list-group-item "  style="background-color: rgb(168, 155, 180);">more</li>
                    <li class="list-group-item" v-for="(value,key) in general" :key="key">{{ key}} : {{ value }}</li>
                </ul>
            </div>
        </div>
    </div>
</div>

</template>

<script>
export default{
    data(){
        return{
            firstname:"Tiwaporn",
            lastname: "Pengnoy",
            age: 19,
            address: "51/12 m.2 Samnakton,Banchang,Rayong 21130",
            picture:"https://rms.tatc.ac.th/files/importpicstd/01/66309010011.jpg",
            hobby:["ทำไร่","ทำสวน","ฟังเพลง","ดูหนัง","เล่นกีฬา"],
            general:{เพศ:"หญิง",น้ำหนัก:40,ส่วนสูง:159,โรคประจำตัว:false}
        }
    },
    methods: {

    getFullname(){
        return `$(this.firstname) $(this.lastname)`
    },
    showData(){
        alert(this.firstname)
    },
    increment(value){
        this.age += value
    },
    decrement(value){
        this.age -= value
    },
    setNickName(event){
        this.nickname=event.target.value
    },
    submitForm(){
        alert('บันทึกข้อมูลเรียบร้อย')
    }

}
}

</script>
