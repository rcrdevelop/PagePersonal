<template>
<div class="flex flex-center">
    <div class="row justify-center text-h3 text-white  fit">
            CONTACT
        </div>
  <div class="row items-center  animation-page-contact rounded-borders container q-mt-md">
      <div class="q-pa-md bg-white full-width shadow-2" v-for="item in list" :key="item.label">
        <q-input readonly bg-color="white"  class="fit" input-class='info-text' :label="item.label">
        <template v-slot:prepend>
          <q-icon :name="item.icon" :color="item.color" />
        </template>
        <template v-slot:append>
          <q-btn @Click="copy(item.label)" flat label="COPY" />
        </template>
      </q-input>
          
      </div>
  </div>
  </div>
</template>

<style>
.container{
    height: 80vh;
    margin: auto auto;
}
@media screen and (max-width: 600px) {
    .info-text{
        font-size: 4vw;
    }
    .info-icon{
        font-size: 6vw;
    }
}
@media screen and (min-width: 600px) {
    .info-text{
        font-size: 1vw;
    }
    .info-icon{
        font-size: 3vw;
    }
    .container{
        width: 40vw;
    }
}
.animation-page-contact{
    height: 80vh;
    animation: slide-bottom 1.8s linear;
    -webkit-animation: slide-bottom 1.8s linear;
    position: absolute;
    top: 20%;
}
@keyframes slide-bottom {
    from{
        top: 100%; 
        opacity: 0;
    }
    to{
        top: 20%;
        opacity: 1;
    }
}
</style>
<script>
import { useQuasar } from "quasar";
export default {
    setup(){
        const $q = useQuasar()
        return{
            list:[
                {
                    label: '+584164155266',
                    icon: 'phone',
                    color: 'grey-8'
                },
                {
                    label: 'contreras06rj@gmail.com',
                    icon: 'mail',
                    color: 'orange-10'
                },
                {
                    label: 'RCR#8658',
                    icon: 'discord',
                    color: 'blue-7'
                }
            ],
            copy(text){
                window.Clipboard = (function(window, document, navigator) {
   var textArea,
      copy;

   function isOS() {
      return navigator.userAgent.match(/ipad|iphone/i);
   }

   function createTextArea(text) {
      textArea = document.createElement('textArea');
      textArea.value = text;
      document.body.appendChild(textArea);
   }

   function selectText() {
      var range,
         selection;

      if (isOS()) {
         range = document.createRange();
         range.selectNodeContents(textArea);
         selection = window.getSelection();
         selection.removeAllRanges();
         selection.addRange(range);
         textArea.setSelectionRange(0, 999999);
      } else {
         textArea.select();
      }
   }

   function copyToClipboard() {
      document.execCommand('copy');
      document.body.removeChild(textArea);
   }

   copy = function(text) {
      createTextArea(text);
      selectText();
      copyToClipboard();
   };

   return {
      copy: copy
   };
})(window, document, navigator);

// How to use
Clipboard.copy(text);
                $q.notify({
                    message: 'information copied to clipboard',
                    color: 'info'
                    })
            }
        }
    }
}
</script>
