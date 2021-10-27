<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

 Returns list of proposal voting details
<input class="md-input" placeholder="Enter proposal id" id="proposalId" width="100"></input><br/><br/>
<!-- <input class="md-input" placeholder="Enter page" id="page"></input><br/>
<input class="md-input" placeholder="Enter pageSize" id="pageSize"></input><br/><br/> -->
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/proposal/voting_details/${document.getElementById("proposalId").value || "469008972006"}`
//    /?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "6"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/proposal/voting_details/${document.getElementById("proposalId").value || "469008972006"}`)
        // /?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "6"}`)
        .then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/voting_details/${document.getElementById("proposalId").value || "469008972006"}`
                // /?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "6"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| --------- | ------------ | ------------------------------------ |
| proposal id      | Id of the requested proposal | 469008972006 |
| page      | page number | 1 |
| page size      | Number of records in a page | 6 |

Example Request JSON:<br/>

{
    "address":"boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2","sequence":106,"hash":"0x9ae101d4ff95c9e765145be22adec7fd0af2bc2302d4fcd65be0add852a8e6317a572cca4af247a2943e50c303e048dea380b1220e8011d59a807c80d27c4b20","ballot_answer":"No","voting_time":1633007107,"voter_utxo_key":"0xd58cc81e7d669a40875413e4974927d4694d6b59f5bceda20e84bcf2133c9ebff95f62c7a62ac65e879c3a475abdd56d2130e50eb767ab4c53cdd54a14b5e712","full_count":2},{"address":"boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2","sequence":106,"hash":"0x228179890f9c2132496174cbbdbe30f3a46349393f27b2ca5ad0a8125cdb4e368db008f15e5434887dc4f6ff653f552fa3b1270b36aefb626e4302c7738b6f15","ballot_answer":"No","voting_time":1633084353,"voter_utxo_key":"0xdc5e2235b98bd9286fd7e5269d66593953105ec89b2ff3fa037a435a937101ce770cac45fe5e31bdc990e10b687e96e50603ddcd05facf4cf9ebbed5c15f175a","full_count":2
}

