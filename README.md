# WeblogChallenge

Project in Scala for analyzing log data from Amazon cloud server.

To compile:

    mvn compile

To build JAR:

    mvn package

To run:

    spark-submit --master local[4] target/WeblogChallenge-0.1.0-jar-with-dependencies.jar <operation> [ip address]
    
The command line options are:

    - operation: [0|1|2|3|4|5|6]
    
        0: generate url / user profile data; 
        
        1: generate transition data; 
        
        2: generate transition data and simulate arbitrary user navigation
        
        3: simulate navigation for a IP; 
        
        4: generate time series data for server load
        
        5: generate server load data for regression
        
        6: predict load for next minute
        
    - ip address: client IP
