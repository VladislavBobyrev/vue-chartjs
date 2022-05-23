<template>
  <div class="home">
    <input type="number" v-model="oneInt">
    <input type="number" v-model="twoInt">
    <calculator :calc='numbers'/>
   <h1>Сумма Ваших чисел: {{numbers}}</h1>
  </div>
</template>

<script lang="ts">
import {   defineComponent, Ref, ref, watch } from 'vue';

export default defineComponent({
  name: 'HomeView',
  components: {
  },
  setup() {
    let numbers:Ref<number> = ref(2)

    const oneInt:Ref<number> = ref(2)
    const twoInt:Ref<number>= ref(2)

     watch([oneInt, twoInt], () => {
      return   numbers.value = twoInt.value + oneInt.value
    })

  //   // рекурсия 

  // /**
  //  * @function принимает два аргумента По результатам работы гарантируется что в результирующем тексте нет искомого образца
  //  * @param str  текст на изменение
  //  * @param x  образец, которого в тексте быть/стать не должно
  //  */
    // const fn = (str:string, x:string):string => 
    // {
    //   return str.replace(x, '') !== str  ? fn(str.replace(x, ''), x)  : str
    // }
    // const res =  fn('abcabcacbcbbacdDCBabcCD', 'abc')
    // console.log(res)



  //   // reg Exp
  //   const id:number = 12345
  //   // const regexp = /3.\d+/  // удалить все числа после цифры 3
  //   const regexp = /(id)(.*\d)/  // заменить id до первого / но слово id не удалять/
  //   let url:string = `https://abccdedefg.com/houm/abccdedefg/?id${id}bc6789/`;

  //   const upadteUrl = url.replace(regexp, "$1")

  //   // split
  //  console.log(url.split(`abccdedefg`).join(`about`))
  
  // // map
  // // let lengths = [{name:"Bilbo", salary: 30}, {name:"Gandalf",salary: 30}, {name:"Nazgul", salary: 30}].map((item) =>  item.salary);
  // let lengths = [{name:"Bilbo", salary: 30}, {name:"Gandalf",salary: 30}, {name:"Nazgul", salary: 220}].reduce((item, curentValue, curentIdx, arr) => 
  // {
  //  return arr[curentIdx].salary += curentValue.salary
  // }); 

    return {
      numbers,
      oneInt,
      twoInt,
    }
  }
});
</script>
