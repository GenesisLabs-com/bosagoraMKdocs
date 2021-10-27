<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
<br/>
Returns Latest transactions of the ledger.
<br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/latest-transactions`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/latest-transactions`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/latest-transactions`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |


Example Response JSON:<br/>
[{"height":"0","tx_hash":"0x26866bb263593d024a92103646c48cf35a2b1bfcc49b087915b85db14a432b373569d56f576242354328a31bf0102a0a78cb806cf6e25d88d7981367833631b7","type":0,"amount":"4880000000000000","tx_fee":"0","tx_size":"368","time_stamp":1609459200,"full_count":2},{"height":"0","tx_hash":"0xeb5e0004d046422c84ddb7b9d54a0eba484a41b5179beda0b3dd7c54c3fca609437a9c8ef16b5bfc2335d9b258eb68908757e0f1a4c725752598aaa962924551","type":1,"amount":"120000000000000","tx_fee":"0","tx_size":"278","time_stamp":1609459200,"full_count":2}]