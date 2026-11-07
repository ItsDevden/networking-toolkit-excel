# DevDen Networking Toolkit — Excel

*Just THE Excel sheet that got slightly out of hand.*

The grandfather of DevDen Networking Toolkit.

This version is no longer maintained and should probably be ignored.

It's only here for the sake of the lore.

## The successors

### Web Version

[![Web Repository](https://img.shields.io/badge/GitHub-Web_Repository-487d79?style=flat-square&logo=github&logoColor=white)](https://github.com/ItsDevden/Networking-Toolkit-Web)

The current version. Runs in your browser, supports group collaboration and has significantly more features than a spreadsheet has any right to inspire.

### Desktop Version

[![Desktop Repository](https://img.shields.io/badge/GitHub-Desktop_Repository-775b86?style=flat-square&logo=github&logoColor=white)](https://github.com/ItsDevden/Networking-toolkit)

The Windows application that came after Excel, before I decided everything needed to run in a browser.

Both repositories contain more information about the actual toolkit and how it works.

## What's in this thing?

Not much compared to its successors.

- **VLSM Planner:** Calculates subnet prefixes, network addresses, usable host ranges and broadcast addresses.
- **Binary, Decimal and Hex Converters:** Converts values between number systems.
- **16-bit Binary Breakdown:** Displays individual bits for examining binary values.
- **Reset Buttons:** Because apparently clearing cells manually was too much work.

## For the nerds

### VLSM

The original reason this entire project exists.

The spreadsheet takes a starting network address and a list of required hosts, then calculates subnet allocations using powers of two.

For ordinary IPv4 LANs, the required block size is:

`2^ceil(log2(hosts + 2))`

The two additional addresses account for the network and broadcast addresses.

For example:

| Required hosts | Address block | Prefix |
|---|---|---|
| 50 | 64 | /26 |
| 25 | 32 | /27 |
| 10 | 16 | /28 |
| 5 | 8 | /29 |

Each subnet is allocated sequentially according to its block size.

The spreadsheet expects the host requirements **largest first**, without empty rows, and an appropriately aligned starting network address.

Unlike the newer versions, it doesn't automatically handle sorting and all the input validation.

It's Excel. Give it a break.

### Binary Breakdown

The spreadsheet also includes a 16-bit binary breakdown.

Each bit represents a power of two, starting at `2^15` and ending at `2^0`.

For example, the decimal number `192`:

`00000000 11000000`

Only two bits are enabled:

`128 + 64 = 192`

The breakdown makes it easier to see how binary values are constructed instead of just displaying the converted number.

This is particularly useful when learning subnetting, since IPv4 subnet masks and network boundaries are determined by individual bits.

For example, the last octet of a `/26` subnet mask is:

`11000000 = 192`

Which gives us:

`255.255.255.192`

The same principle applies when calculating network and host portions of an IPv4 address.

### Binary, Decimal and Hex

The spreadsheet includes converters between three number systems:

- **Binary (base 2):** Uses `0` and `1`.
- **Decimal (base 10):** Uses `0–9`.
- **Hexadecimal (base 16):** Uses `0–9` and `A–F`.

For example, the same value represented three ways:

| Number system | Value |
|---|---|
| Binary | 11000000 |
| Decimal | 192 |
| Hexadecimal | C0 |

Nothing revolutionary, but pretty useful when you're learning networking and need to understand what the numbers actually represent.

## Running it

Download the `.xlsm` file and open it in Microsoft Excel.

Some features use VBA macros. Only enable macros if you've reviewed the file and trust its source.

But seriously, use one of the newer versions instead.

## Copyright & Usage

Copyright © 2026 DenDev. All rights reserved.

This project is preserved as an archive of the original DevDen Networking Toolkit.

The source is publicly available for viewing and educational reference. No license is granted to copy, modify, redistribute or commercially exploit the software without prior written permission, except as permitted by applicable law and GitHub's Terms of Service.

For permissions or licensing inquiries, contact the repository owner.
