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

        // const requestOptions = {
        //     method: 'GET',
        //     redirect: 'follow',
        //     mode: 'no-cors'
        // };

        // let response = await fetch("http://api-devnet.magiceden.dev/v2/wallets/EWmtsfBA8EikR3vvhsXgxn7cBQCUZfXJ7jMwXUpYRzXY/tokens?offset=0&limit=100&listStatus=listed", requestOptions);

        // if (response.ok) { // если HTTP-статус в диапазоне 200-299
        // // получаем тело ответа (см. про этот метод ниже)
        // response = await response.json();
        // console.log(response);
        // } else {
        // console.log("Ошибка HTTP: " + response.status);
        // }

        // fetch("http://api-devnet.magiceden.dev/v2/wallets/EWmtsfBA8EikR3vvhsXgxn7cBQCUZfXJ7jMwXUpYRzXY/tokens?offset=0&limit=100&listStatus=listed", requestOptions)
        //     // .then((response) => response.text())
        //     // .then((text) => console.log(text));
        //     .then((response) => console.log(response))
        //     .then((text) => console.log(text));  
        

        // fetch("http://api-devnet.magiceden.dev/v2/wallets/EWmtsfBA8EikR3vvhsXgxn7cBQCUZfXJ7jMwXUpYRzXY/tokens?offset=0&limit=100&listStatus=listed", requestOptions)
        //     .then(response => response.text())
        //     .then(result => console.log(`Done: ${result}`))
        //     .catch(error => console.log('error', error));

        // const response = await fetch('https://public-api.solscan.io/account/tokens?account=5DNLQ7j5gXZHDBEiX1uNUJEmxF9qzBSv2r4ztCEMpx4A', {method: 'GET'});
        // console.log('Fetching...');
        // const data = await response.json();
        // console.log(response);
        // console.log(`Done: ${data[0]}`);

        console.log('Fetching...');
        fetch('http://api-mainnet.magiceden.dev/v2/wallets/5DNLQ7j5gXZHDBEiX1uNUJEmxF9qzBSv2r4ztCEMpx4A/tokens', {method: 'GET', redirect: 'follow'})
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


        // const res = await fetch('http://api-mainnet.magiceden.dev/v2/wallets/5DNLQ7j5gXZHDBEiX1uNUJEmxF9qzBSv2r4ztCEMpx4A/tokens', {method: 'GET', redirect: 'follow', mode: 'no-cors'});
        // const data = await res.text();
        // console.log(res);
        // console.log({ body: data });
        // return { body: data };
    }
        
        // fetch(`http://api-mainnet.magiceden.dev/v2/wallets/5DNLQ7j5gXZHDBEiX1uNUJEmxF9qzBSv2r4ztCEMpx4A/tokens`, {method: 'GET', redirect: 'follow', mode: 'no-cors'})
        //     .then(response => response.text())
        //     .then(result => console.log(result))
        //     .catch(error => console.log('error', error));
        
        // fetch(`http://api-mainnet.magiceden.dev/v2/wallets/5DNLQ7j5gXZHDBEiX1uNUJEmxF9qzBSv2r4ztCEMpx4A/tokens`, {method: 'GET', redirect: 'follow', mode: 'no-cors'})
        //     .then((response) => {
        //         if (!response.ok) {
        //         throw new Error(`HTTP error! Status: ${ response.status }`);
        //         }

        //         return response.text();
        //     })
        //     .then((response) => {
        //         console.log(response);
        //     });
        // }

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