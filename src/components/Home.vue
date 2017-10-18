<template>
<div>
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
</div>
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
  },
  methods: {
  },
  mounted(){
    var container = document.getElementById("home-container"),
        cnt = 1, limit = 100;
    var a = setInterval(function(){
      if(cnt > limit){
        clearInterval(a);
      }else{
        container.style.opacity = cnt / limit;
        cnt += 1;
      }
    },3);
  }
  
}
</script>

<style scoped>
#home-container{
  letter-spacing: 16px;
  padding-top:20%;
  opacity: 0;
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
