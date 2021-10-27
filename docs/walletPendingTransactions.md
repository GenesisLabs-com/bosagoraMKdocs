<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
<br/>
Returns List the total by output address of the pending transaction.
<input class="md-input" placeholder="Enter Address" id="address" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/wallet/transactions/pending/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}`
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
| address   | The input address of the pending transaction | boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67 |


Example Response JSON:<br/>
{
address: "boa1xp5mw96emyjwsd29xfd90ern548nr95raft88p3xr6ngw8ncl8xm5y6ynas"
amount: "10000000"
block_delay: 0
fee: "161700"
peer_count: 1
submission_time: 1631883958
tx_hash: "0xb5246d3865ac18a6ada62d2863184c1d4398726dc98448094bb8f93e44239187abba558bcdc41c045699499bbd32e3c2b2e48e3e869eaecd15bf51213e953034"
}