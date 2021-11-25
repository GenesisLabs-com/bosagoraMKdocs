<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
<br/>
Returns a set of transactions history of the addresses.

<input class="md-input" placeholder="Enter Address" id="address" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/wallet/blocks/header?height=1`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/wallet/blocks/header?height=1`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/wallet/blocks/header?height=1`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>


| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |
| address   | address to query. | boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67|

Example Response JSON:<br/>
{"height":"1","hash":"0x4e91f7276dec449f423b629727a7b430898c53c79f8d5f97d014941492f1229db5042c4cdc943c9f05d2c821966a0993860a8c9449a9f6dc96411ffae7ed34f9","merkle_root":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000","time_stamp":1637738673}