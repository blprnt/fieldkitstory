<template>
  <div id="app">
    <img alt="Fieldkit Landscape" src="./assets/Fieldkit_Panel 01_Final_sized.png" />
    <HelloWorld msg="Welcome to Fieldkit." msg2="Fieldkit lets everyone everywhere monitor the world around them with low-cost, reliable sensors and easy-to-use tools for storing, sharing and telling stories with data."/>
    <img alt="Fieldkit Easy Install" src="./assets/Fieldkit_Panel 02_Final_sized.jpg" />
    <HelloWorld msg="Easy-to-use environmental sensing." msg2="Fieldkit sensors are designed to be accurate, durable and extensible. Our mobile app makes configuration, testing and deployment easy for amateurs and professionals alike."/>
    <img alt="Fieldkit Easy Install" src="./assets/Fieldkit_Panel 03_Final_sized.jpg" />
    <HelloWorld msg="For sensor projects, big and small." msg2="Fieldkit’s low per-unit cost makes deploying networks of several, dozens, even hundreds of sensors possible - no matter how small the budget."/>
    <img alt="Fieldkit Easy Install" src="./assets/Fieldkit_Panel 04_Final_sized.jpg" />
    <HelloWorld msg="Easily explore and share your data." msg2="The fieldkit platform securely stores and manages your data, and lets you share and tell stories with it."/>
    <img alt="Fieldkit is for everyone" src="./assets/Fieldkit_Panel 05_Final_sized.png" />
    <HelloWorld msg="Fieldkit is for everyone." msg2="We’re building fieldkit because we believe everyone should be able to understand and advocate for the world they live in.

    Fieldkit is a tool for field scientists, environmental advocates, naturalists, students and teachers, and most importantly… it’s for you!
    "/>
     <img id="campers" alt="Fieldkit Easy Install" src="./assets/Fieldkit_People_01.png" />
    <HelloWorld msg="We have some questions. Will you help out?" msg2="We've been busy in the lab making first public versions of the Fieldkit sensors + software platform. We're trying to learn a bit more about how people might use Fieldkit in the real world. If you can help us to answer a few easy questions (it should only take three or four minutes), we'll give you a special discount when Fieldkit is released."/>
    <RoleForm msg="What role best describes what you do?"/>
    <Chooser msg="As a prospective Fieldkit user, which of these features would be more important to you?" right="Low per-unit cost" left="Long battery life" v-on:choose="choose()" total=5 />
    <Contact msg="Can we stay in touch?"/>



  </div>

  

</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import RoleForm from "./components/RoleForm.vue"
import Chooser from "./components/Chooser.vue"
import Contact from "./components/Contact.vue"

const features = [
  "Low per-unit cost",
  "Long battery life in the field",
  "Easy sharing of data",
  "Data visualization",
  "Integration with social media feeds",
  "Research-grade data",
  "Easy setup for non experts"
]

function switchChoose() {
  alert('test');
}

function pickTwo() {
  var i1 = Math.floor(Math.random() * (features.length - 1));
  var i2 = i1 + Math.ceil(Math.random() * (features.length - 1 - i1));
  return([i1, i2]);
}

export default {
  name: "app",
  components: {
    HelloWorld, RoleForm, Chooser, Contact
  },
  methods: {
    choose: function(targ) {
      var picks = pickTwo();
      this.$children[7].left = features[picks[0]];
      this.$children[7].right = features[picks[1]];
      this.$children[7].total --;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  margin-left:15%;
  margin-right:15%;
}

img {
  max-width:100%;
}

#campers {
  width:50%;
}

p {
  font-size:1.5em;
  text-align: left;
}
</style>
