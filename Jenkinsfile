pipeline {
    agent {
	label "deploy"}




	stages{
        stage ("Git checkout "){
            steps{
        git branch: 'main', 
            url: 'https://github.com/WassimBA/Kubernetes.git'
     	       }
           }
	 stage('deploy mysql'){
        steps{
	dir("config"){
	sh 'kubectl apply -f deploy-sql.yaml '
		}
	}
}
         stage('deploy app'){
        steps{
	dir("config"){
        sh 'kubectl apply -f deploy-app.yaml '
        	}
	}
}



     }

}
