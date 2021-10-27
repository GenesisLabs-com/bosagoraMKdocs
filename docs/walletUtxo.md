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
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/wallet/utxo/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}?amount=${document.getElementById("amount").value || 50}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/wallet/utxo/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}?amount=${document.getElementById("amount").value || 50}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res[0])
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/wallet/utxo/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}?amount=${document.getElementById("amount").value || 50}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |
| address   | The public address to receive UTXO  | boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67 |
| amount    | Amount Required | 50 |

Example Response JSON:<br/>
{
    "utxo":"0x1791b08829791b6ba128e65ee7091c1f53abffd0750f587da8da05ddb9bf892adce542e27e65c3a1c5fd1bbc42736ce1cfc4b9f90e9b33418ab3af8b7c0a10db","type":0,"unlock_height":"1","amount":"610000000000000","height":"0","time":1609459200,"lock_type":0,"lock_bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="
}