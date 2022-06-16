<style>
    input {
        width: 1000px;
        border: 0;
        font-size: 32px;
    }
    button {
        background-color: aquamarine;
        border: none;
        font-size: 32px;
        width: 200px;
    }
    button:hover {
        background-color: aqua;
    }
    button:active {
        background-color: rgb(0, 153, 255);
    }
</style>


<script>

    async function get_nfts() {
       
        console.log('Starting fetching tokens...');

        const requestOptions = {
            method: 'GET',
            redirect: 'follow', 
            mode: 'no-cors'
        };

        console.log('Fetching...');
        fetch('https://api-mainnet.magiceden.dev/v2/wallets/5DNLQ7j5gXZHDBEiX1uNUJEmxF9qzBSv2r4ztCEMpx4A/tokens', requestOptions)
            .then((response) => {
                return response.text();
            })
            .then((data) => {
                console.log(data);
            });

        // console.log('Fetching...');
        // fetch('https://public-api.solscan.io/account/tokens?account=5DNLQ7j5gXZHDBEiX1uNUJEmxF9qzBSv2r4ztCEMpx4A')
        //     .then((response) => {
        //         return response.json();
        //     })
        //     .then((data) => {
        //         console.log(data);
        //     });

    }

    let wallet_ok = false;
    let wallet = "";
 
</script>


<h1>Enter solana wallet adress:</h1>
<input
    maxlength="44"
    bind:value={wallet}
>
<button on:click={get_nfts}>Show NFTs</button>

{#if wallet_ok}
<p>Wallet: {wallet}</p>
{/if}