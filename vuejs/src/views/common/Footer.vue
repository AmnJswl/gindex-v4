<template>
  <footer class="footer pb-5">
    
  </footer>
</template>
<script>
export default {
  props: {},
  data: function () {
    return {
      content: "",
      sitename: "",
      footerLogo: false,
      footerLogoLink: "",
    };
  },
  components: {},
  methods: {},
  computed: {
    siteTitle() {
      return window.gds.filter((item, index) => {
        return index == this.$route.params.id;
      })[0];
    },
  },
  beforeMount(){
    this.sitename = document.getElementsByTagName("title")[0].innerText;
  },
  mounted() {
    this.footerLogo = window.themeOptions.footer_data.footer_logo
    if(this.footerLogo){
      this.footerLogoLink = window.themeOptions.footer_data.footer_logo_link;
    } else {
      this.footerLogoLink = "";
    }
  },
};
</script>
