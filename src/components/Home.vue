<template>
  <transition 
	appear 
	v-on:before-appear="beforeAppear"
  	v-on:appear="appear"
  	v-on:after-appear="afterAppear"
  	v-on:appear-cancelled="cancelAppear">
	  <div id="home-container">
		<div>
			<h1 id="name">{{ name }}</h1>
	  		<h4 id="msg">{{ msg }}</h4>
		</div>
		<div>
		  <p id="links-group">
			<span v-for="link in links">
			  <a class="home-link" target="_blank" :href=link.url><i :class=link.icon></i></a> 
			</span>
		  </p>
	    </div>
	  </div>
  </transition>
</template>

<script>
import Velocity from 'velocity-animate'

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
  },
  methods: {
    beforeAppear: function (el) {
      el.querySelector('#name').style.opacity = 0
      el.querySelector('#msg').style.opacity = 0
      el.querySelector('#links-group').style.opacity = 0
    },
    appear: function (el, done) {
      var name = el.querySelector('#name'),
	      msg = el.querySelector('#msg'),
	      linksGroup = el.querySelector('#links-group');
      
      Velocity(name, { opacity: 1, }, { delay: 100 })
      Velocity(msg, { opacity: 1 }, { delay: 300})
      Velocity(linksGroup, { opacity: 1 }, { delay: 600})
      Velocity(el, { fontSize: '1em' }, { delay: 800, complete: done })
    },
    afterAppear: function (el, done) {
    /*
      Velocity(el, { rotateZ: '50deg' }, { duration: 600 })
      Velocity(el, { rotateZ: '100deg' }, { loop: 2 })
      Velocity(el, {
        rotateZ: '45deg',
        opacity: 0
      }, { complete: done })
    */
    },
    cancelAppear: function(){}
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
</style>
