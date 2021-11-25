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
| page      | page number | 1 |
| page size      | Number of records in a page | 6 |

Example Request JSON:<br/>
{
"proposal_id":"469008972006","proposal_title":"Title","proposal_type":"Fund","fund_amount":10000000000000,"vote_start_height":1000,"vote_end_height":3026,"proposal_status":"Voting","proposal_date":1629349706,"proposer_name":"슈퍼노드","voting_start_date":1630177200,"voting_end_date":1630609200,"full_count":4
}
