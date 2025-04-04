pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                echo "In C or Java, we can compile our program in this step"
                echo "In Python, we can build our package here or skip this step"
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                
                echo "Activating virtual environment and dependencies"
                . mlip/bin/activate
                pip install pytest
                pip install numpy
                pip install pandas
                pip install scikit-learn
                echo "Running Test"
                pytest
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "In this step, we deploy our project"
                echo "Depending on the context, we may publish the project artifact or upload pickle files"
                '''
            }
        }
    }
}