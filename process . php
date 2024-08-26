<?php
require 'vendor/autoload.php';
use Twilio\Rest\Client;

// Collect data from the form
$name = $_POST['name'];
$phone = $_POST['phone'];
$address = $_POST['address'];

// Twilio credentials
$sid = 'ACab0f86721bdfe2427b00d6af376fde7d'; // Replace with your Twilio Account SID
$token = '4fd7e169c32843aef11e5edc352ce87e'; // Replace with your Twilio Auth Token
$twilio = new Client($sid, $token);

// Initiate call verification
$call = $twilio->calls->create(
    $phone, // The user's phone number
    '+your_twilio_number', // Your Twilio phone number
    array(
        'twiml' => '<Response><Gather action="/handle_response.php" method="POST">
                      <Say>Thank you for your order. Press 1 to confirm your order or 2 to cancel.</Say>
                    </Gather>
                    <Say>We did not receive any input. Goodbye!</Say>
                    </Response>'
    )
);

echo "Payment successful. A verification call has been placed. Call SID: " . $call->sid;
?>
