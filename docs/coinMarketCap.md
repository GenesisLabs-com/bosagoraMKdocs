<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**

Returns Coin market cap.
<br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/coinmarketcap`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/coinmarketcap`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/coinmarketcap`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |



Example Response JSON:<br/>
{
    "last_updated_at": 1631852818,
    "price": "0.111752",
    "market_cap": 33896716,
    "vol_24h": 1469319,
    "change_24h": 2
}