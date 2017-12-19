erlang protobuf example
=====

Build
-----
    $ cd example
    $ rebar3 compile
    
Run
-----
    $ rebar3 shell

```erlang
Erlang/OTP 19 [erts-8.3.5] [source] [64-bit] [smp:16:16] [async-threads:0] [hipe] [kernel-poll:false]

Eshell V8.3.5  (abort with ^G)
1> rr(example_pb).
['HelloWorld',field,gpb_oneof,rpc]
2> l(example_pb).
{module,example_pb}
3> example_pb:encode_msg(#'HelloWorld'{message_id = 1, content = "hello, world!"}).
   <<8,1,18,13,104,101,108,108,111,44,32,119,111,114,108,100,
     33>>
4> example_pb:decode_msg(v(3), 'HelloWorld').
#'HelloWorld'{message_id = 1,content = <<"hello, world!">>}
```
    
