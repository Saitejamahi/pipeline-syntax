pipeline {
  agent any
  stages {
    stage('install niginx') {
      steps {
        // Install Nginx
        sh 'sudo apt update'
        sh 'sudo apt install -y nginx'
      }
    }

    stage('delete default page') {
      steps {
        // Delete default Nginx web page
        sh 'sudo rm -rf /var/www/html/*'
      }
    }

    stage('host nginx') {
      steps {
        // Copy your ecomm files to the Nginx web directory
        sh 'sudo cp -rf ecomm/* /var/www/html'
      }
    }

    stage('restart nginx') {
      steps {
        // Restart Nginx service
        sh 'sudo systemctl restart nginx'
      }
    }
  }
}
