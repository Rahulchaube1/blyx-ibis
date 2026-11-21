# Blyx Ibis

Reconcile an invoice with split payments in integer minor units.

This extension includes the Blyx Ibis 0.1.1 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Run in the editor

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

## Use Ibis in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/ibis`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-ibis-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-ibis-starter-0.1.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/ibis) · [Framework source](https://github.com/Rahulchaube1/blyx-ibis/tree/e007a9495559a3cdfe086ac27b4b758874112094) · [Report an issue](https://github.com/Rahulchaube1/blyx-ibis/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
