<script lang="ts" setup>
import { WalletMultiButton, useWallet } from 'solana-wallets-vue'



const { publicKey } = useWallet()

</script>

<template>
  <div class="min-h-screen bg-gray-200 flex flex-col items-center">
      
      <h1 class="font-bold text-primary text-2xl mt-24">Solana Wallet + Nuxt 3 + Tailwind CSS</h1>
      <h2 class="font-bold text-primary">with Anchor</h2>

      <div class="flex p-10 justify-between mt-8 w-1/2 mx-auto bg-white shadow-lg rounded-lg items-center">
          <ClientOnly>
                <WalletMultiButton />
                <template #placeholder>
                    Loading
                </template>
          </ClientOnly>
          <div>
              <p v-if="publicKey">{{ publicKey }}</p>
              <p v-else>Please connect your wallet</p>
          </div>
      </div>

  </div>
</template>