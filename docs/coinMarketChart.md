<h6>Endpoint</h6>

<p id="endpoint"></p>
HTTP Method: **GET**

Returns BOA statistics of last 24 hours.
<br/>
<button class="md-button" onclick="tryNow()">Try Now</button>
<script>
   document.getElementById("endpoint").innerHTML =`http://3.38.34.30/coinmarketchart`
    function tryNow(){
        document.getElementById("showResult").innerHTML =""
        document.getElementById("endpoint").innerHTML =""
        fetch(`http://3.38.34.30:3836/coinmarketchart`).then((res) => {
            res.json().then((res) => {
                document.getElementById("showResult").innerHTML = JSON.stringify(res)
                document.getElementById("endpoint").innerHTML =`http://3.38.34.30:3836/coinmarketchart`
                })
        }).catch((err) => {
            console.log(err)
        })
    }
</script>
<p id="showResult"></p>
| Query String | Explanation    | Example                            |
</br>

Example Response JSON:<br/>
[
    {
        "usd_price": "0.109532",
        "last_updated_at": 1631784722
    },
    {
        "usd_price": "0.109569",
        "last_updated_at": 1631785238
    },
    {
        "usd_price": "0.109509",
        "last_updated_at": 1631785484
    },
    {
        "usd_price": "0.109526",
        "last_updated_at": 1631785607
    },
    {
        "usd_price": "0.109414",
        "last_updated_at": 1631786146
    },
    {
        "usd_price": "0.109331",
        "last_updated_at": 1631786478
    },
    {
        "usd_price": "0.109823",
        "last_updated_at": 1631786693
    },
    {
        "usd_price": "0.109796",
        "last_updated_at": 1631786914
    },
    {
        "usd_price": "0.109862",
        "last_updated_at": 1631787184
    },
    {
        "usd_price": "0.109762",
        "last_updated_at": 1631787506
    },
    {
        "usd_price": "0.109789",
        "last_updated_at": 1631787832
    },
    {
        "usd_price": "0.109485",
        "last_updated_at": 1631788249
    },
    {
        "usd_price": "0.109483",
        "last_updated_at": 1631788499
    },
    {
        "usd_price": "0.109455",
        "last_updated_at": 1631788802
    },
    {
        "usd_price": "0.109685",
        "last_updated_at": 1631789094
    },
    {
        "usd_price": "0.109901",
        "last_updated_at": 1631789691
    },
    {
        "usd_price": "0.109808",
        "last_updated_at": 1631790237
    },
    {
        "usd_price": "0.109708",
        "last_updated_at": 1631790427
    },
    {
        "usd_price": "0.109871",
        "last_updated_at": 1631790697
    },
    {
        "usd_price": "0.109749",
        "last_updated_at": 1631791151
    },
    {
        "usd_price": "0.109812",
        "last_updated_at": 1631791282
    },
    {
        "usd_price": "0.109861",
        "last_updated_at": 1631791641
    },
    {
        "usd_price": "0.109654",
        "last_updated_at": 1631791967
    },
    {
        "usd_price": "0.109788",
        "last_updated_at": 1631792232
    },
    {
        "usd_price": "0.110236",
        "last_updated_at": 1631792692
    },
    {
        "usd_price": "0.110261",
        "last_updated_at": 1631793357
    },
    {
        "usd_price": "0.110146",
        "last_updated_at": 1631793819
    },
    {
        "usd_price": "0.110264",
        "last_updated_at": 1631794080
    },
    {
        "usd_price": "0.110011",
        "last_updated_at": 1631794394
    },
    {
        "usd_price": "0.109900",
        "last_updated_at": 1631794759
    },
    {
        "usd_price": "0.109716",
        "last_updated_at": 1631795015
    },
    {
        "usd_price": "0.109682",
        "last_updated_at": 1631795384
    },
    {
        "usd_price": "0.109839",
        "last_updated_at": 1631795546
    },
    {
        "usd_price": "0.109899",
        "last_updated_at": 1631796031
    },
    {
        "usd_price": "0.109949",
        "last_updated_at": 1631796123
    },
    {
        "usd_price": "0.109927",
        "last_updated_at": 1631796411
    },
    {
        "usd_price": "0.109828",
        "last_updated_at": 1631796917
    },
    {
        "usd_price": "0.111365",
        "last_updated_at": 1631797556
    },
    {
        "usd_price": "0.111316",
        "last_updated_at": 1631797867
    },
    {
        "usd_price": "0.111967",
        "last_updated_at": 1631798145
    },
    {
        "usd_price": "0.111863",
        "last_updated_at": 1631798324
    },
    {
        "usd_price": "0.111475",
        "last_updated_at": 1631798661
    },
    {
        "usd_price": "0.111477",
        "last_updated_at": 1631798984
    },
    {
        "usd_price": "0.111109",
        "last_updated_at": 1631799352
    },
    {
        "usd_price": "0.110979",
        "last_updated_at": 1631799780
    },
    {
        "usd_price": "0.110951",
        "last_updated_at": 1631800056
    },
    {
        "usd_price": "0.110736",
        "last_updated_at": 1631800429
    },
    {
        "usd_price": "0.110929",
        "last_updated_at": 1631801132
    },
    {
        "usd_price": "0.110427",
        "last_updated_at": 1631801433
    },
    {
        "usd_price": "0.110546",
        "last_updated_at": 1631801512
    },
    {
        "usd_price": "0.110186",
        "last_updated_at": 1631801893
    },
    {
        "usd_price": "0.110190",
        "last_updated_at": 1631802272
    },
    {
        "usd_price": "0.110238",
        "last_updated_at": 1631802445
    },
    {
        "usd_price": "0.109880",
        "last_updated_at": 1631802870
    },
    {
        "usd_price": "0.109806",
        "last_updated_at": 1631803416
    },
    {
        "usd_price": "0.110535",
        "last_updated_at": 1631803860
    },
    {
        "usd_price": "0.110563",
        "last_updated_at": 1631804134
    },
    {
        "usd_price": "0.110591",
        "last_updated_at": 1631804191
    },
    {
        "usd_price": "0.110531",
        "last_updated_at": 1631804531
    },
    {
        "usd_price": "0.110143",
        "last_updated_at": 1631804814
    },
    {
        "usd_price": "0.109872",
        "last_updated_at": 1631805361
    },
    {
        "usd_price": "0.109983",
        "last_updated_at": 1631805580
    },
    {
        "usd_price": "0.109854",
        "last_updated_at": 1631805942
    },
    {
        "usd_price": "0.110146",
        "last_updated_at": 1631806279
    },
    {
        "usd_price": "0.109711",
        "last_updated_at": 1631806519
    },
    {
        "usd_price": "0.109716",
        "last_updated_at": 1631806596
    },
    {
        "usd_price": "0.109651",
        "last_updated_at": 1631806974
    },
    {
        "usd_price": "0.109926",
        "last_updated_at": 1631807371
    },
    {
        "usd_price": "0.109914",
        "last_updated_at": 1631807681
    },
    {
        "usd_price": "0.109894",
        "last_updated_at": 1631808020
    },
    {
        "usd_price": "0.109565",
        "last_updated_at": 1631808146
    },
    {
        "usd_price": "0.109682",
        "last_updated_at": 1631808446
    },
    {
        "usd_price": "0.108888",
        "last_updated_at": 1631808785
    },
    {
        "usd_price": "0.108786",
        "last_updated_at": 1631809113
    },
    {
        "usd_price": "0.108764",
        "last_updated_at": 1631809469
    },
    {
        "usd_price": "0.108752",
        "last_updated_at": 1631809807
    },
    {
        "usd_price": "0.108648",
        "last_updated_at": 1631810090
    },
    {
        "usd_price": "0.108595",
        "last_updated_at": 1631810459
    },
    {
        "usd_price": "0.108678",
        "last_updated_at": 1631810640
    },
    {
        "usd_price": "0.108680",
        "last_updated_at": 1631810977
    },
    {
        "usd_price": "0.108567",
        "last_updated_at": 1631811275
    },
    {
        "usd_price": "0.108576",
        "last_updated_at": 1631811620
    },
    {
        "usd_price": "0.108505",
        "last_updated_at": 1631811912
    },
    {
        "usd_price": "0.107850",
        "last_updated_at": 1631812083
    },
    {
        "usd_price": "0.107862",
        "last_updated_at": 1631812494
    },
    {
        "usd_price": "0.108603",
        "last_updated_at": 1631812673
    },
    {
        "usd_price": "0.108598",
        "last_updated_at": 1631813137
    },
    {
        "usd_price": "0.108506",
        "last_updated_at": 1631813324
    },
    {
        "usd_price": "0.108485",
        "last_updated_at": 1631813673
    },
    {
        "usd_price": "0.108314",
        "last_updated_at": 1631813940
    },
    {
        "usd_price": "0.107629",
        "last_updated_at": 1631814286
    },
    {
        "usd_price": "0.107373",
        "last_updated_at": 1631814754
    },
    {
        "usd_price": "0.108251",
        "last_updated_at": 1631815498
    },
    {
        "usd_price": "0.108232",
        "last_updated_at": 1631815561
    },
    {
        "usd_price": "0.108215",
        "last_updated_at": 1631816063
    },
    {
        "usd_price": "0.108103",
        "last_updated_at": 1631816312
    },
    {
        "usd_price": "0.108220",
        "last_updated_at": 1631816611
    },
    {
        "usd_price": "0.108339",
        "last_updated_at": 1631817035
    },
    {
        "usd_price": "0.108291",
        "last_updated_at": 1631817192
    },
    {
        "usd_price": "0.108247",
        "last_updated_at": 1631817577
    },
    {
        "usd_price": "0.108196",
        "last_updated_at": 1631817869
    },
    {
        "usd_price": "0.108213",
        "last_updated_at": 1631818348
    },
    {
        "usd_price": "0.108226",
        "last_updated_at": 1631818745
    },
    {
        "usd_price": "0.108470",
        "last_updated_at": 1631819142
    },
    {
        "usd_price": "0.108290",
        "last_updated_at": 1631819274
    },
    {
        "usd_price": "0.108300",
        "last_updated_at": 1631819693
    },
    {
        "usd_price": "0.108334",
        "last_updated_at": 1631820078
    },
    {
        "usd_price": "0.108322",
        "last_updated_at": 1631820336
    },
    {
        "usd_price": "0.108104",
        "last_updated_at": 1631820578
    },
    {
        "usd_price": "0.108323",
        "last_updated_at": 1631820826
    },
    {
        "usd_price": "0.108266",
        "last_updated_at": 1631821533
    },
    {
        "usd_price": "0.108348",
        "last_updated_at": 1631822094
    },
    {
        "usd_price": "0.108297",
        "last_updated_at": 1631822325
    },
    {
        "usd_price": "0.108123",
        "last_updated_at": 1631822563
    },
    {
        "usd_price": "0.108012",
        "last_updated_at": 1631822891
    },
    {
        "usd_price": "0.108226",
        "last_updated_at": 1631823235
    },
    {
        "usd_price": "0.108269",
        "last_updated_at": 1631823635
    },
    {
        "usd_price": "0.108304",
        "last_updated_at": 1631823860
    },
    {
        "usd_price": "0.108314",
        "last_updated_at": 1631824255
    },
    {
        "usd_price": "0.108174",
        "last_updated_at": 1631824558
    },
    {
        "usd_price": "0.108226",
        "last_updated_at": 1631824749
    },
    {
        "usd_price": "0.108213",
        "last_updated_at": 1631825020
    },
    {
        "usd_price": "0.108195",
        "last_updated_at": 1631825287
    },
    {
        "usd_price": "0.108129",
        "last_updated_at": 1631825746
    },
    {
        "usd_price": "0.108347",
        "last_updated_at": 1631825823
    },
    {
        "usd_price": "0.108174",
        "last_updated_at": 1631826325
    },
    {
        "usd_price": "0.108299",
        "last_updated_at": 1631826488
    },
    {
        "usd_price": "0.108078",
        "last_updated_at": 1631826868
    },
    {
        "usd_price": "0.108133",
        "last_updated_at": 1631827259
    },
    {
        "usd_price": "0.108670",
        "last_updated_at": 1631827512
    },
    {
        "usd_price": "0.108485",
        "last_updated_at": 1631828101
    },
    {
        "usd_price": "0.108502",
        "last_updated_at": 1631828677
    },
    {
        "usd_price": "0.108466",
        "last_updated_at": 1631828884
    },
    {
        "usd_price": "0.108530",
        "last_updated_at": 1631829325
    },
    {
        "usd_price": "0.108564",
        "last_updated_at": 1631829750
    },
    {
        "usd_price": "0.108642",
        "last_updated_at": 1631830070
    },
    {
        "usd_price": "0.110391",
        "last_updated_at": 1631830311
    },
    {
        "usd_price": "0.110005",
        "last_updated_at": 1631830886
    },
    {
        "usd_price": "0.109978",
        "last_updated_at": 1631831054
    },
    {
        "usd_price": "0.109914",
        "last_updated_at": 1631831300
    },
    {
        "usd_price": "0.109917",
        "last_updated_at": 1631831597
    },
    {
        "usd_price": "0.109802",
        "last_updated_at": 1631831813
    },
    {
        "usd_price": "0.109669",
        "last_updated_at": 1631832336
    },
    {
        "usd_price": "0.109627",
        "last_updated_at": 1631832432
    },
    {
        "usd_price": "0.109622",
        "last_updated_at": 1631832753
    },
    {
        "usd_price": "0.109697",
        "last_updated_at": 1631833107
    },
    {
        "usd_price": "0.109612",
        "last_updated_at": 1631833544
    },
    {
        "usd_price": "0.109565",
        "last_updated_at": 1631833789
    },
    {
        "usd_price": "0.109404",
        "last_updated_at": 1631833941
    },
    {
        "usd_price": "0.109413",
        "last_updated_at": 1631834667
    },
    {
        "usd_price": "0.109448",
        "last_updated_at": 1631835017
    },
    {
        "usd_price": "0.109530",
        "last_updated_at": 1631835209
    },
    {
        "usd_price": "0.109316",
        "last_updated_at": 1631835478
    },
    {
        "usd_price": "0.109453",
        "last_updated_at": 1631835943
    },
    {
        "usd_price": "0.109569",
        "last_updated_at": 1631836235
    },
    {
        "usd_price": "0.109831",
        "last_updated_at": 1631836479
    },
    {
        "usd_price": "0.109826",
        "last_updated_at": 1631836775
    },
    {
        "usd_price": "0.109785",
        "last_updated_at": 1631836966
    },
    {
        "usd_price": "0.109712",
        "last_updated_at": 1631837443
    },
    {
        "usd_price": "0.109733",
        "last_updated_at": 1631837622
    },
    {
        "usd_price": "0.109826",
        "last_updated_at": 1631837967
    },
    {
        "usd_price": "0.110055",
        "last_updated_at": 1631838329
    },
    {
        "usd_price": "0.109855",
        "last_updated_at": 1631838688
    },
    {
        "usd_price": "0.110009",
        "last_updated_at": 1631838808
    },
    {
        "usd_price": "0.109744",
        "last_updated_at": 1631839192
    },
    {
        "usd_price": "0.109720",
        "last_updated_at": 1631839383
    },
    {
        "usd_price": "0.109713",
        "last_updated_at": 1631839744
    },
    {
        "usd_price": "0.109699",
        "last_updated_at": 1631839866
    },
    {
        "usd_price": "0.109913",
        "last_updated_at": 1631840403
    },
    {
        "usd_price": "0.109911",
        "last_updated_at": 1631840667
    },
    {
        "usd_price": "0.109694",
        "last_updated_at": 1631840889
    },
    {
        "usd_price": "0.110342",
        "last_updated_at": 1631841352
    },
    {
        "usd_price": "0.110452",
        "last_updated_at": 1631841596
    },
    {
        "usd_price": "0.111263",
        "last_updated_at": 1631841909
    },
    {
        "usd_price": "0.111517",
        "last_updated_at": 1631842205
    },
    {
        "usd_price": "0.111734",
        "last_updated_at": 1631842373
    },
    {
        "usd_price": "0.111802",
        "last_updated_at": 1631842761
    },
    {
        "usd_price": "0.111748",
        "last_updated_at": 1631843053
    },
    {
        "usd_price": "0.112613",
        "last_updated_at": 1631843404
    },
    {
        "usd_price": "0.112635",
        "last_updated_at": 1631844073
    },
    {
        "usd_price": "0.112636",
        "last_updated_at": 1631844188
    },
    {
        "usd_price": "0.112943",
        "last_updated_at": 1631844491
    },
    {
        "usd_price": "0.111538",
        "last_updated_at": 1631844880
    },
    {
        "usd_price": "0.111525",
        "last_updated_at": 1631844976
    },
    {
        "usd_price": "0.111698",
        "last_updated_at": 1631845491
    },
    {
        "usd_price": "0.111680",
        "last_updated_at": 1631845556
    },
    {
        "usd_price": "0.111570",
        "last_updated_at": 1631846061
    },
    {
        "usd_price": "0.112040",
        "last_updated_at": 1631846442
    },
    {
        "usd_price": "0.111997",
        "last_updated_at": 1631846671
    },
    {
        "usd_price": "0.111915",
        "last_updated_at": 1631846778
    },
    {
        "usd_price": "0.111823",
        "last_updated_at": 1631847297
    },
    {
        "usd_price": "0.111934",
        "last_updated_at": 1631847436
    },
    {
        "usd_price": "0.111546",
        "last_updated_at": 1631847834
    },
    {
        "usd_price": "0.111560",
        "last_updated_at": 1631848128
    },
    {
        "usd_price": "0.111458",
        "last_updated_at": 1631848439
    },
    {
        "usd_price": "0.111689",
        "last_updated_at": 1631848829
    },
    {
        "usd_price": "0.111678",
        "last_updated_at": 1631848937
    },
    {
        "usd_price": "0.111294",
        "last_updated_at": 1631849238
    },
    {
        "usd_price": "0.111037",
        "last_updated_at": 1631849734
    },
    {
        "usd_price": "0.111070",
        "last_updated_at": 1631849917
    },
    {
        "usd_price": "0.111395",
        "last_updated_at": 1631850299
    },
    {
        "usd_price": "0.111285",
        "last_updated_at": 1631850685
    },
    {
        "usd_price": "0.111460",
        "last_updated_at": 1631850856
    },
    {
        "usd_price": "0.111385",
        "last_updated_at": 1631851136
    },
    {
        "usd_price": "0.111520",
        "last_updated_at": 1631851476
    },
    {
        "usd_price": "0.111492",
        "last_updated_at": 1631851853
    },
    {
        "usd_price": "0.111684",
        "last_updated_at": 1631852018
    },
    {
        "usd_price": "0.111651",
        "last_updated_at": 1631852338
    },
    {
        "usd_price": "0.111641",
        "last_updated_at": 1631852754
    },
    {
        "usd_price": "0.111752",
        "last_updated_at": 1631852818
    }
]