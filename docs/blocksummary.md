<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**


Returns a block overview
<input class="md-input" placeholder="Enter Height" id="height" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/block-summary?height=${document.getElementById("height").value || "0"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/block-summary?height=${document.getElementById("height").value || "0"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/block-summary?height=${document.getElementById("height").value || "0"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| height      | Height of block| 0 |

Example Response JSON:<br/>
[{"height":"0","total_transactions":2,"hash":"0xe8dbdeb515cf835f515355045ec1af6cb141f9690fb85b01294fe1985e84a37bd78f0100af5e1847a881d04da033e1a84c903f81bd05e52cadc534518f4011ff","prev_hash":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000","merkle_root":"0xaf402f71c175bc6f53ededdd9cfa1f4c074efcd2fe7090c9d0ca3b95c5d1e7513cd4b4f922c4f7ebf120958f449a2d3e23a397c7219e297b8ff1cfbc00ebc93d","signature":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000","random_seed":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000","time":1609459200,"version":"v0.x.x","total_sent":5000000000000000,"total_received":5000000000000000,"total_reward":0,"total_fee":0,"total_size":646}]