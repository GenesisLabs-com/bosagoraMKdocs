<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**

Returns a pending transaction by the transaction hash.
<input class="md-input" placeholder="Enter Hash" id="hash" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/transaction/pending/${document.getElementById("hash").value || "0xec5ac9c163072644abe80e8139c45e986626811f5b96a382d3cc812a32878a710f874e7fb8ac2910babdc06c24bcfe44de61beb1723179400fcdd08b2aa34434"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/transaction/pending/${document.getElementById("hash").value || "0xec5ac9c163072644abe80e8139c45e986626811f5b96a382d3cc812a32878a710f874e7fb8ac2910babdc06c24bcfe44de61beb1723179400fcdd08b2aa34434"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/transaction/pending/${document.getElementById("hash").value || "0xec5ac9c163072644abe80e8139c45e986626811f5b96a382d3cc812a32878a710f874e7fb8ac2910babdc06c24bcfe44de61beb1723179400fcdd08b2aa34434"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| hash      | The hash of the transaction to get| 0x6a018d88783486604212cf3239c8a219d836d325561c55b8e13c4ca16c1a6a2cfbff96a4195d0cd64c49cc426b37960f06f470cf066f2cd2df1bbb0d96c53321 |


Example Response JSON:<br/>
{
    "inputs": [
        {
            "utxo": "0x1791b08829791b6ba128e65ee7091c1f53abffd0750f587da8da05ddb9bf892adce542e27e65c3a1c5fd1bbc42736ce1cfc4b9f90e9b33418ab3af8b7c0a10db",
            "unlock": {
                "bytes": "smhkx6Pn55bqw7l+jIxhxN8qJ83y2kQywY9DZiBoAQDFXFaJY/Hdl63c38jRmJpvbOaRVz50SoUu5ZTlzB5tXQE="
            },
            "unlock_age": 0
        }
    ],
    "outputs": [
        {
            "type": 0,
            "value": "609999994900000",
            "lock": {
                "type": 0,
                "bytes": "kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="
            }
        },
        {
            "type": 0,
            "value": "3000000",
            "lock": {
                "type": 0,
                "bytes": "2d/QYt76oor16BDI7Zjo7u69xxoXckflZ2UUkckpy1I="
            }
        }
    ],
    "payload": "",
    "lock_height": "0"
}