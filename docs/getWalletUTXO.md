<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
<br/>
Returns a set of UTXOs of the address
<br/>
<input class="md-input" placeholder="Enter Address" id="address" width="100"></input><br/>
<input class="md-input" placeholder="Enter Amount" id="amount"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/wallet/utxo/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}?amount=${document.getElementById("amount").value || 50}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/wallet/utxo/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}?amount=${document.getElementById("amount").value || 50}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/wallet/utxo/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}?amount=${document.getElementById("amount").value || 50}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |
| address   | The public address to receive UTXO  | boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2 |
| amount    | Amount Required | 50 |

Example Response JSON:<br/>
[{"utxo":"0x0a5b4685cc5b07f5ba378ce879f690320c4c7d2195644f0c04bdc13de7063d2ed68cfa2a36ca0d9d044a816326c9eac8d6f55dad4e977aef02530ebc10a0bd5e","type":0,"unlock_height":"7","amount":"7261904729229","height":"6","time":1637738696,"lock_type":0,"lock_bytes":"md+rscNMxR56h8elO/gUP2jLjLexx9ALiKlFkUP6QJw="}
]