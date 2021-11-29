<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Return the block height corresponding to the block creation time
<input class="md-input" placeholder="Enter Time" id="time"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/block_height_at/${document.getElementById("time").value || "1638166596"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/block_height_at/${document.getElementById("time").value || "1638166596"}`).then((res) => {
            
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/block_height_at/${document.getElementById("time").value || "1638166596"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| time         | block creation time | 1638166596 |

Example Response JSON:<br/>
"37045"
