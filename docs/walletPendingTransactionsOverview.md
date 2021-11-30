<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
<br/>
Returns a pending transaction overview.

<input class="md-input" placeholder="Enter Hash" id="hash"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/transaction/pending/overview/${document.getElementById("hash").value ||"0xfeac1a778c20ddc94987597fccae8bb4a85951c6ec0cc9deb83f6b478daa3333c5e8235632f33156c49da6a0f1b2b47f68f6b5037b2e9e52ac8bf1842eeba4e7"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/transaction/pending/overview/${document.getElementById("hash").value ||"0xfeac1a778c20ddc94987597fccae8bb4a85951c6ec0cc9deb83f6b478daa3333c5e8235632f33156c49da6a0f1b2b47f68f6b5037b2e9e52ac8bf1842eeba4e7"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/transaction/pending/overview/${document.getElementById("hash").value ||"0xfeac1a778c20ddc94987597fccae8bb4a85951c6ec0cc9deb83f6b478daa3333c5e8235632f33156c49da6a0f1b2b47f68f6b5037b2e9e52ac8bf1842eeba4e7"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<h6>Result</h6>
<p id="showResult"></p>

| Query String | Explanation    | Example                            |
| --------- | ------------ | ------------------------------------ |
| Hash       | hash of the transaction | 0xfeac1a778c20ddc94987597fccae8bb4a85951c6ec0cc9deb83f6b478daa3333c5e8235632f33156c49da6a0f1b2b47f68f6b5037b2e9e52ac8bf1842eeba4e7 |


Example Response JSON:<br/>
{"status":"Pending","height":"","time":1637830156,"tx_hash":"0xfeac1a778c20ddc94987597fccae8bb4a85951c6ec0cc9deb83f6b478daa3333c5e8235632f33156c49da6a0f1b2b47f68f6b5037b2e9e52ac8bf1842eeba4e7","tx_type":"Payment","tx_size":231,"unlock_height":"0","lock_height":"0","unlock_time":0,"payload":"0","senders":[{"address":"boa1xqcj00xwz7e6mxg5p324m98enc7j2a727ty9p7jqf6aezvfps4f8xtg5mal","amount":3583957999631,"utxo":"0x1a3a0d56e46ab397cbf602c8ac17c47e2dd06feed58116c5b0aaef1e3009e6e2edb58d71a05589c80e0d18a9608c65bf57a6d10e3bda454c189347ef47e285bd","signature":"","index":0,"unlock_age":"Key","bytes":"Dx8xPk6dNrpBAOvLlBZOLHy7YSddMPxda3fiPe79bQLiRUIhEK9KsjB4Ed52TA5HNfiQgrujTTVnlV9cVGoOJwE="}],"receivers":[{"type":0,"address":"boa1xqcj00xwz7e6mxg5p324m98enc7j2a727ty9p7jqf6aezvfps4f8xtg5mal","lock_type":"Key","amount":2224310318035,"utxo":"","index":0,"bytes":"MSe8zhezrZkUDFVdlPmePSV3yvLIUPpATruRMSGFUnM="},{"type":0,"address":"boa1xzre000thp9r3u0kxlhfe0rt5m3xlse0gmmcnxqqpnxc3vw2nhdv2auejmg","lock_type":"Key","amount":1359647681596,"utxo":"","index":1,"bytes":"h5e967hKOPH2N+6cvGum4m/DL0b3iZgADM2Iscqd2sU="}],"fee":"161700","dataFee":"0"}