<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**

Return the block height corresponding to the block creation time
<input class="md-input" placeholder="Enter Time" id="time" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/block_height_at/${document.getElementById("time").value || "1631686328"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/block_height_at/${document.getElementById("time").value || "1631686328"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res[0])
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/block_height_at/${document.getElementById("time").value || "1631686328"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Query String | Explanation    | Example                            |
| ------------ | -------------- | ---------------------------------- |
| time         | block creation time | 1631686328 |

Example Response JSON:<br/>
"37045"
