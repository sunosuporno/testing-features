<template>
  <button @click="handleClick">Connect Wallet</button>
   <span v-if="connectedChain">Connected Chain: {{connectedChain.id}}</span>
</template>

<script>
import { useOnboard } from '@web3-onboard/vue'
import web3Onboard from '../composables/web3Onboard'
import { ref, watch, watchEffect } from '@vue/runtime-core'
export default {

    setup(){
        const { wallets, connectWallet, disconnectConnectedWallet, connectedWallet, connectedChain } = useOnboard()
        const showChainName = ref(false)

        const handleClick = async () => {
           await connectWallet()
           console.log('connectedChain', connectedChain.value)
           showChainName.value = true
        }

        watch(connectedChain, async() => {
            if(connectedChain){
                console.log('connectedChain', connectedChain.value)  
            }
            console.log('connectedChain', connectedChain.value.namespace)
        })

        return {
            handleClick, connectedChain, connectedWallet, disconnectConnectedWallet, wallets, showChainName
        }
    }
// setup() {
// const MAINNET_RPC_URL = 'https://rpc.ankr.com/eth'

// const injected = injectedModule()

// const onboard = Onboard({
//   wallets: [injected],
//   chains: [
//     {
//       id: '0x1',
//       token: 'ETH',
//       label: 'Ethereum Mainnet',
//       rpcUrl: MAINNET_RPC_URL,
//     },
//     {
//       id: '0x89',
//       token: 'MATIC',
//       label: 'Matic Mainnet',
//       rpcUrl: 'https://matic-mainnet.chainstacklabs.com'
//     }
//   ],
//   appMetadata: {
//     name: 'My App',
//     icon: '../assets/logo.svg',
//     description: 'My app using Onboard'
//   }
// })


//     const handleClick = async () => {
//         const connectedWallets = await onboard.connectWallet()
//         console.log(connectedWallets)
//     }

//    const {connectedChain} = useOnboard()
//    const {connectedWallet} = useOnboard() 

//     return {
//         handleClick,
//         connectedChain,
//         connectedWallet
//         }
//     },
}
</script>

<style></style>
