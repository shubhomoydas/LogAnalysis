# WeblogChallenge

Project in Scala for analyzing log data from Amazon cloud server.

To compile:

    mvn compile

To build JAR:

    mvn package

To run (make a folder 'output' in order for output files to be generated):

    spark-submit --master local[4] target/WeblogChallenge-0.1.0-jar-with-dependencies.jar <operation> [ip address]
    
The command line options are:

    - operation: [0|1|2|3|4|5|6]
    
        0: generate url / user profile data -- outputs file(s) in 'output' folder \
            showing users with longest sessions, etc.
        
        1: generate transition data -- generated transition probability tables for \
            all users. Probably not required. But useful for debug.
        
        2: generate transition data and simulate arbitrary user navigation -- \
            in addition to generating the transition probabilities, \
            also simulates navigation. This is also not really required unless debugging.
        
        3: simulate navigation for a client IP (requires ip address) -- Extracts all \
            logs for a particular IP and builds transition probability tables. Then \
            simulates the user (say) 200 times and reports average session length, \
            average number of unique urls, average number of total urls per session.
        
        4: generate time series data for server load -- useful to inspect and understand \
            server load charactaristics.
        
        5: generate server load data for regression -- useful only if we have lots of \
            data over multiple years. Usefulness is mostly moot at this point for this project.
        
        6: predict load for next minute -- Basically average of last 5 minutes load. \
            The predictions match quite well with true values. see: \
            https://github.com/shubhomoydas/WeblogChallenge/blob/master/docs/predicted_server_load.pdf
        
    - ip address: client IP -- required only for operation 3 (above).
