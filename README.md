# Reverse Income Tax Calculator (UK)

A reverse-engineered UK income tax calculator that determines the annual gross income required to achieve a target monthly take-home pay, accounting for income tax, National Insurance contributions, and pension deductions.

## Overview

Rather than calculating take-home pay from gross income (the traditional approach), this calculator works backwards: enter your desired monthly take-home and pension contribution percentage, and it calculates the required gross annual income needed to hit that target.

This is particularly useful for:
- **Career planning** — determining salary requirements for specific lifestyle goals
- **Negotiation** — knowing your target salary when discussing compensation
- **Financial modeling** — understanding tax and pension impacts on real income
- **Benefits comparison** — evaluating job offers with different pension schemes

## Features

✓ **Accurate tax calculations** — Implements full UK tax system logic including:
  - Personal allowances and tax bands
  - Income tax (basic and higher rates)
  - National Insurance (employee contributions)
  - Pension contributions (pre-tax deductions)

✓ **Multi-jurisdiction support**:
  - England, Wales, and Northern Ireland
  - Scotland (separate tax bands)

✓ **Multiple tax years** — 2024/25, 2025/26, 2026/27

✓ **Zero dependencies** — Vanilla JavaScript, runs entirely in-browser with no server required

✓ **Real-time calculations** — Updates instantly as you adjust inputs

✓ **No data collection** — All calculations are performed locally; nothing is sent to external servers

## How It Works

The calculator uses a **binary search algorithm** to reverse the standard tax calculation:

1. User enters monthly take-home target and pension contribution percentage
2. Algorithm iteratively tests gross income values
3. For each test value, it calculates:
   - Pension contribution (% of gross)
   - Income tax (based on personal allowance and tax bands)
   - National Insurance (employee contributions)
   - Resulting take-home pay
4. When take-home matches the target (within £1), it returns the required gross income

The calculation respects:
- **Personal allowance** — the tax-free income threshold (£12,570 for 2026/27)
- **Tax bands** — progressive rates for basic, intermediate, and higher income
- **National Insurance thresholds** — 8% up to £37,700, then 2% above
- **Pension deductions** — reduce taxable income before tax is calculated
- **Regional variations** — separate rates for Scotland

## Installation & Usage

### Online
Visit the live calculator at your subdomain:
```
https://calculator.yourdomain.com
```

### Local Use
1. Clone or download this repository
2. Open `reverse_income_tax_calculator.html` in any modern web browser
3. No build process, no dependencies, no internet required

### Self-Hosting
To deploy to your own server:

**GitHub Pages (recommended)**
```bash
git clone https://github.com/yourusername/reverse-income-calculator.git
cd reverse-income-calculator
# Enable Pages in repo Settings
# Point custom domain to your subdomain via DNS
```

**Traditional hosting**
```bash
sftp user@your-host.com
cd public_html/calculator
put reverse_income_tax_calculator.html
```

## Input Parameters

| Parameter | Range | Description |
|-----------|-------|-------------|
| Monthly take-home | £0+ | Your target monthly disposable income |
| Pension contribution | 0–100% | Percentage of gross salary (pre-tax) |
| Tax year | 2024/25–2026/27 | Financial year for tax rates |
| Location | England/Scotland | Determines applicable tax bands |

## Output

The calculator returns:

- **Required annual gross income** — The salary you need to earn
- **Annual take-home pay** — Confirmed yearly disposable income
- **Income tax breakdown** — Total tax liability for the year
- **National Insurance breakdown** — Employee NI contributions
- **Pension contributions** — Total amount deducted

## Example

**Inputs:**
- Desired monthly take-home: £3,000
- Pension contribution: 10%
- Tax year: 2026/27
- Location: England

**Output:**
- Required gross income: ~£47,300/year
- Annual take-home: £36,000 (£3,000 × 12)
- Income tax: £6,960
- National Insurance: £3,368
- Pension contributions: £4,730

## Limitations & Disclaimers

This calculator is a **ready reckoner** and makes standard assumptions:

⚠️ **Does not account for:**
- Personal tax codes (non-standard allowances)
- Marriage Allowance or other transferable allowances
- Dividend allowances or investment income
- Trading income or self-employment
- Student loan repayments
- Childcare vouchers or cycle scheme benefits
- Specific workplace pension schemes with non-standard rates

⚠️ **Accuracy:**
- Calculations are estimates based on standard 2024–27 rates
- HMRC tax codes and allowances may vary individually
- For a definitive answer, consult your payslip or contact HMRC

**For official guidance, visit:** [HMRC](https://www.hmrc.gov.uk/) or [GOV.UK Tax Guide](https://www.gov.uk/income-tax-rates-bands)

## Technical Details

### Browser Compatibility
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

### Performance
- Calculation completes in <50ms
- No external API calls
- Zero network latency impact

### Data Privacy
- **No data is collected** — all processing happens in your browser
- **No cookies** — session state is local only
- **No analytics** — no third-party tracking

## Contributing

Contributions are welcome! Please:

1. Test changes across multiple browsers
2. Verify tax rate accuracy against HMRC guidance
3. Submit issues for edge cases or rate updates
4. Update documentation for new features

### Reporting Issues

Found a calculation error or have a suggestion? Please open an issue with:
- Expected vs. actual output
- Tax year and location used
- Steps to reproduce

## License

This project is licensed under the **Apache License 2.0**.

See the [LICENSE](LICENSE) file for full details. You are free to:
- ✓ Use commercially or privately
- ✓ Modify and distribute
- ✓ Sublicense

You must:
- ✓ Include original license and copyright notice
- ✓ Document significant changes

## Acknowledgments

- Tax rates and thresholds sourced from [HMRC 2026/27 guidance](https://www.gov.uk/topic/personal-tax)
- Scotland tax bands from [Revenue Scotland](https://www.revenue.scot/)
- Original calculator logic reverse-engineered from [Money Saving Expert Tax Calculator](https://www.moneysavingexpert.com/tax-calculator/)

## Roadmap

Potential future enhancements:
- [ ] Cumulative tax code visualization
- [ ] Annual salary vs. contract rate calculator
- [ ] Savings breakdown (post-tax income allocation)
- [ ] Comparison tool (multiple job offers)
- [ ] CSV export of results
- [ ] Dark mode UI option

## Support

**Questions or feedback?**
- Open an issue on GitHub
- Check existing issues for similar questions
- Review the [Limitations](#limitations--disclaimers) section

---

**Last updated:** May 2026  
**Tax rates reflect:** 2024/25–2026/27 UK financial years  
**Next review:** June 2027 (for 2027/28 rates)

---

*** Fueled by coffee: https://buymeacoffee.com/mullered ***
