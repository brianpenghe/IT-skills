---
title: 'some R notes'
date: 2017-04-18T19:27:00.002-07:00
draft: false
url: /2017/04/some-r-notes.html
---

> **Archived note — originally created: 2017-04-18 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


# # # [Convert a dataframe to matrix](http://blog.163.com/bsbfans@126/blog/static/456628242012102841341628/ "阅读全文")

data.matrix {base}

R Documentation

Convert a Data Frame to a Numeric Matrix
----------------------------------------

# # # Description

Return the matrix obtained by converting all the variables in a data frame to numeric mode and then binding them together as the columns of a matrix. Factors and ordered factors are replaced by their internal codes.

# # # Usage

```
data.matrix(frame, rownames.force = NA)
```

# # # Arguments

`frame`

a data frame whose components are logical vectors, factors or numeric vectors.

`rownames.force`

logical indicating if the resulting matrix should have character (rather than `NULL`) `[rownames](http://stat.ethz.ch/R-manual/R-patched/library/base/html/colnames.html)`. The default, `NA`, uses `NULL` rownames if the data frame has ‘automatic’ row.names or for a zero-row data frame.

# # # Details

Logical and factor columns are converted to integers. Any other column which is not numeric (according to `[is.numeric](http://stat.ethz.ch/R-manual/R-patched/library/base/html/numeric.html)`) is converted by `[as.numeric](http://stat.ethz.ch/R-manual/R-patched/library/base/html/numeric.html)` or, for S4 objects, `[as](http://stat.ethz.ch/R-manual/R-patched/library/methods/html/as.html)(, "numeric")`. If all columns are integer (after conversion) the result is an integer matrix, otherwise a numeric (double) matrix.

# # # Value

If `frame` inherits from class `"data.frame"`, an integer or numeric matrix of the same dimensions as `frame`, with dimnames taken from the `row.names` (or `NULL`, depending on `rownames.force`) and `names`.

Otherwise, the result of `[as.matrix](http://stat.ethz.ch/R-manual/R-patched/library/base/html/matrix.html)`.

# # # Note

The default behaviour for data frames differs from **R** < 2.5.0 which always gave the result character rownames.

# # # References

Chambers, J. M. (1992) _Data for models._ Chapter 3 of _Statistical Models in S_ eds J. M. Chambers and T. J. Hastie, Wadsworth & Brooks/Cole.

# # # See Also

`[as.matrix](http://stat.ethz.ch/R-manual/R-patched/library/base/html/matrix.html)`, `[data.frame](http://stat.ethz.ch/R-manual/R-patched/library/base/html/data.frame.html)`, `[matrix](http://stat.ethz.ch/R-manual/R-patched/library/base/html/matrix.html)`.

# # # Examples

```
DF <- data.frame(a=1:3, b=letters\[10:12\], c=seq(as.Date("2004-01-01"), by = "week", len = 3), stringsAsFactors = TRUE)data.matrix(DF\[1:2\])data.matrix(DF)
```

# # # Generate heat map based on a matrix  

image(1-temp, col=heat.colors(20,alpha=1))

# # # Draw a curve using R. curve() function  

e.g

\> curve(dnorm(x,mean=1.3/11, sd=sqrt(2/11)),-5,5, col = "green")

\> curve(dnorm(x,mean=0, sd=sqrt(2)),-5,5,add=TRUE, col = "red")

\> curve(dnorm(x,mean=1.3/10, sd=sqrt(2/10)),-5,5,add=TRUE, col = "black")

\> curve(dnorm(x,mean=1.3/(10+1/18), sd=sqrt(2/(10+1/18))),-5,5, col = "green")

\> curve(dnorm(x,mean=0, sd=sqrt(18)),-5,5,add=TRUE, col = "red")

\> curve(dnorm(x,mean=1.3/10, sd=sqrt(2/10)),-5,5,add=TRUE, col = "black")

#R #TroubleshootNotes #BloggerPublishedNonAcademicNotes
