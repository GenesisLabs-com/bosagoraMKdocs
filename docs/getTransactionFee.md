<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**

Returns transaction fees by the transaction size
<input class="md-input" placeholder="Enter tx size" id="size" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/transaction/fees/${document.getElementById("size").value || "0"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/transaction/fees/${document.getElementById("size").value || "0"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/transaction/fees/${document.getElementById("size").value || "0"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| tx_size      | Transaction Size | 0 |



Example Response JSON:<br/>
    {
        "tx_size":0,"high":"110000","medium":"100000","low":"100000"
    }