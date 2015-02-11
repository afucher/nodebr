# Assert

    Stability: 5 - Locked

This module is used for writing unit tests for your applications, you can
access it with `require('assert')`.

## assert.fail(actual, expected, message, operator)

Throws an exception that displays the values for `actual` and `expected` separated by the provided operator.

## assert(value[, message]), assert.ok(value[, message])

Tests if value is truthy, it is equivalent to `assert.equal(true, !!value, message);`

## assert.equal(actual, expected[, message])

Tests shallow, coercive equality with the equal comparison operator ( `==` ).

## assert.notEqual(actual, expected[, message])

Tests shallow, coercive non-equality with the not equal comparison operator ( `!=` ).

## assert.deepEqual(actual, expected[, message])

Tests for deep equality.

## assert.notDeepEqual(actual, expected[, message])

Tests for any deep inequality.

## assert.strictEqual(actual, expected[, message])

Tests strict equality, as determined by the strict equality operator ( `===` )

## assert.notStrictEqual(actual, expected[, message])

Tests strict non-equality, as determined by the strict not equal operator ( `!==` )

## assert.throws(block[, error][, message])

Espera `block` para lançar um erro. `error` pode ser construtor, `RegExp` ou função de validação.

Validar instanceof usando construtor:

    assert.throws(
      function() {
        throw new Error("Wrong value");
      },
      Error
    );

Validar mensagem de erro usando RegExp: 

    assert.throws(
      function() {
        throw new Error("Wrong value");
      },
      /value/
    );

Validação de erro personalizada:

    assert.throws(
      function() {
        throw new Error("Wrong value");
      },
      function(err) {
        if ( (err instanceof Error) && /value/.test(err) ) {
          return true;
        }
      },
      "unexpected error"
    );

## assert.doesNotThrow(block[, message])

Expects `block` not to throw an error, see `assert.throws` for details.

## assert.ifError(value)

Tests if value is not a false value, throws if it is a true value. Useful when
testing the first argument, `error` in callbacks.
