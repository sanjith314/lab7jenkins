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
                echo "Creating virtual environment"
                python3 -m venv mlip

                echo "Activating virtual environment and dependencies"
                . mlip/bin/activate

                python -m pip install --upgrade pip setuptools --break-system-packages
                pip install --break-system-packages pytest numpy pandas scikit-learn

                echo "Running Test"
                chmod +x ./mlip/bin/pytest

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
