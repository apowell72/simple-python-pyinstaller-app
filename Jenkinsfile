pipeline {
    agent none // (1)
    stages {
        stage('Build') { // (2)
            agent {
                docker {
                    registryUrl 'atas-docker.atas.gtri.org'
                    image 'hraps-docs-dev' // (3)
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' // (4)
                stash(name: 'compiled-results', includes: 'sources/*.py*') // (5)
            }
        }
    }
}