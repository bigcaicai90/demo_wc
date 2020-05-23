# demo_wc
## in a spark env we could user sparkContext to do word count job.
-------
sc.textFile("wc_input").flatMap(\_.split(" ")).map((\_,1)).reduceByKey(\_ + \_).repartition(1).sortByKey().saveAsTextFile("wc_outputs")

## TODO: median
