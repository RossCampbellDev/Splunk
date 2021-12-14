# Splunk
## Splunk cheat sheet and learning
## importing data
### local file
log into splunk -> Add Data -> Upload -> Select File (.zip)
configure Input Settings (probably leave source type as automatic)
can use regex or a part of the path in the data to define a 'host' for each item

### remote (using forwarder)

## analysing data
### using SPL, Search Processing Language
specify source data if required:  `source="filename.zip:*"`

using regex, can 'find in item' eg look for `error*` or `fail*` to find any log entries etc that contain words like error, errored, fail, failure, failed

criteria can be piped in the manner of a command line instruction

### stats
`| stats` can be combined with other keywords to help us quantify things, for example:
`| stats count by col1, col2, col3` is analogous to an SQL COUNT statement combined with GROUP BY

### sort
we can pipe to the sort command to order by a column, using a hyphen to indicate descending order
`| sort col1` / `| sort - col1`

### where
`| where count > 1`
`| where col1 in("a", "b", "c")`

### regex
for more advanced filtering than 'where'
`| regex col1="abc.*"`

## Visualising Data
click on a selected field to the left of the data window on the events screen
we can click 'top values by name' or any of the other options to generate a simple report

we can also type into the search bar to generate charts
`| timechart count by col1 limit=10`

### format
we can change the format of the visualisation to glean more from it, using the links above the chart (eg change to bar chat, volume... change axes and notation... etc)

### narrowing down data sets
we can click on one of the values on the chart legend to add it to the filter in the search bar

### table
`| table col1, col2, col3`

#IOC #IOI #IR #SOC #dataanalysis #networking #cheatsheet
