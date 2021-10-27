<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**

Returns a transaction status.
<input class="md-input" placeholder="Enter Hash" id="hash"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/transaction/status/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/transaction/status/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/transaction/status/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| hash      | hash of the transaction | 0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7 |

Example Response JSON:<br/>
{"status":"confirmed","tx_hash":"0x26866bb263593d024a92103646c48cf35a2b1bfcc49b087915b85db14a432b373569d56f576242354328a31bf0102a0a78cb806cf6e25d88d7981367833631b7","block":{"height":0,"hash":"0xe8dbdeb515cf835f515355045ec1af6cb141f9690fb85b01294fe1985e84a37bd78f0100af5e1847a881d04da033e1a84c903f81bd05e52cadc534518f4011ff"}}