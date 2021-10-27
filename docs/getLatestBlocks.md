<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Returns Latest blocks of the ledger.
<!-- <input class="md-input" placeholder="Enter Page" id="page" width="100"></input><br/>
<input class="md-input" placeholder="Enter pageSize" id="pageSize"></input><br/><br/> -->
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/latest-blocks?page=0&pageSize=6`
//    ${document.getElementById("page").value || "0"}&pageSize=${document.getElementById("pageSize").value || "6"`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/latest-blocks?page=0&pageSize=6`)
        // ${document.getElementById("page").value || "0"}&pageSize=${document.getElementById("pageSize").value || "6"}`)
        .then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/latest-blocks?page=0pageSize=6`
                //${document.getElementById("page").value || "0"}&pageSize=${document.getElementById("pageSize").value || "6"}`
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


Example Response JSON:<br/>
[{"height":"3","hash":"0xaf183b3ac3b667b1ae79f93392ace8565b9e140388521e4e5a7fe1f552205894f4e348a42d88176dc439bd04b7764eae9c2b48af68d05a3917907eb847617d3a","merkle_root":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000","signature":"0x80488a3d74678983c2a3a2878f48588e53d6713fdc203e86a44287562e430e7d00750728bd67e87dbdd9d32e10d20d1fb9afedda3acf4a422feefc8505207c19","validators":"1","tx_count":"0","enrollment_count":"0","time_stamp":1631789804,"full_count":4},{"height":"2","hash":"0x8811e686e319b9bb20e7ffbb22501b6fd6d166bee7ae4e8051b4f640a0b1f9f68d7e7cbe0221cc8caf55eb3782eb0a470b99c6fd3ed057ca399d809aa7b4fa4f","merkle_root":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000","signature":"0x9a0f225970239220272a83ba058038a9f00de64674966c988826682c15dfee3e057398db16cff91fb4aef0ca8d5a02b3bd42ec20acdd06c18a0c24c54f3a6257","validators":"1","tx_count":"0","enrollment_count":"0","time_stamp":1631789799,"full_count":4},{"height":"1","hash":"0x6453be41ffbb56ada86ee8ff9fb23acbb6b87e409eb871d67cf5599d82b8adddfbfebe2fc7da0c6efb755f3f788dc6bead322a2029fbe65b6917fe4d9f6277f2","merkle_root":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000","signature":"0x4da1ad0fe9cd7409929fef139a45db3652dc16fbd8cefc8d04df50056c44071107bb20061e4e6027000c977655d6043ad3cefbec494df4ae2ce55d827183dc6f","validators":"1","tx_count":"0","enrollment_count":"0","time_stamp":1631789794,"full_count":4},{"height":"0","hash":"0xe8dbdeb515cf835f515355045ec1af6cb141f9690fb85b01294fe1985e84a37bd78f0100af5e1847a881d04da033e1a84c903f81bd05e52cadc534518f4011ff","merkle_root":"0xaf402f71c175bc6f53ededdd9cfa1f4c074efcd2fe7090c9d0ca3b95c5d1e7513cd4b4f922c4f7ebf120958f449a2d3e23a397c7219e297b8ff1cfbc00ebc93d","signature":"0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000","validators":"0","tx_count":"2","enrollment_count":"1","time_stamp":1609459200,"full_count":4}]