<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Returns enrolled validators of block.
<input class="md-input" placeholder="Enter Height" id="height" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/block-enrollments?height=${document.getElementById("height").value || "0"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/block-enrollments?height=${document.getElementById("height").value || "0"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res[0])
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/block-enrollments?height=${document.getElementById("height").value || "0"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| height      | height of block | 0 |

Example Response JSON:<br/>
[{"height":"0","utxo":"0x210f6551d648a4da654da116b100e941e434e4f232b8579439c2ef64b04819bd2782eb3524c7a29c38c347cdf26006bccac54a58a58f103ae7eb5b252eb53b64","enroll_sig":"0x018389f5876ebac77ad4c2269415bf8a5b14e2374e9d30a933f70a10abbca2a40e0122b707d1a0b305efcbca42d73e884987396248c66d329bca486a39735f8c","commitment":"0xcfc5b09bc53136c1691e0991ffae7f2657bba248da07fb153ddf08a5109ce1c7d38206bfab6da57d70c428286d65081db992fbade6c67b97c62e9cb2862433e1","cycle_length":20,"full_count":1}]