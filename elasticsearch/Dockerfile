ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELASTIC_VERSION}



#
#ADD ./src/test/resources/models/en-ner-persons.bin /usr/share/elasticsearch/config/ingest-opennlp/
#ADD ./src/test/resources/models/en-ner-locations.bin /usr/share/elasticsearch/config/ingest-opennlp/
#ADD ./src/test/resources/models/en-ner-dates.bin /usr/share/elasticsearch/config/ingest-opennlp/
#
#ENV ES_SETTING_INGEST_OPENNLP_MODEL_FILE_NAMES=en-ner-persons.bin
#ENV ES_SETTING_INGEST_OPENNLP_MODEL_FILE_LOCATIONS=en-ner-locations.bin
#ENV ES_SETTING_INGEST_OPENNLP_MODEL_FILE_DATES=en-ner-dates.bin
#
#ADD build/distribution/elasticsearch-ingest-opennlp.zip /elasticsearch-ingest-opennlp.zip

COPY config/stopFilter.txt config/stopFilter.txt
COPY config/synonymsFilter.txt config/synonymsFilter.txt
COPY config/user_dictionary.txt config/user_dictionary.txt


#COPY plugin/doo-plugin-7.15.1.zip plugin/doo-plugin-7.15.1.zip
COPY plugin/kr-danalyzer-8.4.1.zip plugin/kr-danalyzer-8.4.1.zip
COPY plugin/rest-handler-8.4.zip plugin/rest-handler-8.4.zip
#COPY plugin/ingest-opennlp-8.4.1.1.zip plugin/ingest-opennlp-8.4.1.1.zip
#COPY plugin/payload-score-0.1.zip plugin/payload-score-0.1.zip

RUN elasticsearch-plugin install analysis-nori

#RUN elasticsearch-plugin install file:///usr/share/elasticsearch/plugin/doo-plugin-7.15.1.zip
RUN elasticsearch-plugin install file:///usr/share/elasticsearch/plugin/kr-danalyzer-8.4.1.zip
RUN elasticsearch-plugin install file:///usr/share/elasticsearch/plugin/rest-handler-8.4.zip
#RUN elasticsearch-plugin install file:///usr/share/elasticsearch/plugin/ingest-opennlp-8.4.1.1.zip
#RUN #elasticsearch-plugin install file:///usr/share/elasticsearch/plugin/payload-score-0.1.zip
# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu
