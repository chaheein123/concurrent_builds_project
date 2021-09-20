pipeline {
    agent none

    stages {

        stage("Variables declar") {
            steps {
                script {
                    yo = ["pro1.py", "pro2.py", "pro3.py"]
                }
                
            }
            
        }



        stage("Parallel stage") {

            parallel {
                while (yo.size() > 0) {
                    stage("step 1") {
                        agent {
                            label "my-slave1"
                        }
                        steps {
                            script {
                                println("abcdefg");
                                println(yo);
                                yo.pop();

                                sh """
                                    python pro1.py
                                """

                            }
                            
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
                            println(yo);
                        }
                    }
                }
            }
        }
    }
}
