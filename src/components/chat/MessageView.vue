<template>
    <v-card variant="tonal"      
 >
      <v-list  
      :items="messageView" :key="messageView" 	item-props lines="false">
        <template v-slot:subtitle="{ item }">
          <v-list-item-subtitle       >
            <div style="white-space: pre-wrap">
              <template v-if="item.subtitle.includes('```') " >
                <template v-for="(line, index) in item.subtitle.split('`')" :key="line">
                  <template v-if="line.trim() !== ''">
                    <template v-if="index % 2 === 0">{{ line }}</template>
                    <template v-else>
                      <div class="code-block">{{ line }}</div>
                    </template>
                  </template>
                </template>
              </template>
              <template v-if="item.title==='Ошибка'">
            <div class="code-block" style="color: red;">
             {{  item.subtitle }}  </div>
              </template>
              <template v-if="!item.subtitle.includes('```') && item.title!=='Ошибка'">
                <div >{{ item.subtitle }}</div>
              </template>
            </div>
          </v-list-item-subtitle>
        </template>
      </v-list>
    </v-card>
  </template>
  
  
<script setup>
import { defineProps } from 'vue';


const props = defineProps({
    messageView:{
        type:Array,
        required: true
    },
    subtitle:{
        type:String
    }
})





</script>  

<style>


.code-block {
  position: relative;
  font-family: "Fira Code", monospace;
  font-size: 16px;
  background-color: #000000;
  color: #f0f1f3;
  padding: 20px;
  margin: 20px 0;
  border-radius: 10px;
  border: none;
  overflow-x: auto;
  line-height: 1.5;
}

.code-block[class*="language-"] {
  position: relative;
}

.code-block[class*="language-"] > code:before {
  content: attr(class);
  background: #abb2bf;
  color: #282c34;
  font-size: 14px;
  font-weight: bold;
  padding: 4px 8px;
  position: absolute;
  top: -20px;
  left: 20px;
  border-radius: 5px;
  box-shadow: 0px 3px 5px rgba(0, 0, 0, 0.3);
}

.code-block[class*="language-"] > code {
  position: relative;
  white-space: pre-wrap;
}

.code-block[class*="language-"] > code:before {
  content: "";
  position: absolute;
  top: 20px;
  bottom: 20px;
  left: 20px;
  width: 30px;
  background-color: #282c34;
  color: #abb2bf;
  text-align: right;
  padding: 20px 0;
  pointer-events: none;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
  box-shadow: 3px 0px 5px rgba(0, 0, 0, 0.3);
}

.code-block[class*="language-"] > code:after {
  content: "";
  position: absolute;
  top: 20px;
  bottom: 20px;
  right: 0;
  width: 20px;
  background-color: #000000;
  color: #abb2bf;
  pointer-events: none;
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;
  box-shadow: -3px 0px 5px rgba(0, 0, 0, 0.3);
}

.code-block[class*="language-"] > code > span {
  display: block;
  padding-left: 50px;
  position: relative;
}

.code-block[class*="language-"] > code > span:before {
  content: attr(data-line-number);
  position: absolute;
  left: 20px;
  text-align: right;
  width: 20px;
  color: #5c6370;
  font-size: 14px;
  font-family: "Fira Code", monospace;
}


#printing-text {
  font-family: Arial, sans-serif;
  font-size: 24px;
  overflow: hidden;
  white-space: nowrap;
  border-right: 2px solid #000;
  animation: typing 2s steps(30) infinite;
}

@keyframes typing {
  from { width: 0; }
  to { width: 100%; }
}
</style>