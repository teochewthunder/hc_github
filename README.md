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
  - grab data from CSV.
  - convert to integer values and create a two-dimensional array of these values.
  - obtain the minimum and maximum values of the `Year` column.
  - use the minimum and maximum values in a `For` loop to populate the `yearSeriesData` array.
  - set all range sliders and outputs to minimum value.
  - run `renderLineChart()`.
- `setYear()`
  - has `target` as a parameter. The value is either "from" or "to".
  - if "from"
    - if the new value of `rngYearFrom` is greater than the current value of `rngYearTo`, set `rngYearTo`'s value to be the same as `rngYearFrom`'s.
  - if "to"
    - if the new value of `rngYearTo` is lesser than the current value of `rngYearFrom`, set `rngYearFrom`'s value to be the same as `rngYearTo`'s.
  - run `renderLineChart()`.
- `monthToName()`
  - has `month` as a parameter. This is an integer from 1 to 12.
  - declare an array of month names.
  - use `month` - 1 as a reference to that array, and return the element's value.
- `renderLineChart()`
  - xx
  - xx
  - xx

