<script setup></script>
<style scoped>
.card {
  width: 320px;
  padding: 30px;
  /* background: #0f9c55; */
  background: #f15353;
  border: 8px solid #000;
  box-shadow: 15px 15px 0 #000;
  transform: rotate(-2deg);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}
.card:hover {
  transform: rotate(0deg) scale(1.02);
  box-shadow: 20px 20px 0 #000;
}

.banner {
  position: absolute;
  top: 3px;
  right: -95px;
  background: #000;
  color: #fff;
  padding: 15px;
  width: 350px;
  text-align: center;
  transform: rotate(45deg);
  font-weight: bold;
  font-size: 18px;
  letter-spacing: 2px;
  overflow: hidden;
  transition: background 0.5s ease;
}
.banner:hover {
  background: red;
}
.banner-text {
  display: inline-block;
  transition: opacity 0.5s ease, transform 0.5s ease;
  width: 100%;
  position: absolute;
  left: 13%;
  top: 50%;
  transform: translateY(-50%);
}
.banner-text-small {
  display: inline-block;
  transition: opacity 0.5s ease, transform 0.5s ease;
  width: 100%;
  position: absolute;
  left: 13%;
  top: 50%;
  transform: translateY(-50%);
  font-size: 10px;
  opacity: 0;
  transform: translateY(60%);
}
.banner:hover .banner-text:first-child {
  opacity: 0;
  transform: translateY(-100%);
}
.banner:hover .banner-text-small {
  opacity: 1;
  transform: translateY(-40%);
}

.card__title {
  font-size: 22px;
  font-weight: 700;
  color: #ffffff;
  text-transform: uppercase;
  margin-bottom: 10px;
  display: block;
  border-bottom: 2px solid #000000;
  width: 50%;
}
.card__subtitle {
  font-size: 18px;
  line-height: 1.4;
  color: #ffffff;
  margin-bottom: 20px;
  padding-bottom: 10px;
}

.card__form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.card__form input {
  padding: 12px;
  border: 6px solid #000000;
  font-size: 16px;
  font-family: "Proxima Nova", sans-serif;
  transition: all 0.3s ease;
  background-color: #fff;
  color: #000000;
}
.card__form input:focus {
  outline: none;
  transform: scale(1.05);
  box-shadow: 0 0 10px 3px rgb(246, 255, 0);
}

/* The sign-up button */
.sign-up {
  border: 4px solid #000;
  background: #000;
  color: #fff;
  padding: 12px;
  font-size: 18px;
  font-weight: bold;
  text-transform: uppercase;
  cursor: pointer;
  transition: all 0.3s ease;
}
.sign-up:hover {
  background: #fff;
  color: #000;
  transform: translateY(-5px);
  box-shadow: 0 5px 0 #000;
}
</style>

<template>
  <div class="card">
    <div class="banner">
      <span class="banner-text">JOIN US</span>
      <span class="banner-text-small">UPDATES & OFFERS</span>
    </div>
    <span class="card__title">See art...</span>
    <p class="card__subtitle">
      Join our email list to get exclusive updates and offers. No spam, we
      promise.
    </p>
    <div class="card__form">
      <input type="email" name="text" placeholder="Your Email" required />
      <button class="sign-up">Sign Up</button>
    </div>
  </div>
</template>
