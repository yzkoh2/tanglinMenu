<template>
  <div class="app-container">
    <div class="container-fluid overlay">
      <div class="custom-shape-divider-top-1745957112">
        <svg
          data-name="Layer 1"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 1200 120"
          preserveAspectRatio="none"
        >
          <path
            d="M985.66,92.83C906.67,72,823.78,31,743.84,14.19c-82.26-17.34-168.06-16.33-250.45.39-57.84,11.73-114,31.07-172,41.86A600.21,600.21,0,0,1,0,27.35V120H1200V95.8C1132.19,118.92,1055.71,111.31,985.66,92.83Z"
            class="shape-fill"
          ></path>
        </svg>
      </div>
    </div>

    <tanglinLogo />

    <div class="container">
      <tanglinHeader />

      <tigerLogo />
    </div>

    <buttonContainer :buttons="customButtons" @button-click="handleButtonClick" />

    <brandIcons />
  </div>

</template>

<script setup>
// Imports
import { RouterLink, RouterView } from 'vue-router'
import tanglinLogo from './components/tanglinLogo.vue'
import tanglinHeader from './components/tanglinHeader.vue'
import tigerLogo from './components/tigerLogo.vue'
import buttonContainer from './components/buttonContainer.vue'
import brandIcons from './components/brandIcons.vue'

// Buttons Info
const customButtons = [
  {
    text: 'START YOUR TASTING ADVENTURE',
    disabled: false,
    action: 'tasting',
  },
  {
    text: 'TAKE US HOME',
    disabled: false,
    action: 'home',
    url: "https://tanglin-gin.com/shop/",
  },
  {
    text: 'HOST YOUR NEXT ADVENTURE',
    disabled: false,
    action: 'host',
    url: "https://tanglin-gin.com/private-events/",
  },
  {
    text: 'WATCH THIS SPACE... (AND BRING A GLASS)',
    disabled: true,
    action: 'watch',
  },
]

// Buttons logic
const handleButtonClick = (action) => {
  console.log(`Button clicked with action: ${action}`)

  const clickedButton = customButtons.find(button => button.action === action)

  if (clickedButton && clickedButton.url && !clickedButton.disabled) {
    window.open(clickedButton.url, '_blank')
  }
}
</script>

<style scoped></style>
