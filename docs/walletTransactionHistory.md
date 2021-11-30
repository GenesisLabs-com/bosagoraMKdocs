<h6>Endpoint</h6>
<p id="endpoint"></p>

HTTP Method: **GET**
<br/>
<br/>
Returns a set of transactions history of the addresses.

<input class="md-input" placeholder="Enter Address" id="address" width="100"></input><br/><br/>
<button class="md-button" onclick="tryNow()">Try Now</button>

<script>
   document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/wallet/transactions/history/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`https://dev-stoa-boascan.bosagora.com/wallet/transactions/history/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`https://dev-stoa-boascan.bosagora.com/wallet/transactions/history/${document.getElementById("address").value || "boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67"}`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<h6>Result</h6>
<p id="showResult"></p>


| Parameter | Explanation  | Example                              |
| --------- | ------------ | ------------------------------------ |
| address   | address to query. | boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67|

Example Response JSON:<br/>
[{"display_tx_type":"Outbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xpxx007eyhx4qh4w2dfmm8fh8yse5fv6prtgnw2ulpl4lam32l5v7ykkrah","peer_count":72,"height":"19","time":1638163458,"tx_hash":"0xa14b94999f7e3c6c6baabb5cc0db1cbedbed1bcb2e97f5532c41a5cd34bba08986c0ff7fcb0c4542c4e0aa682154a0a4214f0af1593b079d140129a95cf2a8f5","tx_type":"Payment","amount":"-610000000000000","unlock_height":"20","unlock_time":1638164058,"tx_fee":2366700,"tx_size":3381,"full_count":9},{"display_tx_type":"Outbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xzuu00qnhnpxq7jgxnqemjzuk5406068g6xzpt7glywudhs87dsgzcrj7m5","peer_count":72,"height":"17","time":1638163448,"tx_hash":"0x927f49180d35894f86bc36fd2588306432f3c432d108dca515bf471ce7a51b2ad3ee8dc9e75ad03f2fae869665bfabb678e7d536a9f19d099a848c572fc3dfed","tx_type":"Payment","amount":"-610000000000000","unlock_height":"18","unlock_time":1638164048,"tx_fee":2366700,"tx_size":3381,"full_count":9},{"display_tx_type":"Outbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xqrr00xnghw6d6023h2hy7mngenvsttcsynmxt7qt806xr05ssjpjhqvhwt","peer_count":72,"height":"15","time":1638163438,"tx_hash":"0x54605faef597546c141bd73ab151e6d8e73f746a44032adab79c8f0f678b039d33b003cbb6f8eea472742941114427724633b9681c543f849eb69cb4b3af48fb","tx_type":"Payment","amount":"-610000000000000","unlock_height":"16","unlock_time":1638164038,"tx_fee":2366700,"tx_size":3381,"full_count":9},{"display_tx_type":"Outbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xrnn00264lfprtktmccrm4jqas534l33kx2knx7k0d73pu593pqsyjgl2l9","peer_count":72,"height":"13","time":1638163428,"tx_hash":"0x2e09561cf04798a0c3d6027798d90c3f5a3ea31e74ae9e590028e4444ba2cd4cae8e5b97c208817f438c936554f48ffc53d9920054af958757f24d49854fa76e","tx_type":"Payment","amount":"-610000000000000","unlock_height":"14","unlock_time":1638164028,"tx_fee":2366700,"tx_size":3381,"full_count":9},{"display_tx_type":"Outbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xqkk0037xy9tgyfu6gc4fr2f5yvxa9ngvp33c9h7m5rtstz5tldd2mja2yk","peer_count":72,"height":"11","time":1638163418,"tx_hash":"0x841dbcce2416e6977fa3e462c896c7a0a96e4a02ec8a891dfeb34113313033c59db6dd33e81c9c0e2f9304c4c89bcc25323a3a2ce2464d2145a0a9638076ae0f","tx_type":"Payment","amount":"-610000000000000","unlock_height":"12","unlock_time":1638164018,"tx_fee":2366700,"tx_size":3381,"full_count":9},{"display_tx_type":"Outbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xzgg00zdrwnsrsy37e0rszcshvd4l4wmjyjxc4vlevm5zea997vzk5wttdz","peer_count":72,"height":"9","time":1638163408,"tx_hash":"0x178b43a015541ec9ac4518c717f90c6168c2f15e3980079dbfac48c2c94169df3caadbfca4a7eb3ae337ef7da7f3e23fd43bcaaf4da4019dee1faa415851d38b","tx_type":"Payment","amount":"-610000000000000","unlock_height":"10","unlock_time":1638164008,"tx_fee":2366700,"tx_size":3381,"full_count":9},{"display_tx_type":"Outbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xpdd00xpjxdlvq634pfn47lwz9pa0wslst30kvq809gv3ysdayfagnrmc2f","peer_count":72,"height":"7","time":1638163398,"tx_hash":"0xabf365ebca612dfc90039f5ea919666798f5afe8129f53a35261d37a91d2c6ac4402c5b0f4d58999a9c281a94e2a757a822537dc674a94c6aad696d07cc07adc","tx_type":"Payment","amount":"-610000000000000","unlock_height":"8","unlock_time":1638163998,"tx_fee":2366700,"tx_size":3381,"full_count":9},{"display_tx_type":"Outbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xza007gllhzdawnr727hds36guc0frnjsqscgf4k08zqesapcg3uujh9g93","peer_count":84,"height":"5","time":1638163388,"tx_hash":"0x4af81596e1f98d94620fbf63e2d6f93e37d090c4da2f2ccdb96a1e8e593f2dca9d5e59d16fefaa7b8c65370e1809366da936426759753365d326573cfbe9fa95","tx_type":"Payment","amount":"-610000000000000","unlock_height":"6","unlock_time":1638163988,"tx_fee":2744700,"tx_size":3921,"full_count":9},{"display_tx_type":"Inbound","address":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer":"boa1xzgenes5cf8xel37fz79gzs49v56znllk7jw7qscjwl5p6a9zxk8zaygm67","peer_count":0,"height":"0","time":1638163369,"tx_hash":"0x26866bb263593d024a92103646c48cf35a2b1bfcc49b087915b85db14a432b373569d56f576242354328a31bf0102a0a78cb806cf6e25d88d7981367833631b7","tx_type":"Payment","amount":"4880000000000000","unlock_height":"1","unlock_time":1638163969,"tx_fee":0,"tx_size":368,"full_count":9}]