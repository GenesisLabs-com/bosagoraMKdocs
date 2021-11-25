<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

<!-- Returns proposals of the ledger. -->
<!-- <input class="md-input" placeholder="Enter Page" id="page" width="100"></input><br/> -->
<input class="md-input" placeholder="Enter pageSize" id="pageSize"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/block/validators?height=${document.getElementById("pageSize").value || "3"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/block/validators?height=${document.getElementById("pageSize").value || "3"}`)
        // ${document.getElementById("page").value || "0"}&pageSize=${document.getElementById("pageSize").value || "6"}`)
        .then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/block/validators?height=${document.getElementById("pageSize").value || "3"}`
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
[{"address":"boa1xrval7gwhjz4k9raqukcnv2n4rl4fxt74m2y9eay6l5mqdf4gntnzhhscrh","utxo_key":"0x210f6551d648a4da654da116b100e941e434e4f232b8579439c2ef64b04819bd2782eb3524c7a29c38c347cdf26006bccac54a58a58f103ae7eb5b252eb53b64","pre_image":{"height":"3","hash":"0x7d5ef81f5eae55c454e2ab54336f708f53aaffbcb38741292412bfe6f7d843dd357483b54bd12df114f5a389c167c59042bba471923f2dd3d5293d3b4a1d8238"},"slashed":0,"block_signed":0,"full_count":5},{"address":"boa1xzval2a3cdxv28n6slr62wlczslk3juvk7cu05qt3z55ty2rlfqfc6egsh2","utxo_key":"0x3b44d65edb3361dd91441ab4f449eeda55644026624c4b8ae12ecf0264fa8a228dbf672ef97e2c4f87fb98ad7099e17b7f9ba7dbe8479672066912b1ea24ba77","pre_image":{"height":"3","hash":"0x9e32c2412b142fc4736e0da48b292c4daccc25c5dba695dd0789225bcd96a74c3e27877e621d4ef6ca7bba2f6d9958a14496deafbdcef1be42e4555e4c793fbd"},"slashed":0,"block_signed":1,"full_count":5},{"address":"boa1xzval3ah8z7ewhuzx6mywveyr79f24w49rdypwgurhjkr8z2ke2mycftv9n","utxo_key":"0x7bacc99e9bf827f0fa6dc6a77303d2e6ba6f1591277b896a9305a9e200853986fe9527fd551077a4ac2b511633ada4190a7b82cddaf606171336e1efba87ea8f","pre_image":{"height":"3","hash":"0xf3f3aba7c503d0ddf9d537d19936bb7c827e5a612de3b5002f585d25902c8b4dfc24fc44c7a727cec81fe5b1e1ead5babbb11207ba517dfa54db47aa1e64ce98"},"slashed":0,"block_signed":0,"full_count":5},{"address":"boa1xrval5rzmma29zh4aqgv3mvcarhwa0w8rgthy3l9vaj3fywf9894ycmjkm8","utxo_key":"0xab19131ad8974a20881e2cd0798684a06ca0054160735cdf67fe8ee5a0eb4e28e9bf3f4c735f9ed3da958778978c86b409b8d133f30992141f0ac7e01e7f1255","pre_image":{"height":"3","hash":"0x09eb52d09652c6558745c97045affd5dfb6db41611fa91ee54166d1ebb187a7e1bd62eff57981afe51f04fe29ccfca284d7f44f765db64263c8ad01fb497aefc"},"slashed":0,"block_signed":0,"full_count":5},{"address":"boa1xzval4nvru2ej9m0rptq7hatukkavemryvct4f8smyy3ky9ct5u0s8w6gfy","utxo_key":"0xdb7664caba94c8d4602c10992c13176307e1e05361c150217166ee77fc4af9bf176f31dc61aba61e634dfc0b4c5f729d59e604607f61c9f66b10c6841f972a0a","pre_image":{"height":"3","hash":"0x28c818aab578dd3742c05add5b1efc2c6da688d223735d2c288ab6890ca18f322cb5b4cb3c852254b80efbb0dd9419d85491f68fc710d9cdd7911743dd027178"},"slashed":0,"block_signed":0,"full_count":5}]