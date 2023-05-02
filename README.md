# WiniPayer - Client PHP API

PHP package to use and verify payments via WiniPayer

## Official website

https://www.winipayer.com

## Installation

Install the PHP library via composerer

    require 'ngomory/winipayer'

## Class initialization

    <?php

    require_once 'vendor/autoload.php';

    use Ngomory\WiniPayer;

    $WiniPayer = new WiniPayer(
        'test',
        '0ShrTtBMC15buIGwu593',
        '275307e6-6532-479a-a954-77331a875d65',
        '4128123b4ff44e72881165279bda10b1'
    );

## Create invoice for paiement

    $WiniPayer->setItems(
            [
                [
                    'name' => 'Pot de fleure',
                    'quantity' => 2,
                    'unit_price' => 3650,
                    'total_price' => 7300
                ]
            ],
            ...
        )
        ->setCancelUrl('https://tester.winipayer.com')
        ->setReturnUrl('https://tester.winipayer.com/success')
        ->setCallbackUrl('https://tester.winipayer.com/ipn')
        ->createInvoice(100, "La description ici ...")
