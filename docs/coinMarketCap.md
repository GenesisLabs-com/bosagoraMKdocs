<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Returns Coin market cap.
<br/>
<input class="md-input" placeholder="Enter currency" id="currency"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/coinmarketcap?currency=${document.getElementById("currency").value || "usd"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/coinmarketcap?currency=${document.getElementById("currency").value || "usd"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/coinmarketcap?currency=${document.getElementById("currency").value || "usd"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<h6>Result</h6>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| --------- | ------------ | ------------------------------------ |
| currency      | currency | usd |

Example Response JSON:<br/>
{"last_updated_at":1638179699,"currency":"usd","price":"0.317147","market_cap":96751716,"vol_24h":9241041,"change_24h":1}