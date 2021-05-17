<template>
    <form v-on:submit="addTask">
        <label>Task Name</label>
        <input v-model="text" type="text" placeholder="Your name..">

        <label>day</label>
        <input v-model="day" type="text" placeholder="Your last name..">
        <div>
            <label>Set Reminder</label>
            <input v-model="reminder"  type="checkbox">
        </div>
        
  
        <input type="submit" value="Submit">
    </form>
</template>

<script>
export default {
    name:'AddTask',
    data(){
        return{
            id:'',
            text:'',
            day:'',
            reminder:false
        }
    },
    methods:{
        addTask(e){
         
         e.preventDefault();
           const newTask = {
               id:Math.floor(Math.random()*10000),
               text:this.text,
               day:this.day,
               reminder:this.reminder
           }
          // console.log(newTask)
           
           this.$emit('add-task',newTask);

           this.text='',
           this.day='',
           this.reminder=false
        }
    }
}
</script>

<style scoped>
input[type=text] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

div{
    display: flex;
    justify-content: space-between;
    align-items: center;
}

input[type=submit] {
  width: 100%;
  background-color: #4CAF50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type=submit]:hover {
  background-color: #45a049;
}

div {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>