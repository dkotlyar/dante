FROM wernight/dante

RUN apk add -U build-base linux-pam-dev

# make pam_pwdfile.so
COPY libpam-pwdfile.zip /tmp/

RUN unzip -q /tmp/libpam-pwdfile.zip -d /tmp/ \
    && cd /tmp/libpam-pwdfile \
    && make install \
    && rm -rf /tmp/libpam-pwdfile \
    && rm -f /tmp/libpam-pwdfile.zip

RUN apk add -U mariadb-dev

# make pam_pwdfile.so
COPY pam_mysql-0.7RC1.tar.gz /tmp/

RUN cd /tmp \
    && tar xzf pam_mysql-0.7RC1.tar.gz \
    && cd /tmp/pam_mysql-0.7RC1 \
    && ./configure \
    && make install \
    && rm -rf /tmp/pam_mysql-0.7RC1 \
    && rm -f /tmp/pam_mysql-0.7RC1.tar.gz

