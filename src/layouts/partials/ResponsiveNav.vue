<template>
  <div>
    <nav
      id="mobile-nav"
      class="mobile-nav fixed left-0 top-0 h-screen w-full overflow-y-auto pt-12 bg-purple-900 z-50 md:hidden"
    >
      <ul>
        <li
          class="level-1 mb-4 md:mr-4 md:mb-0"
          v-for="element in $static.metadata.menu"
          :key="element.name"
        >
          <g-link
            :to="element.link"
            class="link block py-2 px-5 text-white text-3xl hover:text-pink-500"
            active-class="is-active-link"
            exact-active-class="active text-pink-500"
          >{{ element.name }}</g-link>
        </li>
      </ul>
    </nav>

    <button
      id="mobile-nav-toggle"
      class="mobile-nav-toggle block fixed h-16 w-full bottom-0 flex items-center justify-center font-bold border-none bg-purple-900 text-white z-50 focus:outline-none md:hidden"
      aria-expanded="false"
      aria-controls="mobile-nav"
    >
      <span class="mobile-nav-label mr-2 font-medium">Menu</span>

      <span class="mobile-nav-icon" aria-hidden="true">
        <span class="mobile-nav-icon-line bg-white w-6 block transition mb-1"></span>
        <span class="mobile-nav-icon-line bg-white w-6 block transition mb-1"></span>
        <span class="mobile-nav-icon-line bg-white w-6 block transition"></span>
      </span>
    </button>
  </div>
</template>

<static-query>
query {
  metadata {
    menu {
      name
      link
    }
  }
}
</static-query>

<script>

export default {

  mounted() {
    require('@modules/mobile-nav');
  }

}
</script>