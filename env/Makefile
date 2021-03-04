init:
	helm init --client-only --stable-repo-url=https://mirror.azure.cn/kubernetes/charts/
	helm repo add jenkins-x http://192.168.20.143:8080/cm
	helm repo add bitnami https://charts.bitnami.com/bitnami
	# helm repo add stable https://charts.helm.sh/stable

build: clean init
	jx step helm build --boot --provider-values-dir=../kubeProviders
	helm lint .

clean: 
	rm -rf charts
	rm -rf requirements.lock
