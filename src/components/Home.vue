<template>
  <transition 
	appear 
	appear-class="slide"
	appear-to-class="slide-to">
	  <div id="home-container">
		<div>
			<h1 id="name">{{ name }}</h1>
	  		<h4>{{ msg }}</h4>
		</div>
		<div>
		  <p>
			<span v-for="link in links">
			  <a class="home-link" target="_blank" :href=link.url><i :class=link.icon></i></a> 
			</span>
		  </p>
	    </div>
	  </div>
  </transition>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      name: 'WOOSUNGCHU',
      msg: 'Hello there',
      links: [
      	{url:'https://github.com/woosungchu',icon:'fa fa-github fa-2x'},
      	{url:'https://www.linkedin.com/in/woosung-chu-3875a711a/',icon:'fa fa-linkedin-square fa-2x'},
      	{url:'https://stackshare.io/woosungchu/did',icon:'fa fa-angellist fa-2x'}
      ]
    }
  }
}
</script>

<style scoped>
#home-container{
  letter-spacing: 16px;
  padding-top:20%;
}

#home-container * {
  margin-top:8px;
}

#name{
  font-weight: bold;
  font-size: 46px;
}

.home-link{
  color:black !important;
}

.slide {
  transform: translateX(-10px);
  opacity: 0;
}
.slide-to {
  transition: all .3s ease;
}

</style>
