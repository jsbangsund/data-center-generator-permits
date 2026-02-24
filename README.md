# Data center generator permits
Data and analysis of back-up power and generators for data centers extracted from air quality permits.

If you find this data useful, please reference our report on diesel generators used for data centers:
Casomar, C., & Bangsund, J. (2026). *A community guide: Limiting harm from diesel generators at data centers*. Better Data Center Project.

Currently, this repository only contains data from Virginia. More states may be added in the future.

# Notes, limitations, and known issues

 - Virginia air permits submitted up to 12/31/2025 have been analyzed. Permits were taken from the VA Department of Environmental Quality website: https://www.deq.virginia.gov/news-info/shortcuts/permits/air/issued-air-permits-for-data-centers
 - US EPA emissions Tier assignments (in column `tier`) were best guesses based on permitted emission limits, original permit date, and types of emissions controls. 
    - Distinguishing between Tier 1 and Tier 2 units is difficult, because the standards phased in over several years and the EPA's emissions limits are load-weighted while permits list maximum emissions at 100% load. 
    - Units that have SCR but no DPF, cDPF, or DOC are labeled "Tier 2 + SCR". 
    - Units with SCR and cDPF or DPF are labeled Tier 4.
 - For VA data, we classified some independent cities as being in the county they are surrounded by (e.g. Manassas and Prince William). Full address information can be found in the `site_location` column.
 - In the `equipment_type` column, we distinguish between "emergency" vs. "non-emergency" gensets. In VA, only Tier 4 compliant gensets can be "non-emergency", which allows them to be used outside of unplanned outages and maintenance.
 - `fuel_throughput_limit_raw`: Many files do not specify a fuel throughput limit. Others provide an equation to weight the fuel consumption of each type of genset. We left this blank for either case because of the complexity of capturing this in a spreadsheet.

## License

The data of this project is licensed under the [Creative Commons Attribution 4.0 license (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/), and the accompanying analysis and visualization code is licensed under the [MIT license](LICENSE.md).