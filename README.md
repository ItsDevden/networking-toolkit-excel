# Networking Toolkit

## Why did I make this instead of using an online tool?

I’m studying to become a data technician. On a slow day at school, I wanted to challenge myself and see if I could build the tools I needed in Excel. I made this workbook for myself, learned a bit along the way, and now I use it because I’m lazy enough to automate the calculations. 😄

## What’s in it?

- Binary, decimal and hexadecimal conversion
- A 16-bit binary breakdown
- A VLSM subnet planner that calculates prefixes, network IDs, first and last usable IPs, and broadcast addresses
- Reset buttons for clearing inputs

## Using the VLSM planner

Enter a **starting network ID**, then enter the number of hosts needed for each subnet, **largest first**, with no empty rows between them. The workbook calculates the address ranges automatically.

The starting network ID must be aligned to the first subnet. The planner does not check whether all subnets fit inside a larger network you’ve been assigned.

## Macros

This is an `.xlsm` workbook. It contains VBA code for IP address calculations and the reset buttons, so macros need to be enabled for those features to work.

If Windows blocks the macros after downloading the workbook:

1. Close Excel.
2. Right-click the downloaded `.xlsm` file → **Properties**.
3. On the **General** tab, tick **Unblock** near the bottom, then click **Apply**.
4. Open the workbook again and enable macros if Excel asks.

Only enable macros in a workbook whose code you trust.

Feel free to use this workbook, change it, or build on it however you want.

## License

MIT
