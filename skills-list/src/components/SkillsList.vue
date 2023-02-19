<template>
  <div>
    <h1></h1>
    <form @submit.prevent="addSkill">
      <label for="new-skill"></label>
      <input
        class="input-skill"
        id="new-skill"
        v-model="newSkill"
        type="text"
        required
        placeholder="Add new skill"
      />
    </form>
    <ul>
      <li class="test" v-for="(skill,index) in skills" :key="index">
        <center class="cnt">
          <div class="skill">
            <span>{{index}}.{{skill}} </span
            ><span class="remove" @click="removeSkill(index)">Delete</span>
          </div>
        </center>
        <div class="bottom"></div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      skills:[],
      newSkill: '',
    };
  },
  methods:{
    addSkill(){
      if(this.newSkill && !this.skills.includes(this.newSkill)){
        this.skills.push(this.newSkill);
        this.newSkill = '';
      }
    },
        removeSkill(index){
          this.skills.splice(index, 1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cnt {
  margin-bottom: 10px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
  margin: 5px;
  width: 500px;
  margin: auto;
}
li {
  display: inline-block;
  margin-bottom: 3px !important;
  height: 50px;
}
a {
  color: #42b983;
}
.test {
  color: black;
  margin: auto;
  text-align: left;
  height: 30px;
  font-size: 20px;
  margin-bottom: "10px";
  width: 500px;
  display: inline-block;
}
.skill {
  background-color: #87ceeb;
  text-align: left;
  height: 50px;
  font-size: 20px;
  display: flex;
  width: 500px;
  justify-content: space-between;
    margin-bottom: 3px !important;

}
.input-skill {
  background: black;
  color: white;
  height: 50px;
  width: 500px;
}
.remove {
  cursor: pointer;
}
</style>
