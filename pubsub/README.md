```javascript

function fn1( value ) {
  console.log( value );
  return false;
}
 
function fn2( value ) {
  fn1( "fn2 says: " + value );
  return false;
}

$.PubSub( "mailArrived" ).subscribe( fn1 );
$.PubSub( "mailArrived" ).subscribe( fn2 );
$.PubSub( "mailSent" ).subscribe( fn1 );
 
// Publisher
$.PubSub( "mailArrived" ).publish( "hello world!" );
$.PubSub( "mailSent" ).publish( "woo! mail!" );
```
