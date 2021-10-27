<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**

Returns a transaction by the transaction hash.
<input class="md-input" placeholder="Enter Hash" id="hash"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/transaction/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/transaction/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/transaction/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| hash      | The hash of the transaction to get | 0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7 |

Example Response JSON:<br/>
{"inputs":[],"outputs":[{"type":0,"value":"610000000000000","lock":{"type":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}},{"type":0,"value":"610000000000000","lock":{"type":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}},{"type":0,"value":"610000000000000","lock":{"type":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}},{"type":0,"value":"610000000000000","lock":{"type":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}},{"type":0,"value":"610000000000000","lock":{"type":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}},{"type":0,"value":"610000000000000","lock":{"type":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}},{"type":0,"value":"610000000000000","lock":{"type":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}},{"type":0,"value":"610000000000000","lock":{"type":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}}],"payload":"","lock_height":"0"}