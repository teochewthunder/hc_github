# HighCharts Line Chart for GitHub commits (TBA)
HighCharts code for displaying dynamic Line Chart from imported CSV.

## HTML
- container for chart.
- checkbox `cbSeparateYears`.
  - runs `renderLineChart()`.
- range slider `rngYearFrom`. (includes output `opYearFrom`)
  - runs `setYear()` with argument "from".
- range slider `rngYearTo`. (includes outout `opYearTo`)
  - runs `setYear()` with argument "to".
 
## CSS
- for alignment and aesthetics. No related functionality.

## JavaScript 
- onLoad
  - xx
  - xx
  - xx
- `setYear()`
  - has `target` as a parameter. THe value is either "from" or "to".
  - if "from"
    - if the new value of `rngYearFrom` is greater than the current value of `rngYearTo`, set `rngYearTo`'s value to be the same as `rngYearFrom`'s.
  - if "to"
    - if the new value of `rngYearTo` is lesser than the current value of `rngYearFrom`, set `rngYearFrom`'s value to be the same as `rngYearTo`'s.
  - run `renderLineChart()`.
- `monthName()`
  - xx
  - xx
  - xx
- `renderLineChart()`
  - xx
  - xx
  - xx

