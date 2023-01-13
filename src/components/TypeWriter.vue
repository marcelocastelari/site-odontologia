<template>
    <div class="flex flex-row-reverse ml-96 mr-24">
      <h1 class="">Transformando sorrisos
        <span class="">{{ typeValue }}</span>
        <span class="cursor" :class="{'typing': typeStatus}">&nbsp;</span>
      </h1>
    </div>
  </template>
  
  <script>
  
  
  export default {
      data: () => {
        return {
          typeValue: '',
          typeStatus: false,
          typeArray: ['para uma vida mais feliz'],
          typingSpeed: 100,
          erasingSpeed: 100,
          newTextDelay: 2000,
          typeArrayIndex: 0,
          charIndex: 0
        }
      },
      methods: {
        typeText() {
          if(this.charIndex < this.typeArray[this.typeArrayIndex].length) {
            if(!this.typeStatus)
              this.typeStatus = true;
            this.typeValue += this.typeArray[this.typeArrayIndex].charAt(this.charIndex);
            this.charIndex += 1;
            setTimeout(this.typeText, this.typingSpeed);
          }
          else {
            this.typeStatus = false;
            setTimeout(this.eraseText, this.newTextDelay);
          }
        },
        eraseText() {
          if(this.charIndex > 0) {
            if(!this.typeStatus)
              this.typeStatus = true;
            this.typeValue = this.typeArray[this.typeArrayIndex].substring(0, this.charIndex - 1);
            this.charIndex -= 1;
            setTimeout(this.eraseText, this.erasingSpeed);
          }
          else {
            this.typeStatus = false;
            this.typeArrayIndex += 1;
            if(this.typeArrayIndex >= this.typeArray.length)
              this.typeArrayIndex = 0;
            setTimeout(this.typeText, this.typingSpeed + 1000);
          }
        }
      },
      created() {
        setTimeout(this.typeText, this.newTextDelay + 200);
      }
    }
  </script>
  
  <style lang="scss" scoped>
      span.cursor {
        display: inline-block;
        margin-left: 3px;
        width: 6px;
        background-color: #eead2d;
        animation: cursorBlink 1s infinite;
      }
      span.cursor.typing {
        animation: none;
      }
    
    @keyframes cursorBlink {
      49% { background-color: #eead2d; }
      50% { background-color: transparent; }
      99% { background-color: transparent; }
    }
  </style>