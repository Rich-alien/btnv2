<template>
  <div class="v-catalog">
	
	<button @click=" getRandomNumber" v-on:click="show = !show" class="button">Touch me</button>
	<div class="block">
			<transition name="bounce">
			<h1 v-if="show" class="fg">{{text[number]}}</h1>
			</transition>	
	</div>
	<!-- <h1 class='TextInBtn'>Touch me</h1> -->
  </div>
</template>

<script>
	
export default {
 name: 'v-catalog',
 components:{
 },
 props:{},
 data(){
	return{
		text:[
		'Откусить мыло',
		'Прожевать горсть кошачьей еды',
		'Обменяться какой нибудь одеждой',
		'Тверкать у стены вниз головой',
		'В течение минуты притворяться , что ты озвучиваешь хентай',
		'В течение  минуты общаться кукареканием',
		'Поделись сигой',
		'Съесть мазик  с сладким',
		'Позволь соседу  нарисовать тебе на лбу что-нибудь',
		'Написать незнакомцу выебать тебя',
		'Рассказать одну историю',
		'Сделать кофе',
		'Пойти покурить',
		'Эротичный  танец',
		'Съесть что нибудь с пола',
		'Минуту изображать бьющегося в агонии дельфина',
		'Пропуск хода',
		'Пропуск хода',
		'Отрезать себе несколько прядей волос',
		'Притворись что занимаешься кексом с подушкой',
		'Спой что-нибудь максимально противным голосом',
		'Минуту изображай кошку с течкой',
		'Вылей на себя стакан воды',
		'',
	
		
		
		
			

		],
		show:false,
		number:0,
	}
 },
 methods:{
	 getRandomNumber(){
		 this.number=Math.floor(Math.random()*this.text.length);
		 console.log(this.number);
		 console.log(this.text.length);
	 }
 }

}
</script>


<style lang="scss">
.block{
	max-width: 1000px;
}
.v-catalog{
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 100%;
	height: 100vh;
	background: url(bgcImage/1.png) no-repeat;
}
.TextInBtn{
	color: #CD47F1;
	letter-spacing: 1px;
	transform: translateY(-250px);
	font-size: 50px;
	z-index: 0;
	position: fixed;
	
}
.bounce-enter-active {
  animation: bounce-in .5s;
}
.bounce-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}

	.button{
		background-color: black;
		border: none;
		margin-top: 120px;
		width: 750px;
		height: 500px;
		opacity: 0;
		color:white;
		font-size: 40px;
		z-index: 1;
		
		
	}
	.button:focus{
		outline: none;
	
	}
	.button:hover{
		cursor: pointer;
			// animation: bubble 1s infinite ease-in-out;
		


	}
		@keyframes bubble{
			
		}
		.fg{
			color: white;
			margin: 0;
			margin-top: 200px;
			letter-spacing: 3px;
			font-weight: 900;
			font-size: 45px;
			
		}
  
</style>
