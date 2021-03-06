![](https://github.com/chouj/RectRange/blob/master/rectrange.jpg)

# RectRange
a MATLAB function for obtaining coordinate range of a selected rectangle in figure 

**Warning!** Do not use this function upon your final prepared/optimized figure, because it will manipulate Axes Aspect Ratio.

```[Xrange,Yrange]=rectrange(xgrid,ygrid,f)``` lets you select a rectangle in the current figure using the mouse. The figure has to be generated based on a rectangle grid (X, Y) which is usually produced by using function ```MESHGRID```. Then the coordinate ranges of the selected rectangle (Not its position.Thus, its different from function ```GETRECT```) based on grid (xgrid,ygrid) will be derived.This would be useful when you have a map generated based on grids of longitudes latitudes and want to know longitude/latitude range of a certain region. However, this function won't work when the map is produced by using M_Map toolbox due to projection issues.

#### Inputs
```xgrid,ygrid``` - The rectangle grid on which the figure bases. Usually, they
              are generated by ```[xgrid,ygrid]=meshgrid(xgv,ygv)```. See 
              *meshgrid.m*.
              
```f```           - The handle of the figure. For exmaple, ```f = figure;```

```'precise'```   - Default output mode. The precise coordinate ranges will be
              obtained no matter there are intervals between grid points.
              
```'nearest'```   - Other than 'presice', the coordinate ranges of your 
              selected rectangle in x- and y-direction will be derived 
              from 4 grid points close to each vertex of the rectangle.

#### Outputs
```Xrange```      - The range of selected rectangle in x-direction.

```Yrange```      - The range of selected rectangle in y-direction.

For example,
```matlab
     [X,Y,Z] = peaks;
     f=figure;
     contourf(X,Y,Z,'linestyle','none');
     axis equal
     [rx,ry]=rectrange(X,Y,f);
```
One can test this function by uncommenting lines 106, 107, 125-128, 133-134 and 145. The rectangle you selected and its two vertices will be drawn in your figure.

2018/07/29

## Support Me

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/Mesoscale)
[![Donate](https://img.shields.io/badge/Donate-WeChat-brightgreen.svg)](https://github.com/chouj/donate-page/blob/master/simple/images/WeChatQR.jpg?raw=true)
[![Donate](https://img.shields.io/badge/Donate-AliPay-blue.svg)](https://github.com/chouj/donate-page/blob/master/simple/images/AlipayQR.jpg?raw=true)
