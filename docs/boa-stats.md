<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**

Returns statistics of BOA coin.
</br>
<input class="md-input" placeholder="Enter currency" id="currency"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/boa-stats?currency=${document.getElementById("currency").value || "usd"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/boa-stats?currency=${document.getElementById("currency").value || "usd"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/boa-stats?currency=${document.getElementById("currency").value || "usd"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<h6>Result</h6>
<p id="showResult"></p>

| Query String | Explanation | Example |
| ------------ | ----------- | ------- |
| currency     | currency    | usd     |

Example Response JSON:<br/>
{"height":2994,"transactions":"3307","validators":6,"frozen_coin":"120000000000000","total_reward":"83127033588593","time_stamp":1638179868,"circulating_supply":5083127033588593,"active_validators":1,"price":161209848.932152}
