<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**

Returns average transaction fee between range (date - filter)
<input class="md-input" placeholder="Enter Filter" id="filter" width="100"></input><br/>
<input class="md-input" placeholder="Enter Date" id="date"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/average_fee_chart?filter=${document.getElementById("filter").value || "D"}&date=${document.getElementById("date").value || "1609459200"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/average_fee_chart?filter=${document.getElementById("filter").value || "D"}&date=${document.getElementById("date").value || "1609459200"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res[0])
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/average_fee_chart?filter=${document.getElementById("filter").value || "D"}&date=${document.getElementById("date").value || "1609459200"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| filter   | Filter day to display fee chart. | 1D, 5D, 1M, 3M, 6M, 1Y, 3Y, 5Y|
| date         | Start date of the range of dates to look up | 1609459200 |


Example Response JSON:<br/>
{
    "height":0,"granularity":"D","time_stamp":1609459200,"average_tx_fee":0,"total_tx_fee":0,"total_payload_fee":0,"total_fee":0
}
