node() {
stage("Clone"){
    git url: 'https://github.com/nataliyavoronova0304/testjenk.git'
}


stage("Deploy"){
    withCredentials([usernamePassword(credentialsId: 'Demo123', passwordVariable: 'CF_PASSWD', usernameVariable: 'CF_USER')]) {
        bat "cf api https://api.cf.eu10.hana.ondemand.com"
        bat "cf login -u $CF_USER -p $CF_PASSWD"
        bat "cf push"
        bat "cf apps"
    }

}
}
