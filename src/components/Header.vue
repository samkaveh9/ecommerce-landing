<template>
  <header class="header">
    <div class="header__shape">
      <div class="header__shape-inner"></div>
    </div>
    <div class="container">
      <div class="navbar">
        <div class="navbar__row">
          <div class="header__logo">
            <router-link :to="{ name: 'Home' }" class="header__logo-img"></router-link>
          </div>
          <div class="navbar__items" :class="{ 'navbar__items--is-active': showSideBar }">
            <ul class="navbar__ul">
              <li class="navbar__item">
                <a href="" class="navbar__link navbar__link--is-active"
                  >صفحه اصلی</a
                >
              </li>
              <li class="navbar__item navbar__item--has-sub">
                <a href="" class="navbar__link">فروشگاه</a>
                <ul class="navbar__subset">
                  <li class="navbar__item">
                    <a href="" class="navbar__link">زیر منو 1</a>
                  </li>
                  <li class="navbar__item">
                    <a href="" class="navbar__link">زیر منو 2</a>
                  </li>
                  <li class="navbar__item navbar__item--has-sub">
                    <a href="" class="navbar__link">زیر منو 3</a>
                    <ul class="navbar__subset">
                      <li class="navbar__item">
                        <a href="" class="navbar__link">زیر منو 1</a>
                      </li>
                      <li class="navbar__item">
                        <a href="" class="navbar__link">زیر منو 2</a>
                      </li>
                      <li class="navbar__item navbar__item--has-sub">
                        <a href="" class="navbar__link">زیر منو 3</a>
                        <ul class="navbar__subset">
                          <li class="navbar__item">
                            <a href="" class="navbar__link">زیر منو 1</a>
                          </li>
                          <li class="navbar__item">
                            <a href="" class="navbar__link">زیر منو 2</a>
                          </li>
                          <li class="navbar__item">
                            <a href="" class="navbar__link">زیر منو 3</a>
                          </li>
                        </ul>
                      </li>
                    </ul>
                  </li>
                </ul>
              </li>
              <li class="navbar__item">
                <a href="" class="navbar__link">درباره ما</a>
              </li>
              <li class="navbar__item">
                <a href="" class="navbar__link">تماس باما</a>
              </li>
            </ul>
          </div>
          <div class="navbar__action">
            <div class="header__basket">
              <span class="header__basket-icon" @click="showBasketDisplay"></span>
              <span class="header__basket-count">0</span>
              <div class="header__dropdown" :class="{ 'header__dropdown--is-active': isBasketDisplayed }">
                <div
                  class="
                    header__dropdown-content header__dropdown-content--overflow
                  "
                >
                  <div class="header__basket-item" v-for="item in 3" :key="item">
                    <a href="" class="header__basket-link">
                      <img :src="require('../assets/img/big-pic.jpg')" class="header__basket-img" />
                    </a>
                    <div class="header__basket-details">
                      <h5>
                        <a class="header__basket-title" href=""
                          >محصول شماره یک</a
                        >
                      </h5>
                      <div class="header__basket-price">120000 تومان</div>
                      <a href="" class="header__basket-remove">حذف</a>
                    </div>
                  </div>
                  <div class="header__basket-btn">
                    <a
                      href="cart.html"
                      class="btn btn--boxshadow btn--brand w--100"
                      >ثبت و نهایی کردن سفارش</a
                    >
                  </div>
                </div>
              </div>
            </div>
            <div class="header__account">
              <span class="header__account-icon" @click="showAccountDisplay"></span>
              <div class="header__dropdown header__dropdown--w200" :class="{ 'header__dropdown--is-active': isAccountDisplayed }">
                <div class="header__dropdown-content" >
                  <a href="sign-in.html" class="header__account-link">ورود</a>
                  <a href="sign-up.html" class="header__account-link"
                    >ثبت نام</a
                  >
                </div>
              </div>
            </div>
            <div class="header__menu" @click="toggleSideBar"></div>
          </div>
        </div>
      </div>
      <div class="header__top">
        <div class="header__top-content">
          <h1 class="header__top-h1">کیفیت شعار ماست</h1>
          <p class="header__top-p">تضمین بازگشت وجه در صورت نارضایتی مشتری</p>
        </div>
        <form class="header__form">
          <div class="header__search">
            <input
              type="text"
              class="header__serach-input"
              placeholder="جستجو کنید..."
            />
            <button
              class="header__search-btn btn btn--brand btn--boxshadow"
            ></button>
          </div>
        </form>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data: () => ({
    isBasketDisplayed: false,
    isAccountDisplayed: false,
    showSideBar: false
  }),

  methods: {
    showBasketDisplay() {
      this.isAccountDisplayed = false;
      this.isBasketDisplayed = !this.isBasketDisplayed;
    },

    showAccountDisplay() {
      this.isBasketDisplayed = false;
      this.isAccountDisplayed = !this.isAccountDisplayed;
    },

    eventListener(event) {
      if (!event.target.closest(".header__basket,.header__account")) {
        this.isAccountDisplayed = false;
        this.isBasketDisplayed = false;
      }
    },

     toggleSideBar(){
      this.showSideBar = !this.showSideBar
    }
  },

  mounted() {
    document.addEventListener("click", this.eventListener);
  },

  destroyed() {
    document.removeEventListener("click", this.eventListener);
  },
};
</script>