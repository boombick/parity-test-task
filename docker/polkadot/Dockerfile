FROM ubuntu:18.04

RUN mkdir /polkadot
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://github.com/paritytech/polkadot/releases/download/v0.7.30/polkadot -o /polkadot/polkadot
RUN chmod +x /polkadot/polkadot
EXPOSE 30333 9933 9944
CMD [ "/polkadot/polkadot",  "--name",  "AndreyTestNode"]