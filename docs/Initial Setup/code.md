---
layout: default
title: Code
parent: Initial Setup
has_children: false
nav_order: 0
---

# Code
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Inline code

Code can be rendered inline by wrapping it in single back ticks.

<div class="code-example" markdown="1">
Lorem ipsum dolor sit amet, `<inline code snippet>` adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## Heading with `<inline code snippet>` in it.
{: .no_toc }
</div>
```markdown
Lorem ipsum dolor sit amet, `<inline code snippet>` adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## Heading with `<inline code snippet>` in it.
```

---

## Syntax highlighted code blocks

Use Jekyll's built-in syntax highlighting with Rouge for code blocks by using three backticks, followed by the language name:

<div class="code-example" markdown="1">
```rust 
fn parse_args(args: Vec<String>) -> Args {
    fn safe_index(vec: &Vec<String>, i: usize) -> Result<String, ()> {
        if i >= vec.len() {
            Err(())
        } else {
            Ok(vec[i].clone())
        }
    }

    let mut args_p = Args {
        test: None,
        fen: None,
    };

    let mut i = 1;

    loop {
        if args.len() <= i {
            break;
        }

        let arg = args[i].as_str();

        match arg {
            "--test" | "-t" => {
                i += 1;
                let test_arg = safe_index(&args, i).expect("specify the test");
                args_p.test = chess::get_test(test_arg);
                // let test_arg = args[i+1].as_str();
            }
            "--fen" | "-f" => {
                i += 1;
                let fen_arg = safe_index(&args, i).expect("specify the fen");
                args_p.fen = chess::parse_fen(fen_arg);
            }
            _ => {
                panic!("invalid argument: {}", arg);
            }
        }

        i += 1;
    }

    args_p
}

```
</div>
{% highlight markdown %}
```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```
{% endhighlight %}

---

## Code blocks with rendered examples

To demonstrate front end code, sometimes it's useful to show a rendered example of that code. After including the styles from your project that you'll need to show the rendering, you can use a `<div>` with the `code-example` class, followed by the code block syntax. If you want to render your output with Markdown instead of HTML, use the `markdown="1"` attribute to tell Jekyll that the code you are rendering will be in Markdown format... This is about to get meta...

<div class="code-example" markdown="1">

<div class="code-example" markdown="1">

[Link button](http://example.com/){: .btn }

</div>
```markdown
[Link button](http://example.com/){: .btn }
```

</div>
{% highlight markdown %}
<div class="code-example" markdown="1">

[Link button](http://example.com/){: .btn }

</div>
```markdown
[Link button](http://example.com/){: .btn }
```
{% endhighlight %}
