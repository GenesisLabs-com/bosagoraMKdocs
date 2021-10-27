<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**
Returns holder transaction history<br/>
<input class="md-input" placeholder="Enter Address" id="address" width="100"></input><br/>
<input class="md-input" placeholder="Enter Filter" id="filter"></input><br/>
<input class="md-input" placeholder="Enter date" id="date"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/holder_balance_history/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}?filter=${document.getElementById("filter").value || "D"}&date=${document.getElementById("date").value || "1609459200"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/holder_balance_history/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}?filter=${document.getElementById("filter").value || "D"}&date=${document.getElementById("date").value || "1609459200"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res[0])
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/holder_balance_history/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}?filter=${document.getElementById("filter").value || "D"}&date=${document.getElementById("date").value || "1609459200"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |
| address   | The address of BOA Holder| boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2|
| filter   | MFilter day to display fee chart.. | D|
| date   | End date for chart history The number on the page, this value begins with 1. | 1609459200|

Example Response JSON:<br/>
[{"address":"boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2","granularity":"D","time_stamp":1609459200,"balance":20000000000000,"block_height":0}]