## Reconcile split invoice payments

Returns [subtotal, applied payment, open balance, credit]. Use a single currency and already-posted amounts. Invalid arguments and nonfinite results return an empty vector.

1. Open an empty file named `ibis-demo.blyx`.
2. Type `blyx-ibis-demo` and select **Ibis — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
300
300
0
25
```

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-ibis)
