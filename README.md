# demo_wc
## in a spark env we could user sparkContext to do word count job.
-------
sc.textFile("wc_input").flatMap(\_.split(" ")).map((\_,1)).reduceByKey(\_ + \_).repartition(1).sortByKey().saveAsTextFile("wc_outputs")

## TODO: median
# val nums = sc.textFile("wc_input").map(line => line.split(" ").count).collect() // count the number of each line's word, and collect them into a seq.
# var sum = 0
# for num in nums:
#    var s = seq.slice(0, num) //add 1 number into sub-seq each time and calculate the median for that sub-seq.
#    if s.count % 2 == 0:
#        val l = s.count / 2 - 1
#        val r = l + 1
#        yield (s.lookup(l).head + s.lookup(r).head).toDouble / 2
#    else:
#        yield s.lookup(s.count / 2).head.toDouble
# // write the yeild seq back to files, each element as a line.
