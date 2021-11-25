<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**

Returns average transaction fee between range (date - filter)
<input class="md-input" placeholder="Enter Filter" id="filter" width="100"></input><br/>
<input class="md-input" placeholder="Enter Date" id="date"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/transaction/fees/250`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/transaction/fees/250`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res[0])
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/transaction/fees/250`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| date         | start date of the range of dates to look up | 1609459200 |
| filter   | Filter day to display fee chart. | D|

Example Response JSON:<br/>
{
    "height":0,"granularity":"D","time_stamp":1609459200,"average_tx_fee":0,"total_tx_fee":0,"total_payload_fee":0,"total_fee":0
}
