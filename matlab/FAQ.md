
### Q1. how to exactly match the result of cumulative distribution function and quantile function?

As we know, quantile function is the inverse cumulative distribution function.

Then for a existed distribute(a vector), how to exactly match the result of cumulative distribution function and quantile function?

Here is an example given in MATLAB.

    ```MATLAB
    a = [150   154   151   153   124]
    [x_count, x_val] = hist(a, unique(a));
    % compute the probability cumulative distribution 
    p = cumsum(n)/sum(n);
    x_out = quantile(a, p)
    ```

We will found result of x_out is

    x_out =

      137.0000  150.5000  152.0000  153.5000  154.0000

But not 

   124   150   151   153   154

1. [quantile function](https://en.wikipedia.org/wiki/Quantile_function)
2. [matlab quantile function](http://nl.mathworks.com/help/stats/quantile.html#responsive_offcanvas)

