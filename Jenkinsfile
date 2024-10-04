pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'
                # Activate the virtual environment
                python3 -m venv venv
                source venv/bin/activate
                pip3 install numpy
                pip3 install pandas
                pip3 install pytest
                pip3 install scikit-learn
                # Run pytest
                pytest
                # Deactivate the virtual environment
                deactivate
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
