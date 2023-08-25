<template>
    <div>
        <button @click="connect">Connect Ronin</button>
    </div>
</template>
<script>

import { WalletSDK } from '@roninnetwork/wallet-sdk'
import { WalletConnectModal } from '@walletconnect/modal'

export default {
    name: "test",

    methods: {

        async connect() {

            const sdk = new WalletSDK()
            await sdk.connectInjected()

            if (!this.checkRoninInstalled()) {
                return
            }

            const accounts = await sdk.requestAccounts()
            if (accounts) {
                console.log('Accounts')
            } else {
                console.log('No Accounts')
            }
        },

        checkRoninInstalled() {
            if ('ronin' in window) {
                return true
            }
            window.open('https://wallet.roninchain.com', '_blank')
            return false
        }
    }
}
</script>

<style scoped>
button {
    margin: 20px;
}
</style>