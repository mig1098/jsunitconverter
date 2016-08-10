# jsunitconverter
Simple JS unit conversion lib.

This is the library I wrote here:
http://stackoverflow.com/questions/865590/unit-of-measure-conversion-library/3531444#3531444

Just moved into github so it's actually versioned somewhere.

# Usage

This library handles all the SI conversions for grams, bytes, meters and liters, and also I've added ounces and pounds as an example of non-SI units. To add more, you'll need to:

Add the base type to the "units" list for items that follow SI or
Add the conversion ratios for items that don't follow SI
Usage:

$u(1, 'g').as('kg').val(); // converts one gram to kg
You can get the value out with .val(), a string representation using .toString() or the full details via .debug()

# Examples

console.log($u(1, 'g').as('kg').debug());  
console.log($u(1, 'kg').as('g').debug());
console.log($u(1, 'g').as('mg').debug());
console.log($u(1, 'mg').as('g').debug());
console.log($u(1, 'mg').as('kg').debug());

console.log($u(1, 'g').as('oz').debug());
console.log($u(1, 'g').as('lb').debug());

console.log($u(1, 'oz').as('lb').debug());

console.log($u(1, 'lb').as('g').debug());

// this last one throws an exception since you can't convert liters to mg
console.log($u(1, 'l').as('mg').debug());
