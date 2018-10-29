node() {
stage("Clone"){
    git url: 'https://github.com/nataliyavoronova0304/testjenk.git'
}


stage("Deploy"){
    withCredentials([usernamePassword(credentialsId: 'Demo123', passwordVariable: 'CF_PASSWD', usernameVariable: 'CF_USER')]) {
        sh "cf api https://api.cf.eu10.hana.ondemand.com"
        sh "cf login -u $CF_USER -p $CF_PASSWD"
        sh "cf push"
        sh "cf apps"
    }

}
}
