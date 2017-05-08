# Omnigrid

A responsive grid framework using variable row columns and minimal base element styling.

Traditional responsive grids limit you to a set number of columns per row, typically 12 or 16.
Omnigrid allows you to define the number of columns you want in a particular row.
Each row can contain between 1 and 16 columns.

This is my first github project so any feedback or contributions are welcome.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

None, unless you want to compile the css in which case you will need Less.

* [Less](http://lesscss.org) - CSS pre-processor

### Installing

As the project grows there may be some javascript enhancements but for now only the css file needs to be included.

```
<link rel="stylesheet" href="omnigrid.css" />
```

## How to Use

Start with the grid container. This can be standard or full width.

```
<div class="grid">

</div>

-- or --

<div class="grid-full">

</div>
```

Then add your rows and define the number of columns per row for each device.
Device sizes are: sm (small), md (medium), lg (large), and xl (extra large).

```
<div class="grid">
  <div class="row sm-6 md-9 lg-12 xl-16">
    
  </div>
</div>
```

Then add your columns. The columns widths must add up to the number of defined columns within the row for that device.

```
<div class="grid">
  <div class="row sm-6 md-9 lg-12 xl-16">
    <div class="col sm-1 md-4 lg-2 xl-4">
      Column 1
    </div>
    <div class="col sm-3 md-2 lg-6 xl-8">
      Column 2
    </div>
    <div class="col sm-2 md-3 lg-4 xl-4">
      Column 3
    </div>
  </div>
</div>
```

You can also rearrange the columns depending on the device.
The positioning is a combination of push/pull and offset to simplify the grid creation.

This may change in the future but for now here's how you do it.
You will have to take into consideration the column's width and the available number of columns within the row.

Consider the small device. There are 6 columns available.
Starting positions would be 1, 2, 3, 4, 5, and 6.
Column widths are 1, 3, and 2.
Say we wanted to put Column 2 first, Column 3 second, and Column 1 last.
If you're going to set positioning of one column then you'll need to set the positioning of the rest of the columns.
We would position like so.

```
<div class="grid">
  <div class="row sm-6 md-9 lg-12 xl-16">
    <div class="col sm-1 sm-pos-6 md-4 lg-2 xl-4">
      Column 1
    </div>
    <div class="col sm-3 sm-pos-1 md-2 lg-6 xl-8">
      Column 2
    </div>
    <div class="col sm-2 sm-pos-4 md-3 lg-4 xl-4">
      Column 3
    </div>
  </div>
</div>
```

There are also various visibility classes available.

```
Hide or make invisible on a particular device.
.{device}-hide
.{device}-invisible

Only show on a particular device. Hide on other devices.
.{device}-show-block
.{device}-show-inline
.{device}-show-inline-block

Only show on a particular device. Make invisible on other devices.
.{device}-show-block-iv
.{device}-show-inline-iv
.{device}-show-inline-block-iv

Various print classes.
.print-hide
.print-invisible
.print-block
.print-inline
.print-inline-block
```

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/gcoxdev/omnigrid/tags). 

## Authors

* **Gary** - *Initial work* - [gcoxdev](https://github.com/gcoxdev)

See also the list of [contributors](https://github.com/gcoxdev/omnigrid/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* [Normalize.css](https://necolas.github.io/normalize.css/)
* [Bootstrap](http://getbootstrap.com/)
* [Foundation](http://foundation.zurb.com/)
* [Stackoverflow](http://stackoverflow.com/)
* All developers on the web that contribute, help, and advise others on various websites and forums.
