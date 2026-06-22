pipeline {
    agent none
    stages {
        stage("Parallel Build & Test") {
            parallel {
                stage("Build on Agent1") {
                    agent{ label 'agent1'}
                    steps {
                        bat 'echo Agent1 빌드 수행 중'
                    }
                }
                stage("Build on Agent2") {
                    agent{ label 'agent2'}
                    steps {
                        bat 'echo Agent2 빌드 수행 중'
                    }
                }
            }    
        }
    }
}