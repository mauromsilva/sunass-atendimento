<script setup>
import { useAttrs } from 'vue';
import { useMapGetter } from 'dashboard/composables/store';

import logoThumbnail from 'dashboard/assets/images/logo_thumbnail.svg';

const attrs = useAttrs();
const globalConfig = useMapGetter('globalConfig/get');
</script>

<template>
  <img
    v-if="globalConfig.logoThumbnail"
    v-bind="attrs"
    :src="globalConfig.logoThumbnail"
    :alt="attrs.alt || globalConfig.installationName || 'Sunrise Assistencial'"
  />
  <img
    v-else
    v-bind="attrs"
    :src="logoThumbnail"
    :alt="attrs.alt || 'Sunrise Assistencial'"
  />
</template>
