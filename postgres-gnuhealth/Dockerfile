FROM postgres:10.6
# Use our local cache
#RUN echo 'Acquire::http { Proxy "http://apt-cacher:9999"; };' >> /etc/apt/apt.conf.d/01proxy

ENV DUMPFILE="gnuhealth-34-demo.sql.gz"
ENV SQLFILE="demo.sql.gz"

#VOLUME /var/lib/postgresql
# RUN apt-get update && apt-get install -y --no-install-recommends \
# 	gzip curl ca-certificates \
# 	&& rm -rf /var/lib/apt/lists/* \
# 	&& curl -o /$SQLFILE -SL "https://www.gnuhealth.org/downloads/postgres_dumps/$DUMPFILE" \
# 	# && tar --extract --file=$DUMPFILE $SQLFILE \
# 	# && gzip -c $SQLFILE > demo.sql.gz \
# 	# && rm $DUMPFILE \
# 	&& apt-get purge -y --auto-remove curl ca-certificates

COPY gnuhealth.sh /docker-entrypoint-initdb.d/
