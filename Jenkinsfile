pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Checkout source code from Git repository
                git 'https://github.com/dimosko/jenkins-hello-world.git'
                
                // Build step using GCC
                sh 'gcc -o hello hello-world.c'
            }
        }

        stage('Execute') {
            steps {
                // Execute the compiled program
                sh './hello'
            }
        }

         stage('build rdk') {
            steps {
                // Execute the compiled programs
                sh 'cd'
                sh 'cd dr-yocto'
                sh "docker run -it -v $PWD:/public/Work dr-yocto:18.04 bash -c 'cd rdk_aml-next-tv && source meta-obs-aml/setup-environment 18 && bitbake lib32-rdk-generic-hybrid-image'"
            }
        }
    }
}