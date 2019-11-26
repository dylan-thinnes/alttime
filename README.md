# alttime

`alttime` is a simple framework for defining your own time / calendar
specifications. This is just a little experiment in using the date time library
and writing thin frameworks in bash, if you have improvements I welcome them!

I also welcome any new time definitions.

## Usage

Create a calendar/time definition file, e.g. `mycal`.

```
touch mycal
```

Create bash functions `year`, `month`, `day`, `dayofweek`, `hour`, `minute`,
`second` for each type you want to override. Let's say you have a calendar that
always has the year 1234.

```
year () {
    echo 1234
}
```

Then, run your definition using the alttime script, passing in the command
you'd like executed from the second argument onwards.

```
$ ./alttime mycal altyear # Prints the alternate year
1234
```

If you pass no arguments after the definition, the full time is written as
`YYYY/MM/DD (W), HH:MM:SS`

```
$ ./alttime mycal # Prints the full time, which will only have the year changed
1234/11/26 (2), 10:11:16
```

## International Fixed Calendar

I've created a sample spec of the [International Fixed
Calendar](https://en.wikipedia.org/wiki/International_Fixed_Calendar) in
intfixed. Use it thus:

```
$ ./alttime intfixed # Prints the full time, which will only have the date changed
2019/12/22 (1), 10:11:16
```
