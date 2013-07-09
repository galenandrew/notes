# Advanced Date/Time
@author Derick Rethans @derickr
@date 2013-06-29
@url joind.in/8702

## Timezones
- Multiple different exceptions to timezones in US due to rules and voting elections as well as Daylight Savings
- TZID - Time Zone Identifier (eg America/Chicago)
- PECL `timezonedb` extension provides a drop in replacement for timezone database
- `timezone_identifiers_list()` returns all TZIDs for region (continent, country, etc)

### Default Timezones
- Set in PHP.ini, .htaccess or start of script

## DateTime Objects
- `strtotime()` only returns a timestamp (e.g. 1268012901) and gets formatted based on the default timezone
- Better to use DateTime object (> PHP 5.2) `new DateTime("…")`
- `parse_date()` parses date strings similar to `strtotime()` but will tell your errors and returns more info (**GREAT FUNCTION**)

### Formatting
- example 08/03/10 (Aug 3, 2010 - 8 March, 2010 - 2008 March 10)
- `DateTime::createFromFormat()` lets you specify format to parse the date to solve issues like above

### Modifying
- `modify("+ 2 days")` NOTE: called on DateTime object will actually modify the original object AND return the modified object (use DateTime immutable instead)

### Intervals
- `DateInterval` has full and abbreviated notation
- when formatting diff b/w 2 dates there are 2 day formats. `%a` returns *total count of days* (e.g. 45 days) and `%d` returns *total days in month* (e.g. 1 month 15 days)

### Relative Time
- `2010-01-31` bumped to "next month" returns `2010-03-03` because prev/next month increases month number by 1 then overflows the days (e.g. `2010-01-31` -> `2010-02-31` -> `2010-03-03`)

### Periods
- e.g. "third tuesday of every month"

## Storing Date/Time
*Goal to store time exactly 4 months in the future*
- never a good idea to store as **timestamp** and **UTC offset** because you will not be able to convert back to local time
- store **timestamp** and **tzid** OR **datetime** and **tzid** is a better solution

### Querying across timezones
- store as timestamp and tzid, use PHP to convert from local time range to timestamp then use as query WHERE.

## Further Reading
"php|architect's Guide to Date and Time Programming"