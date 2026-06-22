pipeline {
    agent none
    stages {
        stage("Parallel Build & Test") {
            Parallel {
                stage("Build on Agent1") {
                    agent{ albel 'agent1'}
                    steps {
                        bat 'echo Agent1 빌드 수행 중'
                    }
                }
                stage("Build on Agent2") {
                    agent{ albel 'agent2'}
                    steps {
                        bat 'echo Agent2 빌드 수행 중'
                    }
                }
            }    
        }
    }
}