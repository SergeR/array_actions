# array_actions
> Set of simple actions with arrays

## Installation

To get the latest version of `array_actions`, simply require the project using Composer:

``` shell
$ composer require kamyshev/array_actions
```

## Usage

### array_find

To use `array_find`, simply pass an array and callback:

``` php
$records = [
    [
        'state'  => 'IN',
        'city'   => 'Indianapolis',
        'object' => 'School bus',
    ],
    [
        'state'  => 'IN',
        'city'   => 'Indianapolis',
        'object' => 'Manhole',
    ],
    [
        'state'  => 'IN',
        'city'   => 'Plainfield',
        'object' => 'Basketball',
    ],
    [
        'state'  => 'CA',
        'city'   => 'San Diego',
        'object' => 'Light bulb',
    ],
    [
        'state'  => 'CA',
        'city'   => 'Mountain View',
        'object' => 'Space pen',
    ],
];

$grouped = array_find($records, function ($state) {
    return $state['city'] === 'San Diego';
});
```

Example output:

``` text
Array
(
    [state] => CA
    [city] => San Diego
    [object] => Light bulb
)
```

If the element was not found, `array_find` returns `null`.
