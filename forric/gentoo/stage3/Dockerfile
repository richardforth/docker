FROM gentoo/stage3:latest

# Disable all sandbox features
ENV FEATURES="-sandbox -usersandbox -ipc-sandbox -network-sandbox -pid-sandbox -mount-sandbox"
ENV EMERGE_DEFAULT_OPTS="--jobs=2 --load-average=2"

# Fix Portage directory layout
RUN mkdir -p /etc/portage/package.accept_keywords

# Add keyword for apache
RUN echo 'www-servers/apache ~amd64' > /etc/portage/package.accept_keywords/apache

# Sync Portage and install packages
RUN emerge-webrsync && \
    emerge --sync && \
    emerge --verbose --update --deep --newuse @world && \
    emerge --ask=n \
        net-misc/curl \
        sys-process/procps \
	sys-apps/iproute2 \
        www-servers/apache \
        dev-lang/perl
