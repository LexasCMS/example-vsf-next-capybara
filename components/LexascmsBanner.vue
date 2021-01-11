<template>
  <div id="example-app-banner">
    <span>
      This is an e-commerce store example built with
      <a href="https://www.lexascms.com/vue-storefront/" target="_blank">LexasCMS</a> and
      <a href="https://www.vuestorefront.io/" target="_blank">Vue Storefront Next</a> -
      <a href="https://github.com/lexascms/example-vsf-next-capybara/" target="_blank">View source code</a>
    </span>
  </div>
</template>

<style lang="scss" scoped>
#example-app-banner {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #1a202c;
  color: #e2e8f0;
  font-size: 14px;
  padding: 14px 16px;

  a {
    color: inherit;
    text-decoration: underline;
  }
}
</style>
