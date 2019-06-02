node {
   
   stage('GITCODE'){
      git credentialsId: 'GIT', url: 'https://github.com/Ipshita-Pal/centos7docker.git'
   }


    stage('DOCIMAGE'){
    sh label: '', script: 'docker build -t ipshita/centos7web:v1 .'

}

    stage('DOCPUSH'){
    //withCredentials([usernamePassword(credentialsId: 'DOC', passwordVariable: 'pwd', usernameVariable: 'user')])
    withCredentials([usernamePassword(credentialsId: 'DOC', passwordVariable: 'pwd', usernameVariable: 'user')])
    {
     sh "docker login -u $user -p $pwd"
    }
     
     sh 'docker push ipshita/centos7web:v1'
}
}
