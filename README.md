WebAssembly
===========

DSL for creating html structure straight with Elixir blocks:

```Elixir
    
    use WebAssembly
    builder do
      html do
        head do
          ctype = "text/html"
          meta http_equiv: "Content-Type", content: ctype
          title "foo"
        end
        body do
          div class: "mydiv" do
            ul do
              li 1
              if all_goes_well, do:
                li "second"
            end
          end
          text "that was nice"
        end
      end
    end
```

This results in a deeply nested list (aka Erlang iolist)
which you can flatten or send directly to the socket
(via Plug & Cowboy for example).
 
Loosely inspired by [Markaby](https://github.com/markaby/markaby).
