node{

    stage('SCM Checkout')
    {
        git credentialsId: '2eb89954-3865-494c-a688-28aac7800aa4', url: 'https://github.com/Aadi16/Devops.git'
    }
    
    stage('Run Docker Compose File')
    {
        bat 'runas.exe /user:administrator "docker-compose build"'
        bat 'runas.exe /user:administrator "docker-compose up -d"'
    }
  stage('PUSH image to Docker Hub')
    {
      /* withCredentials([string(credentialsId: 'DockerHubPassword', variable: 'DHPWD')]) 
        {
            sh "docker login -u upasanatestdocker -p ${DHPWD}"
        }
        sh 'docker push vardhanns/phpmysql_app'
        */
        //docker.withRegistry( 'https://registry.hub.docker.com', 'DockerHubPassword' ) {
             
             bat 'runas.exe /user:administrator "docker login -u "aadi1601" -p "Aaditya@16_01" docker.io"'
             //sh 'sudo docker push upasanatestdocker/mysql'
             //sh 'sudo docker push upasanatestdocker/job1_web1.0'
             bat 'runas.exe /user:administrator "docker push aadi1601/project1"'
            // sh 'docker push upasanatestdocker/mysql'
          
    }
}
