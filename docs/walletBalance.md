<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
Returns the balance of the address

<br/>
<input class="md-input" placeholder="Enter Address" id="address" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/wallet/balance/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/wallet/balance/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/wallet/balance/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |
| address   | BoaHolder Address | boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67 |

Example Response JSON:<br/>
{
    "address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","balance":"4258998191010910","spendable":"4258998191010910","frozen":"0","locked":"0"
}