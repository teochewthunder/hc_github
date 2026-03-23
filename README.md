# HighCharts GitHub Contribution Chart
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
  - convert to integer values and create a two-dimensional array of these values. Assign to `currentData` array.
  - obtain the minimum and maximum values of the `Year` column.
  - use the minimum and maximum values in a `For` loop to populate the `yearSeriesData` array from `currentData` array.
  - set all range sliders and outputs to minimum value.
  - run `renderLineChart()`.
- `setYear()`
  - has `target` as a parameter. The value is either "from" or "to".
  - if "from":
    - if the new value of `rngYearFrom` is greater than the current value of `rngYearTo`, set `rngYearTo`'s value to be the same as `rngYearFrom`'s.
  - if "to":
    - if the new value of `rngYearTo` is lesser than the current value of `rngYearFrom`, set `rngYearFrom`'s value to be the same as `rngYearTo`'s.
  - run `renderLineChart()`.
- `monthToName()`
  - has `month` as a parameter. This is an integer from 1 to 12.
  - declare an array of month names.
  - use `month` - 1 as a reference to that array, and return the element's value.
- `renderLineChart()`
  - get values of range sliders `rngYearFrom` and `rngYearTo` and checkbox `cbSeparateYears`.
  - declare `dataset` and populate it using a subset from `currentData`, using values of `rngYearFrom` and `rngYearTo` as lower and upper limits.
  - declare `commits` as an array of all the third column data values of `dataset`
  - if `cbSeparateYears` is checked:
    - make `series` an array of elements from `yearSeriesData`.
    - labels on x-axis should show only month.
  - if `cbSeparateYears` is not checked:
    - make `series` an array of one object with`commits` as the data.
    - labels on x-axis should show month and year.
  - display chart using `series`.

