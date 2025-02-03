<template>
  <div class="container">
    <h1>
      <span class="text-white text-xl md:text-2xl lg:text-4xl font-bold">
        Beautiful
      </span>
      <br />
      <span
        class="typed-text text-xl md:text-2xl lg:text-4xl font-bold underline"
        >{{ typeValue }}</span
      >
      <span
        class="cursor h-[1.75em] md:h-[2em] lg:h-[2.5em]"
        :class="{ typing: typeStatus }"
        >&nbsp;</span
      >
    </h1>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      typeValue: "",
      typeStatus: false,
      typeArray: ["Art.", "Masterpieces.", "Creations.", "Expressions."],
      typingSpeed: 125,
      erasingSpeed: 75,
      newTextDelay: 1500,
      typeArrayIndex: 0,
      charIndex: 0,
    };
  },
  methods: {
    typeText() {
      if (this.charIndex < this.typeArray[this.typeArrayIndex].length) {
        if (!this.typeStatus) this.typeStatus = true;

        this.typeValue += this.typeArray[this.typeArrayIndex].charAt(
          this.charIndex
        );
        this.charIndex += 1;

        setTimeout(this.typeText, this.typingSpeed);
      } else {
        this.typeStatus = false;
        setTimeout(this.eraseText, this.newTextDelay);
      }
    },
    eraseText() {
      if (this.charIndex > 0) {
        if (!this.typeStatus) this.typeStatus = true;

        this.typeValue = this.typeArray[this.typeArrayIndex].substring(
          0,
          this.charIndex - 1
        );
        this.charIndex -= 1;
        setTimeout(this.eraseText, this.erasingSpeed);
      } else {
        this.typeStatus = false;
        this.typeArrayIndex += 1;
        if (this.typeArrayIndex >= this.typeArray.length)
          this.typeArrayIndex = 0;

        setTimeout(this.typeText, this.typingSpeed + 1000);
      }
    },
  },
  created() {
    setTimeout(this.typeText, this.newTextDelay + 200);
  },
};
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  display: flex;
  justify-content: start;
  align-items: center;
}

h1 {
  font-weight: normal;

  span.typed-text {
    color: #00ff33;
  }

  span.cursor {
    display: inline-block;
    margin-left: 0.1em;
    width: 0.2em;
    background-color: #fff;
    animation: cursorBlink 1s infinite;
    vertical-align: bottom;
  }

  span.cursor.typing {
    animation: none;
  }
}

.white {
  color: white;
}

@keyframes cursorBlink {
  49% {
    background-color: #fff;
  }
  50% {
    background-color: transparent;
  }
  99% {
    background-color: transparent;
  }
}
</style>
