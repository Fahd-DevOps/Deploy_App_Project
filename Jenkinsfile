node('kube-agent') {
        stage("CD:"){
            
         container('deployer'){
             
            stage("Clone Git Repository") {
          
                git(
                    url: "https://github.com/Fahd-DevOps/Deploy_App_Project",
                    branch: "main",
                    changelog: true,
                    poll: true
                )
             }
                  stage("Deploy the app") {
                      
                     sh """
                     kubectl apply -f deploy-app/deployment.yaml
                     kubectl apply -f deploy-app/app-service.yaml
                     kubectl apply -f deploy-app/app-ingress.yaml
                     """
             }
        }
    }
}