Telnet
======

Forked from https://github.com/miyahan/Telnet.    
Telnet client written in php   

## Upgrades from the original

- Gets full response even when the terminal don't show all the data, only prompts the `--More--`
- Added login to TL1 protocol 

## Description

- Telnet to Linux/UNIX servers
- Telnet to network routeres (Cisco IOS , Juniper JUNOS, Xtreme XOS, Dlink, BDcom)
- Telnet to olt (Nokia, Digistar, Phyhome)    

## Requirement

- PHP 5.6 or later (PHP 7.0 ready!)   


## Usage

### Telnet to Cisco IOS router

```php
try {
    $telnet = new \meklis\network\Telnet('10.0.0.1');
    $telnet->connect();
    $telnet->login('foo', 'bar', 'cisco');
    $telnet->exec('terminal length 0');
    $telnet->exec('enable'."\r\n".'foobar');
    $telnet->setPrompt('router#');
    
    $result = $telnet->exec('show env all');
    echo $result."\n";
} catch (Exception $e) {
    echo $e->getMessage();
}
```


## Installation

Use composer (https://packagist.org/packages/meklis/telnet)


## License

MIT

