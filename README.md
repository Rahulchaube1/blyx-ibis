<img src="assets/logo.png" width="112" height="112" alt="Ibis logo">

# Ibis

Reconcile an invoice with split payments in integer minor units. This Blyx workflow framework is part of the publishing and commerce collection.

Partial payments and overpayments must remain distinguishable when an invoice is reconciled. [GnuCash, accounts receivable](https://www.gnucash.org/docs/v5/C/gnucash-guide/bus_ar.html)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.1 https://github.com/Rahulchaube1/blyx-ibis.git
cd blyx-ibis
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-ibis) · [Package page](https://www.blyx-lang.space/packages/ibis) · [Handbook](https://doc.blyx-lang.space/guide/ibis)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.1 https://github.com/Rahulchaube1/blyx-ibis.git vendor/ibis
```

```blyx
use vendor::ibis::ibis;

fn main() {
    let units = [2, 1];
    let prices = [125, 50];
    let payments = [200, 125];
    let result = ibis_reconcile(units, prices, payments);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
300
300
0
25
```

## API

`ibis_reconcile(units, prices, payments)`

Returns [subtotal, applied payment, open balance, credit]. Use a single currency and already-posted amounts. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| units | Vector of values, each a nonnegative exact integer |
| prices | Vector of values, each a nonnegative exact integer |
| payments | Vector of values, each a nonnegative exact integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- "2,1" "125,50" "200,125"
```

## Libraries

- [LineAmount](https://github.com/Rahulchaube1/blyx-lineamount/tree/v0.1.1) — Extend paired invoice quantities and prices in integer minor units.
- [CashMatch](https://github.com/Rahulchaube1/blyx-cashmatch/tree/v0.1.1) — Apply posted payments and preserve customer credit separately.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-ibis/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The package artwork uses [Lucide icons](https://lucide.dev/license); see [artwork notices](assets/NOTICE.txt).

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
