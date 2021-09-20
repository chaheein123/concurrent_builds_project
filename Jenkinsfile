pipeline {
    agent none

    stages {
        stage("Parallel stage") {

            parallel {
                stage("step 1") {
                    agent {
                        label "my-slave1"
                    }
                    steps {
                        sh """
                            python pro1.py
                        """
                    }
                }

                stage("step 2") {
                    agent {
                        label "agent2"
                    }
                    steps {
                        sh """
                            python pro2.py
                        """
                    }
                }
            }
        }
    }
}