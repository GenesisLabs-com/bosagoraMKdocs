<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
<br/>
Returns Missed Blocks.

<input class="md-input" placeholder="Enter Address" id="address"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/validator/missed-blocks/${document.getElementById("address").value ||"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/validator/missed-blocks/${document.getElementById("address").value ||"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`)
        .then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/validator/missed-blocks/${document.getElementById("address").value ||"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p><br/>
| Query String | Explanation    | Example                            |
| --------- | ------------ | ------------------------------------ |
| address      | block address | boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh |

Example Request JSON:<br/>
[{"block_height":4949,"signed":0},{"block_height":4948,"signed":0},{"block_height":4947,"signed":0},{"block_height":4946,"signed":0},{"block_height":4945,"signed":0},{"block_height":4944,"signed":0},{"block_height":4943,"signed":0},{"block_height":4942,"signed":0},{"block_height":4941,"signed":0},{"block_height":4940,"signed":0}]