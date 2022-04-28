---
layout: tutorial
title: Pigs Example
permalink: /tutorial/pigs/
redirect_from: /tutorial/pigs.html
example_url: /notebooks/pigs/
---
This example includes the following concepts in Tisane:

 - `SetUp`, `Unit`, `Numeric`, and `Ordinal` variables.
 - the `causes` conceptual relationship, and
 - the `nests_within` data relationship.

If you want to run this example yourself, check it out in the [Tisane repository](https://github.com/emjun/tisane/tree/main/examples/Animal_Science)!

<iframe src="/notebooks/pigs.html" id="target" frameborder="0" scrolling="no" style="width:100%;" markdown="0"></iframe>

<script markdown="0">
    // Increase the height of the iframe
    var div = document.getElementById("target");
    div.onload = function() {
        div.style.height =
          div.contentWindow.document.body.scrollHeight + 'px';
    }
</script>
