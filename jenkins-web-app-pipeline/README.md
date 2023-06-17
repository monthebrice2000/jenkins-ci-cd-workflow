# Project I: Build pipelines for Continuous integration, continuous delivery and continuous deployment with Jenkins Docker

<!---Esses são exemplos. Veja https://shields.io para outras pessoas ou para personalizar este conjunto de escudos. Você pode querer incluir dependências, status do projeto e informações de licença aqui--->

![GitHub repo size](https://img.shields.io/github/repo-size/iuricode/README-template?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/iuricode/README-template?style=for-the-badge)
![GitHub forks](https://img.shields.io/github/forks/iuricode/README-template?style=for-the-badge)
![Bitbucket open issues](https://img.shields.io/bitbucket/issues/iuricode/README-template?style=for-the-badge)
![Bitbucket open pull requests](https://img.shields.io/bitbucket/pr-raw/iuricode/README-template?style=for-the-badge)

<img src="./jenkins.webp" alt="exemplo imagem">

> ce projet présente les exemples de contruction des pipelines pour build et déployer nos applications sur le cloud azure de facon continue sans oublier de gérer l'intégration continue, la livraison continue et le déploiement continue avec l'outil <a href="https://www.jenkins.io/doc/">Jenkins</a>.


## Installation de jenkins via docker

```
docker run --name jenkins-dockerr --rm --detach --privileged --network jenkins --network-alias docker --env DOCKER_TLS_CERTDIR=/certs --volume jenkins-docker-certs:/certs/client --volume jenkins-data:/var/jenkins_home --publish 8080:8080 jenkins/jenkins:2.401.1
```

## Results

<img src="pipeline.PNG" alt="exemplo imagem">
<img src="jenkins-ci-cd-workflow.PNG" alt="exemplo imagem">
<img src="jenkins-docker.PNG" alt="exemplo imagem">



<!-- # Build resources with terraform and deploy to azure active directory

<img src="https://raw.githubusercontent.com/monthebrice2000/github-actions-ci-cd-workflow/master/2-one.png" alt="exemplo imagem">
<img src="https://raw.githubusercontent.com/monthebrice2000/github-actions-ci-cd-workflow/master/2-two.png" alt="exemplo imagem"> -->

