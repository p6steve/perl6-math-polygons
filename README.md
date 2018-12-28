# perl6-Math-Polygons
Some perl6 polygon objects that draw using SVG - this is an alpha with the ultimate goal of proper inheritance of Parallelograms, Rhomboids, etc.

# Instructions
There are three intended ways to use this repo:
1. Jupyter Notebook local
- Clone this repo locally on your machine
- Do the Quick Start here Brian Duggan perl6 jupyter-notebook at <https://github.com/bduggan/p6-jupyter-kernel>
- From the root directory run *jupyter-notebook*
2. Jupyter Notebook hosted (wip)
- Paste the github url at <mybinder.org>, then the Dockerfile will be used to build and run on jupyter
3. Perl6 Module (wip)
- *zef install Math::Polygons*

# Synopsis
```perl6
use SVG::Drawing;
use Math::Polygons;

my $rectangle = Rectangle.new( 
    origin => Point.new(20, 20),
    width  => 120, 
    height => 80  
);

my $square = Square.new( 
    origin => Point.new(170, 20),
    side   => 100 
);

my \A = Point.new( 20, 260);
my \B = Point.new( 30, 200);
my \C = Point.new(120, 145);
my \D = Point.new(125, 250);
my $quadrilateral = Quadrilateral.new(
    A, B, C, D,  
);

my $triangle = Triangle.new(
    fill => "green",
    stroke => "black",
    apex => Point.new(220, 160),
    side => 100 
);

my $drawing = SVG::Drawing.new( 
    elements => [ 
        $rectangle, 
        $square,
        $quadrilateral,
        $triangle,
    ],
);
$drawing.serialize.say;
```

# Inspired by
* Brian Duggan's perl6 jupyter-notebook at <https://github.com/bduggan/p6-jupyter-kernel>
* Christopher Stowe's perl6 advent calendar [Christmas Tree](https://perl6advent.wordpress.com/2018/12/18/day-18-an-svg-christmas-tree/)