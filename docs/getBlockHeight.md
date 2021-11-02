<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Returns the highest block height stored in Stoa
<br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML ="https://dev-stoa-boascan.bosagora.com/block_height"
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch("https://dev-stoa-boascan.bosagora.com/block_height").then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML ="https://dev-stoa-boascan.bosagora.com/block_height"
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            | 
| --------- | ------------ | ------------------------------------ |
| page      | page number | 1 |
| page size      | Number of records in a page | 6 |

Example Response JSON:<br/>
"5"
