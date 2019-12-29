# Demo of PHP Monolog / Logstash / Unomaly
3.8.176.245
35.177.30.231
This project demonstrates pushing your PHP application logs to Unomaly.

See the [Unomaly documentation](https://docs.unomaly.com/how-to-send-data-to-unomaly) for help in sending other data to Unomaly.  

## Installing Unomaly

Unomaly offers simple instructions in their [documentation](https://docs.unomaly.com/installation-overview).

They offer a [free license](https://unomaly.com/pricing) for up to 10 sources, as well as a free trial for your entire infrastructure.  

The instance sizing that they provide is suitable for production and is not eligible for free tier.

## Running the project

You can run the project by running these commands:

    cd docker
    docker-compose up -d
    docker exec -it php /bin/bash
    composer install
    
And then visit `http://localhost:8000` in your browser.  

Logstash will push to your Unomaly instance, and also to stdout (your docker logs) to help you debug.  You can remove output to stdout in production. 

## Grokking your own logs

These sites are very useful:

* https://grokdebug.herokuapp.com/
* https://github.com/logstash-plugins/logstash-patterns-core/blob/master/patterns/grok-patterns
* https://github.com/kkos/oniguruma/blob/master/doc/RE

Oniguruma lets you use regex in the Grok pattern, like this: `(?<field_name>the pattern here)`