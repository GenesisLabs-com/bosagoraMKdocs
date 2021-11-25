<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
Returns Reward of the validator
<input class="md-input" placeholder="Enter address" id="address" width="100"></input><br/>
<input class="md-input" placeholder="Enter page" id="page" width="100"></input><br/>
<input class="md-input" placeholder="Enter pageSize" id="pageSize"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/validator/reward/${document.getElementById("address").value || "boa1xrval5rzmma29zh4aqgv3mvcarhwa0w8rgthy3l9vaj3fywf9894ycmjkm8"}?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`
   //${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/validator/reward/${document.getElementById("address").value || "boa1xrval5rzmma29zh4aqgv3mvcarhwa0w8rgthy3l9vaj3fywf9894ycmjkm8"}?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`)
        // ${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`)
        .then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/validator/reward/${document.getElementById("address").value || "boa1xrval5rzmma29zh4aqgv3mvcarhwa0w8rgthy3l9vaj3fywf9894ycmjkm8"}?page=${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`
                // ${document.getElementById("page").value || "1"}&pageSize=${document.getElementById("pageSize").value || "10"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p><br/>
| Query String | Explanation    | Example                            |
| --------- | ------------ | ------------------------------------ |
| address      | block address | boa1xrval5rzmma29zh4aqgv3mvcarhwa0w8rgthy3l9vaj3fywf9894ycmjkm8 |
| page      | page number | 1 |
| page size      | Number of records in a page | 10 |

Example Request JSON:<br/>
[{"block_height":288,"steaking_amount":20000000000000,"block_reward":0,"block_fee":254800,"validator_reward":164429715488,"full_count":33},{"block_height":432,"steaking_amount":20000000000000,"block_reward":10468086909851,"block_fee":161700,"validator_reward":174964354323,"full_count":33},{"block_height":576,"steaking_amount":20000000000000,"block_reward":4258235798365,"block_fee":161700,"validator_reward":174964358617,"full_count":33},{"block_height":720,"steaking_amount":20000000000000,"block_reward":8024556742696,"block_fee":254800,"validator_reward":174964910839,"full_count":33},{"block_height":864,"steaking_amount":20000000000000,"block_reward":0,"block_fee":161700,"validator_reward":174964894550,"full_count":33},{"block_height":1008,"steaking_amount":20000000000000,"block_reward":9620869615416,"block_fee":161700,"validator_reward":174965244415,"full_count":33},{"block_height":1152,"steaking_amount":20000000000000,"block_reward":9281980620042,"block_fee":161700,"validator_reward":174965225556,"full_count":33},{"block_height":1296,"steaking_amount":20000000000000,"block_reward":0,"block_fee":161700,"validator_reward":174965481088,"full_count":33},{"block_height":1440,"steaking_amount":20000000000000,"block_reward":0,"block_fee":161700,"validator_reward":174965432209,"full_count":33},{"block_height":1584,"steaking_amount":20000000000000,"block_reward":0,"block_fee":161700,"validator_reward":174965562554,"full_count":33}]
