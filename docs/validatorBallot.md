<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**
Returns Ballot of the validator
<input class="md-input" placeholder="Enter Address" id="address" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/validator/ballot/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/validator/ballot/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/validator/ballot/${document.getElementById("address").value || "boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| address      | Address of the validator | boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2 |


Example Response JSON:<br/>
[{"proposal_id":"469008972006","tx_hash":"0x9ae101d4ff95c9e765145be22adec7fd0af2bc2302d4fcd65be0add852a8e6317a572cca4af247a2943e50c303e048dea380b1220e8011d59a807c80d27c4b20","sequence":106,"proposal_type":"Fund","proposal_title":"Title","ballot_answer":"Reject","full_count":1}]