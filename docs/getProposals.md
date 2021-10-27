<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Returns proposals of the ledger.
<!-- <input class="md-input" placeholder="Enter Page" id="page" width="100"></input><br/>
<input class="md-input" placeholder="Enter pageSize" id="pageSize"></input><br/><br/> -->
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/proposals/?page=0&pageSize=6`
   //${document.getElementById("page").value || "0"}&pageSize=${document.getElementById("pageSize").value || "6"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/proposals?page=0&pageSize=6`)
        // ${document.getElementById("page").value || "0"}&pageSize=${document.getElementById("pageSize").value || "6"}`)
        .then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/proposals/?page=0&pageSize=6`
                // ${document.getElementById("page").value || "0"}&pageSize=${document.getElementById("pageSize").value || "6"}`
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