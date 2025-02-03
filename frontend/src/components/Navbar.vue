<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";
const scrolledNav = ref(null);
const mobile = ref(null);
const mobileNav = ref(null);
const windowWidth = ref(null);

const toggleMobileNav = () => {
  mobileNav.value = !mobileNav.value;
};

const checkScreen = () => {
  windowWidth.value = window.innerWidth;
  if (windowWidth.value <= 750) {
    mobile.value = true;
  } else {
    mobile.value = false;
    mobileNav.value = false;
  }
};

const updateScroll = () => {
  const scrollPosition = window.scrollY;
  if (scrollPosition > 50) {
    scrolledNav.value = true;
  } else {
    scrolledNav.value = false;
  }
};

onMounted(() => {
  window.addEventListener("resize", checkScreen);
  window.addEventListener("scroll", updateScroll);
  checkScreen();
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", checkScreen);
  window.removeEventListener("scroll", updateScroll);
});
</script>

<template>
  <header
    :class="[
      'bg-[#0f052d] bg-opacity-90 z-[99] w-full fixed transition-all duration-500 ease-in-out text-white',
      { 'scrolled-nav': scrolledNav },
    ]"
  >
    <nav
      class="flex flex-row py-[2px] px-0 transition-all duration-500 ease-in-out w-[90%] mx-auto my-0 relative align-baseline"
    >
      <div class="branding">
        <p class="hidden font-bold text-2xl sm:block">
          The Art Shop
        </p>
      </div>
      <ul v-show="!mobile" class="navigation">
        <li>
          <router-link :to="{ name: 'Home' }" class="link">Home</router-link>
        </li>
        <li>
          <router-link :to="{ name: 'Shop' }" class="link">Shop</router-link>
        </li>
      </ul>
      <div class="icon">
        <i
          class="far fa-bars"
          v-show="mobile"
          @click="toggleMobileNav"
          :class="{ 'icon-active': mobileNav }"
        ></i>
      </div>
      <transition name="mobile-nav">
        <ul v-show="mobileNav" class="dropdown-nav">
          <li>
            <router-link :to="{ name: 'Home' }" class="link">Home</router-link>
          </li>
          <li>
            <router-link :to="{ name: 'Shop' }" class="link">Shop</router-link>
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
nav {
  ul,
  .link {
    font-weight: 500;
    color: #fff;
    list-style: none;
    text-decoration: none;
  }

  li {
    text-transform: uppercase;
    padding: 14px;
    margin-left: 16px;
  }

  .link {
    font-size: 14px;
    transition: 0.5s ease all;
    padding-bottom: 4px;
    border-bottom: 1px solid transparent;

    &:hover {
      color: #00afea;
      border-color: #00afea;
    }
  }

  .branding {
    display: flex;
    align-items: center;

    img {
      width: 50px;
      transition: 0.5s ease all;
    }
  }

  .navigation {
    display: flex;
    flex: 1;
    justify-content: right;
    align-items: center;
  }

  .icon {
    display: flex;
    position: absolute;
    top: 0;
    align-items: center;
    right: 24px;
    height: 100%;

    i {
      cursor: pointer;
      font-size: 24px;
      transition: 0.8s ease all;
    }
  }

  .icon-active {
    transform: rotate(180deg);
  }

  .dropdown-nav {
    display: flex;
    flex-direction: column;
    position: fixed;
    width: 100%;
    max-width: 250px;
    height: 100%;
    background-color: white;
    top: 0;
    left: 0;

    li {
      margin-left: 0;
      .link {
        color: black;
      }
    }
  }

  .mobile-nav-enter-active,
  .mobile-nav-leave-active {
    transition: 1s ease all;
  }

  .mobile-nav-enter-from,
  .mobile-nav-leave-to {
    transform: translateX(-250px);
  }

  .mobile-nav-enter-to {
    transform: translateX(0);
  }
}

.scrolledNav {
  background-color: black;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.06),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);

  nav {
    padding: 8px 0;

    .branding {
      img {
        width: 40px;
        box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.06),
          0 2px 4px -1px rgba(0, 0, 0, 0.06);
      }
    }
  }
}
</style>
