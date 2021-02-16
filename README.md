Function to convert strings to their NATO phonetic alphabet equivalents.

This is a simplified version of the `StrSpell()` function in the `DescTools` package: https://cran.r-project.org/web/packages/DescTools/index.html

```
nato <- function(x) {
    y <- factor(strsplit(x, "")[[1]], levels = c(LETTERS, letters, 0:9))
    lett <- c("Alfa", "Bravo", "Charlie", "Delta", "Echo", "Foxtrot", "Golf", "Hotel", "India", 
              "Juliett", "Kilo", "Lima", "Mike", "November", "Oscar", "Papa", "Quebec", "Romeo", 
              "Sierra", "Tango", "Uniform", "Victor", "Whiskey", "Xray", "Yankee", "Zulu")
    numb <- c("Zero", "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine")
    levels(y) <- c(paste(lett), lett, numb)
    return(as.character(y))
}

# nato("District9")
# [1] "Delta"   "India"   "Sierra"  "Tango"   "Romeo"   "India"   "Charlie" "Tango"   "Nine" 
```
