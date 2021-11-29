<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Returns proposals of the ledger.

<input class="md-input" placeholder="Enter Page" id="page" width="100"></input><br/>
<input class="md-input" placeholder="Enter pageSize" id="pageSize"></input><br/><br/>

<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/proposals?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/proposals?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`)
        .then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/proposals?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`
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
| page size      | Number of records in a page | 10 |

Example Request JSON:<br/>
[{"proposal_id":"469008972006","proposal_title":"Save the world","proposal_type":"Fund","block_height":876,"fund_amount":10000000000000,"vote_start_height":30,"vote_end_height":200,"proposal_status":"Ongoing","proposal_date":1629349706,"proposer_name":" BOANode","voting_start_date":1630195200,"voting_end_date":1630627200,"full_count":1,"total_validators":6,"yes_percentage":"0.00","no_percentage":"0.00","abstain_percentage":"0.00","not_voted_percentage":"100.00","voted_percentage":"0.00","proposal_result":"Pending"}]
