<script lang="ts">
    import { PrivateKey } from "@bsv/sdk";

    let WIF:string;
    let address:string;


    function createKeys(){
        const privKey = PrivateKey.fromRandom();
        WIF = privKey.toWif();
        console.log("Private key WIF format is ", WIF);
        address = privKey.toAddress();
        console.log("Your bitcoin address is ", address);
    }
</script>

<section class=" m-4">
    <button class=" bg-black text-white p-2 rounded-md" on:click={createKeys}>Generate New Wallet Keys</button>
    <p>Private key WIF format is {WIF}</p>
    <p>Your bitcoin address is {address}</p>
</section>