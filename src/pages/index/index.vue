<template>
  <view class="index">
    <view>
      <button id="show-modal" @tap="tapOpenModal">Show Modal</button>
      <teleport to="#teleportId" v-if="showModal">
        <modal :show="showModal" @close="showModal = false">
          <template #header>
            <view>custom header</view>
          </template>
        </modal>
      </teleport>
    </view>
  </view>
  <view id="teleportId" class="teleportId"></view>
</template>

<script setup>
import './index.scss'
import Modal from './Modal.vue'
import { ref } from 'vue'
console.log('setup run.');

const showModal = ref(false)
function tapOpenModal() {
  showModal.value = true
}

</script>
