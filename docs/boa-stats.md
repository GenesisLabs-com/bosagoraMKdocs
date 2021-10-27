<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**

Returns statistics of BOA coin.
</br>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/boa-stats`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/boa-stats`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/boa-stats`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
<br/>
| Query String | Explanation | Example    

<br/>

Example Response JSON:<br/>
{
    "height":15,"transactions":2,"validators":1,"frozen_coin":5283595,"circulating_supply":5283535,"active_validators":155055
}