#!/bin/bash

if [[ ${KUBECONFIG} == "" ]]
then
    echo "Please export KUBECONFIG env variable before running script!!!"
    exit 1
else
    echo "Current value of KUBECONFIG --> [${KUBECONFIG}]"
fi

export $(xargs <.env)

cd "03-1-ingress-nginx"
helm dependency update
helm upgrade -i init-ingress-nginx . -f values-${ENV}.yaml -n ingress-nginx --create-namespace
cd ..
