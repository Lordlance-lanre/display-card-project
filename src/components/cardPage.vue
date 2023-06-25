<template>
	<div class="grids w-[600px] h-[1250px] md:w-full">
		<div>
			<h2 class="text-center text-purple-600 pt-4 text-3xl font-bold ">Random Card Project</h2>
		</div>
		<div class="grid grid-cols-2 my-20 pb-10">
			
		
		<button @click="showItem1" class="bg-slate-300 px-4 rounded md:mx-auto border-2 w-60 ml-4">
			<transition name="fade">
				<div v-if="remove">
					<header  class="">
						Head
					</header>
					<img class="w-32 mx-auto" :src="imageLink.message"/>

					<footer>
						Footer
					</footer>
				</div>
			</transition>

			<div>
				<p>{{word}}</p>
			</div>
		</button>

		<button @click="showItem2" class="bg-slate-300 px-4 rounded mx-auto border-2 w-60 ml-9">
			<transition name="display">
				<div v-if="unFaze">
					<header  class="">
						Head
					</header>
					<img class="w-60 mx-auto" :src="imageLine.message" alt=""/>

					<footer>
						Footer
					</footer>
				</div>
			</transition>
			<div>
			<p>{{wording}}</p>
			</div>
		</button>

		<button @click="showItem3" class="bg-slate-300 px-4 rounded mx-auto border-2 w-60 ml-4 md:ml-48 mt-8">
			<transition name="display">
				<div v-if="unSeen">
					<header  class="">
						Head
					</header>
					<img class="w-60 mx-auto" :src="imageTag.message" alt=""/>

					<footer>
						Footer
					</footer>
				</div>
			</transition>
			<div>
			<p>{{phrase}}</p>
			</div>
		</button>


		<button @click="showItem4" class="bg-slate-300 px-4 rounded mx-auto border-2 w-60 ml-9 mt-8">
			<transition name="display">
				<div v-if="unTag">
					<header  class="">
						Head
					</header>
					<img class="w-48 mx-auto" :src="imageOf.message" alt=""/>

					<footer>
						Footer
					</footer>
				</div>
			</transition>
			<div>
			<p>{{line}}</p>
			</div>
		</button>

		
		<button @click="showItem5" class="bg-slate-300 px-4 rounded mx-auto border-2 w-60 ml-4 md:ml-48 mt-8">
			<transition name="display">
				<div v-if="unLag">
					<header  class="">
						Head
					</header>
					<img class="w-60 mx-auto" :src="imageOne.message" alt=""/>

					<footer>
						Footer
					</footer>
				</div>
			</transition>
			<div>
			<p>{{slime}}</p>
			</div>
		</button>


		<button @click="showItem6" class="bg-slate-300 px-4 rounded mx-auto border-2 w-60 ml-9 mt-8">
			<transition name="display">
				<div v-if="unSlag">
					<header  class="">
						Head
					</header>
					<img class="w-60 mx-auto" :src="imageStone.message" alt=""/>

					<footer>
						Footer
					</footer>
				</div>
			</transition>
			<div>
			<p>{{some}}</p>
			</div>
		</button>
	</div>
	</div>
</template>

<script setup>
import {ref, onMounted} from "vue";
import axios from "axios";


const baseUrl = ("https://dog.ceo/api/breeds/image/random");

// first card
const remove = ref(false);
const word = ref("Click to reveal the card")
const imageLink = ref("");

const showItem1 = () =>{
	remove.value = !remove.value;

	if(remove.value == false){
		word.value = "Click to reveal the card";
	}else{
		word.value = "";
	}
}

const getData = () =>{
	axios.get(baseUrl)
         .then((res) => {
     	   imageLink.value = res.data; 
     	   console.log("image>>",res.data)
          });
}



// second card

const unFaze = ref(null);
const imageLine = ref("");
const wording = ref("Click to reveal the card")

const showItem2 = () =>{
	unFaze.value = !unFaze.value;

	if(unFaze.value == false){
		wording.value = "Click to reveal the card";
	}else{
		wording.value = "";
	}
}

const getData2 = () =>{
	axios.get(baseUrl)
         .then((res) => {
     	   imageLine.value = res.data; 
     	   console.log("image>>",res.data)
          });
}


// third card

const unSeen = ref(null);
const imageTag = ref("");
const phrase = ref("Click to reveal the card")

const showItem3 = () =>{
	unSeen.value = !unSeen.value;

	if(unSeen.value == false){
		phrase.value = "Click to reveal the card";
	}else{
		phrase.value = "";
	}
}

const getData3 = () =>{
	axios.get(baseUrl)
         .then((res) => {
     	   imageTag.value = res.data; 
     	   console.log("imageTag>>",res.data)
          });
}

// fourth card
const unTag = ref(null);
const imageOf = ref("");
const line = ref("Click to reveal the card")


const showItem4 = () =>{
	unTag.value = !unTag.value;

	if(unTag.value == false){
		line.value = "Click to reveal the card";
	}else{
		line.value = "";
	}
}

const getData4 = () =>{
	axios.get(baseUrl)
         .then((res) => {
     	   imageOf.value = res.data; 
     	   console.log("imageTag>>",res.data)
          });
}


// fifth card
const unLag = ref(null);
const imageOne = ref("");
const slime = ref("Click to reveal the card")


const showItem5 = () =>{
	unLag.value = !unLag.value;

	if(unLag.value == false){
		slime.value = "Click to reveal the card";
	}else{
		slime.value = "";
	}
}

const getData5 = () =>{
	axios.get(baseUrl)
         .then((res) => {
     	   imageOne.value = res.data; 
     	   console.log("image>>",res.data)
          });
}


// sixth card


const unSlag = ref(null);
const imageStone = ref("");
const some = ref("Click to reveal the card")


const showItem6 = () =>{
	unSlag.value = !unSlag.value;

	if(unSlag.value == false){
		some.value = "Click to reveal the card";
	}else{
		some.value = "";
	}
}

const getData6 = () =>{
	axios.get(baseUrl)
         .then((res) => {
     	   imageStone.value = res.data; 
     	   console.log("image>>",res.data)
          });
}


onMounted(() =>{
	getData();
	getData2();
	getData3();
	getData4();
	getData5();
	getData6();
})

</script>

<style scoped>

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}	

.display-enter-active,
.display-leave-active {
  transition: opacity 0.5s ease;
}

.display-enter-from,
.display-leave-to {
  opacity: 0;
}	

.grids{
background: rgb(147,95,166);
background: radial-gradient(circle, rgba(147,95,166,1) 9%, rgba(148,187,233,1) 94%);
}
</style>