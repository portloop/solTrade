<script lang="ts" setup>
import { WalletMultiButton, useWallet } from 'solana-wallets-vue'

const { publicKey } = useWallet()



</script>

<template>
 
          <ClientOnly v-if="!publicKey">
                <WalletMultiButton />
                <template #placeholder>
                    Loading
                </template>
          </ClientOnly>
          <!-- <div>
              <p v-if="publicKey">{{ publicKey }}</p>
              <p v-else>Please connect your wallet</p>
          </div> -->

          <div class="deal-buttons" v-if="publicKey">
            <button>Long</button>
            <button>Short</button>
          </div>
</template>


<style>
.swv-button-trigger {
    height: 40px !important;
    width: 100% !important;
}

@media screen and (max-width: 795px) {
    .swv-button-trigger {
        max-width: 160px;
        font-size: 12px;
    }

    .swv-button-trigger p {
        max-width: 100%;
        font-size: 12px;
    }
}

.deal-buttons {
    width: 100%;
    display: flex;
    flex-direction: column;
}

.deal-buttons button:first-child {
    background: #43cd73;
    height: 50px;
    width: 100%;
    border-radius: 6px;
    color: #fff;
    margin-bottom: 20px;
}

.deal-buttons button:last-child {
    background: #cd4f43;
    height: 50px;
    width: 100%;
    border-radius: 6px;
    color: #fff;
}
</style>