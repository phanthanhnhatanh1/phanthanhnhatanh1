<script src="https://static.stringee.com/web_phone/lastest/js/StringeeSoftPhone-lastest.js"></script>
<script>
    var config = {
        showMode: 'full',//full | min | none
        top: 45,
        left: 50,
        //right: 810,

        arrowLeft: 155,
        arrowDisplay: 'top',//top | bottom | none

        //list your Stringee Number
        fromNumbers: [{alias: 'Number-1', number: '+84899199586'}, {alias: 'Number-2', number: '+2222'}]
    };
    StringeeSoftPhone.init(config);

    var access_token2 = 'YOUR_ACCESS_TOKEN';

    StringeeSoftPhone.on('displayModeChange', function (event) {
        console.log('displayModeChange', event);
        if (event === 'min') {
            StringeeSoftPhone.config({arrowLeft: 75});
        } else if (event === 'full') {
            StringeeSoftPhone.config({arrowLeft: 155});
        }
    });

    StringeeSoftPhone.on('requestNewToken', function () {
        console.log('requestNewToken+++++++');
        StringeeSoftPhone.connect(access_token2);
    });

    StringeeSoftPhone.connect(access_token2);
</script>
