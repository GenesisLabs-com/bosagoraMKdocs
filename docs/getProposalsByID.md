<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Returns proposal of the ledger.
<input class="md-input" placeholder="Enter Proposal id" id="proposalId"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/proposal/${document.getElementById("proposalId").value || "469008972006"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/proposal/${document.getElementById("proposalId").value || "469008972006"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/proposal/${document.getElementById("proposalId").value || "469008972006"}`
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

Example Request JSON:<br/>
{
    "proposal_title":"Save the world","proposal_id":"469008972006","detail":"테스트","proposal_tx_hash":"0xac93d0ad21f06c69975a4636c0989da437c24fd17f3f4cb75932eb18890dbde11e370d7d5fefdcfc77ad495259599d58e9c16d35ab65f2dd818674956cefd467","fee_tx_hash":"0x8b6a2e1ecc3616ad63c73d606c4019407ebfd06a122519e7bd88d99af92d19d9621323d7c2e68593053a570522b6bc8575d1ee45a74ee38726f297a5ce08e33d","proposer_name":"슈퍼노드","fund_amount":10000000000000,"proposal_fee":100000000000,"proposal_type":"Fund","vote_start_height":10,"voting_start_date":1630195200,"vote_end_height":50,"voting_end_date":1630627200,"proposal_status":"Closed","proposal_date":1629349706,"pre_evaluation_start_time":1629244800,"pre_evaluation_end_time":1629244800,"ave_pre_evaluation_score":7,"proposer_address":"boa1xrw66w303s5x05ej9uu6djc54kue29j72kah22xqqcrtqj57ztwm5uh524e","proposal_fee_address":"boa1xrzwvvw6l6d9k84ansqgs9yrtsetpv44wfn8zm9a7lehuej3ssskxth867s","urls":[{"url":"https://s3.ap-northeast-2.amazonaws.com/com.kosac.defora.beta.upload-image/BOASCAN_Requirements_Documentation_Version1_0_EN_copy_fb69a8a7d5.pdf"}],"total_validators":6,"total_yes_voted":0,"total_no_voted":0,"total_abstain_voted":0,"total_not_voted":6,"yes_percentage":0,"no_percentage":0,"abstain_percentage":0,"not_voted_percentage":100
}
