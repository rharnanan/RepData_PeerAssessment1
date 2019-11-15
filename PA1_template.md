#### Loading in the data.

    data <- read.csv("activity.csv",as.is = TRUE)

#### Remove N/A values and sum

    data1 <- data[!is.na(data$steps),]

    data1steps<- with(data1, tapply(steps, as.factor(data1$date), sum, na.rm = T))

### What is mean total number of steps taken per day?

![](PA1_template_files/figure-markdown_strict/unnamed-chunk-3-1.png)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##      41    8841   10765   10766   13294   21194

### What is the average daily activity pattern?

![](PA1_template_files/figure-markdown_strict/unnamed-chunk-4-1.png)

### Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps?

835
---

### The total number of missing values is 2304

### What is mean total number of steps taken per day after N/A’s are replaced

![](PA1_template_files/figure-markdown_strict/unnamed-chunk-8-1.png)

    summary(datacleansteps)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##      41    9819   10766   10766   12811   21194

The values do differ when N/A’s are populated but the impact is only on
the lower step intervals

### Activity Patern Weekday and Weekend

![](PA1_template_files/figure-markdown_strict/unnamed-chunk-11-1.png)

’’’{r} library(knitr) knit2html(“PA1\_template”)
browseURL(“PA1\_template”) \`\`\`
