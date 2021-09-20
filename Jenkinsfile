pipeline {
    agent none

    stages {
        stage("Parallel stage") {

            //myglobal = ["pro1.py", "pro2.py", "pro3.py"];

            parallel {
                stage("step 1") {
                    agent {
                        label "my-slave1"
                    }
                    steps {
                        script {
                            println("abcdefg");
                            println(PYTHON_QUEUE);

                            sh """
                                python pro1.py
                            """

                        }
                        
                    }
                }

                stage("step 2") {
                    agent {
                        label "agent2"
                    }
                    steps {
                        script {
                            println("zzzzzzzzz")
                            println(PYTHON_QUEUE);
                            sh """
                                python pro2.py
                            """
                        }
                    }
                }
            }
        }
    }
}
