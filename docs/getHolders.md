<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
Returns Latest transactions of the ledger.
<br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/holders`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/holders`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/holders`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
</br>
| Query String | Explanation    | Example   
</br>                         

Example Response JSON:<br/>
[{"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","tx_count":1,"total_received":4880000000000000,"total_sent":0,"total_reward":0,"total_frozen":0,"total_spendable":4880000000000000,"total_balance":4880000000000000,"percentage":0,"value":0,"full_count":7},{"address":"boa1xrval5rzmma29zh4aqgv3mvcarhwa0w8rgthy3l9vaj3fywf9894ycmjkm8","tx_count":1,"total_received":20000000000000,"total_sent":0,"total_reward":0,"total_frozen":20000000000000,"total_spendable":0,"total_balance":20000000000000,"percentage":0,"value":0,"full_count":7},{"address":"boa1xrval6hd8szdektyz69fnqjwqfejhu4rvrpwlahh9rhaazzpvs5g6lh34l5","tx_count":1,"total_received":20000000000000,"total_sent":0,"total_reward":0,"total_frozen":20000000000000,"total_spendable":0,"total_balance":20000000000000,"percentage":0,"value":0,"full_count":7},{"address":"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh","tx_count":1,"total_received":20000000000000,"total_sent":0,"total_reward":0,"total_frozen":20000000000000,"total_spendable":0,"total_balance":20000000000000,"percentage":0,"value":0,"full_count":7},{"address":"boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2","tx_count":1,"total_received":20000000000000,"total_sent":0,"total_reward":0,"total_frozen":20000000000000,"total_spendable":0,"total_balance":20000000000000,"percentage":0,"value":0,"full_count":7},{"address":"boa1xzval3ah8z7ewhuzx6mywveyr79f24w49rdypwgurhjkr8z2ke2mycftv9n","tx_count":1,"total_received":20000000000000,"total_sent":0,"total_reward":0,"total_frozen":20000000000000,"total_spendable":0,"total_balance":20000000000000,"percentage":0,"value":0,"full_count":7},{"address":"boa1xzval4nvru2ej9m0rptq7hatukkavemryvct4f8smyy3ky9ct5u0s8w6gfy","tx_count":1,"total_received":20000000000000,"total_sent":0,"total_reward":0,"total_frozen":20000000000000,"total_spendable":0,"total_balance":20000000000000,"percentage":0,"value":0,"full_count":7}]