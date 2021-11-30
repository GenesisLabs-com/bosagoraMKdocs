<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**
<br/>
<br/>
Returns Ballot of the validator
<input class="md-input" placeholder="Enter Address" id="address"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/validator/ballot/${document.getElementById("address").value ||"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/validator/ballot/${document.getElementById("address").value ||"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/validator/ballot/${document.getElementById("address").value ||"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<h6>Result</h6>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| address      | Address of the validator | boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2 |

Example Response JSON:<br/>

{
        "proposal_id": "469008972006",
        "tx_hash": "0x2fe87cd6f3012563efce675b4860fb585f54f5aac4482bd7fbaf4d690441dd10913da3af4a79ccc2ae5840607053d960acd9918539b230de83cf499ad74c0025",
        "sequence": 120,
        "proposal_type": "Fund",
        "proposal_title": "Save the world",
        "ballot_answer": "",
        "full_count": 1
    }

