# E邮宝(Epacket、EUP)、E包裹、E特快、国际EMS物流轨迹查询

[![Build Status](https://img.shields.io/travis/slince/shipment-tracking-ems/master.svg?style=flat-square)](https://travis-ci.org/slince/shipment-tracking-ems)
[![Coverage Status](https://img.shields.io/codecov/c/github/slince/shipment-tracking-ems.svg?style=flat-square)](https://codecov.io/github/slince/shipment-tracking-ems)
[![Latest Stable Version](https://img.shields.io/packagist/v/slince/shipment-tracking-ems.svg?style=flat-square&label=stable)](https://packagist.org/packages/slince/shipment-tracking-ems)
[![Scrutinizer](https://img.shields.io/scrutinizer/g/slince/shipment-tracking-ems.svg?style=flat-square)](https://scrutinizer-ci.com/g/slince/shipment-tracking-ems/?branch=master)

中国邮政包裹物流信息查询，适用产品E邮宝、E包裹、E特快、国际EMS

## Installation

Install via composer

```bash
$ composer require slince/shipment-tracking-ems
```
## Basic Usage


```php

$tracker = new Slince\ShipmentTracking\EMS\EMSTracker(AUTHENTICATE, 'en');

try {
   $shipment = $tracker->track('CNAQV100168101');
   
   print_r($shipment->getEvents());  //print the shipment events
   
} catch (Slince\ShipmentTracking\Exception\TrackException $exception) {
    exit('Track error: ' . $exception->getMessage());
}

```
注意：该库并不支持查询国内EMS包裹信息，相关文档主页[http://shipping.ems.com.cn/apiIndex](http://shipping.ems.com.cn/apiIndex)

## License
 
The MIT license. See [MIT](https://opensource.org/licenses/MIT)

