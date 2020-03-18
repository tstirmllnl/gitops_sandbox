FROM argoproj/argocd:latest

# Switch to root for the ability to perform install
USER root

# Install tools needed for your repo-server to retrieve & decrypt secrets, render manifests 
# (e.g. curl, awscli, gpg, sops)
# RUN apt-get update && \
#     apt-get install -y \
#         ansible


RUN pip3 install \
	PyYAML==3.12\
	openshift>=0.6 \
	ansible 

USER argocd