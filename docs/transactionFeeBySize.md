<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**

Returns transaction fee by size
<input class="md-input" placeholder="Enter size" id="size"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/transaction/fees/${document.getElementById("size").value || "250"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/transaction/fees/${document.getElementById("size").value || "250"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/transaction/fees/${document.getElementById("size").value || "250"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| fee         | transaction size | 250 |

Example Response JSON:<br/>
{"tx_size":250,"high":"192500","high_currency":0.006389,"high_delay":2,"medium":"175000","medium_currency":0.005808,"medium_delay":4,"low":"175000","low_currency":0.005808,"low_delay":13}