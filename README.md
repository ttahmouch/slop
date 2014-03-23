Slop
====

This module is meant to be an overly simple, c(S)ommand Line Options Parser.

## Installation

    npm install slop --save

## Usage

    /**
     * Module dependencies.
     */
    var slop = require('slop');
    /**
     * Process.argv will be an array.
     * Array:
     *  1st element will be 'node'
     *  2nd element will be '/path/to/this/JavaScript/file'
     *  3rd - Nth elements will be additional command line arguments
     *
     * Introspect Node arguments vector for:
     * - optional port to begin accepting connections
     *
     * Options.get() values may yield:
     * - {undefined}
     * - {boolean} true
     * - {string} (non-empty)
     *
     * Options.has() values may yield:
     * - {boolean} true
     * - {boolean} false
     */
    var options = slop().parse(process.argv),
        port = options.get('port'),
        debug = options.has('debug');
    /**
     * Default the Port value if it's not defined.
     */
    port = (typeof port === 'string' && Number(port) >= 0) ? port : '8080';

    if (debug) {
        console.log('------------------------------');
        console.log('Incoming Option Values.');
        console.log('Port: ' + port);
        console.log('------------------------------');
    }

## Tests

No unit tests are currently present. Eventually:

    npm test

## Contributing

In lieu of a formal style guideline, take care to maintain the existing coding style.

## Release History

+ 0.0.1 Initial release
