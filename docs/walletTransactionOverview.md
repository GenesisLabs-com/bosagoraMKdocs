<h6>Endpoint</h6>

<p id="endpoint"></p>

HTTP Method: **GET**

Returns a transaction overview.

<input class="md-input" placeholder="Enter Hash" id="hash"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/wallet/transaction/overview/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/wallet/transaction/overview/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/wallet/transaction/overview/${document.getElementById("hash").value || "0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>

| Query String | Explanation    | Example                            |
| ------------ | ---------------- | -------------------------------------------- |
| Hash  | hash of the transaction | 0x26866BB263593D024A92103646C48CF35A2B1BFCC49B087915B85DB14A432B373569D56F576242354328A31BF0102A0A78CB806CF6E25D88D7981367833631B7
 |


Example Response JSON:<br/>
{
    "status":"Confirmed","height":"0","time":1609459200,"tx_hash":"0x26866bb263593d024a92103646c48cf35a2b1bfcc49b087915b85db14a432b373569d56f576242354328a31bf0102a0a78cb806cf6e25d88d7981367833631b7","tx_type":"payment","tx_size":368,"unlock_height":"1","lock_height":"0","unlock_time":1609459800,"payload":"","senders":[],"receivers":[{"type":0,"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","lock_type":0,"amount":610000000000000,"utxo":"0xb9794167a781561298bcb0f634346c85e56fba3f26c641e52dbf0066e8fb0b96d278cdd4c22c7e9885fceb307368e4130aaebd7800905c27c6a6e09870d8d9ca","index":0,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="},{"type":0,"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","lock_type":0,"amount":610000000000000,"utxo":"0x359ab01b4c15f7dffa257a042335321b2a576b61ccd379bf6922451dabbd688ab5818bd1cc22d61a09f11859a0368d82a73329de6614b440486172011472f346","index":1,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="},{"type":0,"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","lock_type":0,"amount":610000000000000,"utxo":"0x33650ce9f62244d45c61cab51f1b0a3fbf94190e8f8ea79bfe85a0852fea6368fc7747db593c719e4f16d29889cdd37196796a76ba78c5facf9eb31824144a69","index":2,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="},{"type":0,"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","lock_type":0,"amount":610000000000000,"utxo":"0x5671ec730a0233c1cec76a59332755c3f59f0310d87acd02261f53c650692a2c8d113a0b0df8fede65ea52010df84f2d67bd166e44f1afe1149910e61bcfa79e","index":3,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="},{"type":0,"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","lock_type":0,"amount":610000000000000,"utxo":"0xfabfc442dd2d5a65b8a65d648eaeb5371f1db46f8a9e7e06c80d36f239469db728758ca466f6933fad7ecbd8153c680184caf2ece953cd02d8d816fabbfb13f5","index":4,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="},{"type":0,"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","lock_type":0,"amount":610000000000000,"utxo":"0x1791b08829791b6ba128e65ee7091c1f53abffd0750f587da8da05ddb9bf892adce542e27e65c3a1c5fd1bbc42736ce1cfc4b9f90e9b33418ab3af8b7c0a10db","index":5,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="},{"type":0,"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","lock_type":0,"amount":610000000000000,"utxo":"0x62582cff703565f17911f438f7bd30ffb7ef7809e016a916fde1d617ba090d37de2e2e0d6b45f0a7f9a2773d5eadb93b390d5eab197ead5247d62a776dc92197","index":6,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="},{"type":0,"address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","lock_type":0,"amount":610000000000000,"utxo":"0x3c18b4e7c93987a7bf71c905c36dda39f7adc61d8f1a4ad919ef1960a97df9dec270581153756820541f662e619a49db3f35a7c8b9ec7607812dd5b03e2653b8","index":7,"bytes":"kZnmFMJObP4+SLxUChUrKaFP/7ek7wIYk79A66URrHE="}],"fee":"0"
}