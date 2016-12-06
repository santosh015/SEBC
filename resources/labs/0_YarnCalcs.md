```
The number of maps is determined by the number of input splits as far as I know so I'm not sure mapreduce.job.maps is used unless we are using non-file based jobs.

the max containers based on vCores would be a good setting 512. We couldn't use 872 based on memory because we would hit the CPU limit first. Of course then you would have to be creating enough data to make full use of this.

What criteria affects workload factor? What does a value of 1, 2, or 4 signify?

The values 1, 2 and 4 is basically to increase the mappers and reducers.It just multiplies the number.So if we have enough numbers nodes and resources available this can be adjusted.

```
