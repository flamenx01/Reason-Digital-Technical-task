<template>
  <div>
    <div class="header_main container">
      <div class="header_branding">
        <router-link class="header_branding__logo" aria-label="Homepage" to="/">
          <img src="https://www.goodthingsfoundation.org/wp-content/uploads/2021/01/good-things-foundation-logo.png" alt="Branding Logo">
        </router-link >
      </div>
      <nav class="header-nav nav-menu">
        <ul>
          <li v-for="(item, index) in store.menuItems" :key="index">
            <router-link :to="item.url">{{item.title}}</router-link>
          </li>
        </ul>
      </nav>
      <button @click="showMenu = !showMenu" class="nav-button btn btn--alt-2">Menu</button>
    </div>
    <nav v-if="showMenu" class="mobile-nav nav-menu container">
      <ul>
        <li v-for="(item, index) in store.menuItems" :key="index">
          <router-link :to="item.url">{{item.title}}</router-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script setup>
import { useThemeStore } from '@/stores/store';
import { ref } from "vue"
const store = useThemeStore();
if (!store.menuItems.length) store.getMenu();

const showMenu = ref(false);
</script>

<style lang="scss" scoped>
.header_main {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid #ccc;
  min-height: 5.75rem;
  .header_branding {
    &__logo {
      display: block;
      height: 3rem;
      img {
        height: 100%;
        width: auto;
        margin-right: 1rem;
        object-fit: contain;
      }
    }
  }
  .header-nav {
    display: flex;
    ul {
      li {
        padding: 2rem 0.625rem;
        a {
          text-decoration: none;
        }
      }
    }
  }
  .nav-button {
    display: none;
  }
  @media (max-width: 70rem) {
    .nav-button {
      display: block;
    }
    .header-nav {
      display: none;
    }
    .mobile-nav {
      display: flex;
    }
  }
}
.nav-menu {
    ul {
    display: flex;
    list-style: none;
    margin-left: 0;
    margin-top: 0;
    li {
      margin-left: 0;
      margin-top: 0;
            a {
        font-size: 1.1rem;
        font-weight: 500;
        color: $dark-text;
        &:visited {
          color: $dark-text;
        }
        &:hover {
          color: $main-color;
        }
      }
    }
  }
}
.mobile-nav {
  display: none;
  ul {
    flex-direction: column;
    li {
      list-style: none;
      padding: 1rem 0.625rem;
    }
  }
  @media (max-width: 70rem) {
    display: flex;
  }
}
</style>
