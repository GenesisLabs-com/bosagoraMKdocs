<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
<br/>
Returns a set of Validators based on the block height if there is a height.
If height was not provided the latest validator set is returned.
If an address was provided, return the validator data of the address if it exists

<input class="md-input" placeholder="Enter Address" id="address" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/validator/${document.getElementById("address").value || "boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/validator/${document.getElementById("address").value || "boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res[0])
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/validator/${document.getElementById("address").value || "boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |
| address   | validator address  | boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh|

Example Response JSON:<br/>
[{"address":"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh","enrolled_at":"0","stake":"0x210f6551d648a4da654da116b100e941e434e4f232b8579439c2ef64b04819bd2782eb3524c7a29c38c347cdf26006bccac54a58a58f103ae7eb5b252eb53b64","preimage":{"height":"","hash":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"}}]