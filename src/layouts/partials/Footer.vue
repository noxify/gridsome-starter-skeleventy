<template>
  <div class="footer-wrapper">
    <footer id="footer" class="footer bg-gray-200" role="contentinfo">
      <div class="footer-inner container m-auto md:flex justify-between items-center px-6 py-10">
        <p class="text-purple-900 pb-8 md:pb-0">
          © 2019 Skeleventy: A starter template built with
          <a
            href="https://www.gridsome.org"
          >Gridsome.</a> - Template powered by
          <a href="https://github.com/josephdyer" target="_blank">Joseph Dyer</a>
        </p>

        <ul class="flex justify-center">
          <li class="mr-4" v-for="element in $static.metadata.social" :key="element.link">
            <a
              :href="element.link"
              class="block text-gray-500 hover:text-pink-500"
              :aria-label="element.icon"
              target="_blank"
            >
              <svg
                class="block"
                fill="currentColor"
                role="img"
                aria-hidden="true"
                width="18"
                height="18"
              >
                <use
                  xmlns:xlink="http://www.w3.org/1999/xlink"
                  :xlink:href="socialIcon(element)"
                />
              </svg>
            </a>
          </li>
        </ul>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  methods: {
    socialIcon(element) {
      return `/icons.svg#icon-${element.icon}`
    }
  }
}
</script>

<static-query>
query {
  metadata {
    social {
      icon
      link
    }
  }
}
</static-query>