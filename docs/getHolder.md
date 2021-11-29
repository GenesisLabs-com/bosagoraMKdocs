<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**

Returns BOA Holder of the ledger.
<input class="md-input" placeholder="Enter address" id="address" width="100"></input><br/>
<input class="md-input" placeholder="Enter currency" id="currency" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/holder${document.getElementById("address").value || "boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}?currency=${document.getElementById("currency").value || "usd"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/holder/${document.getElementById("address").value || "boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}?currency=${document.getElementById("currency").value || "usd"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/holder/${document.getElementById("address").value || "boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}?currency=${document.getElementById("currency").value || "usd"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| address      | Address of the holder | boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh |


Example Response JSON:<br/>

{"address":"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh","tx_count":19,"total_received":59260445590993,"total_sent":0,"total_reward":2950921944848,"total_frozen":20000000000000,"total_spendable":0,"total_balance":59260445590993,"percentage":"1.1673","value":2173850925.614396}