<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**
<br/>
<br/>
Returns block as true if hash matches block hash or transaction as true if hash matches tx_hash 
otherwise it will respond with no data found.


<input class="md-input" placeholder="Enter Hash" id="hash"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/search/hash/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/search/hash/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/search/hash/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |
| hash   | hash of block or transaction | 0xE8DBDEB515CF835F515355045EC1AF6CB141F9690FB85B01294FE1985E84A37BD78F0100AF5E1847A881D04DA033E1A84C903F81BD05E52CADC534518F4011FF|

Example Response JSON:<br/>
{
    "block":1,"transaction":0
}