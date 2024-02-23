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

                # Activate venv
                sudo /home/team03/miniconda3/condabin/conda init

                sudo /home/team03/miniconda3/condabin/conda create -n myenv python=3.8 pytest numpy pandas scikit-learn -c conda-forge -y

                sudo /home/team03/miniconda3/condabin/conda activate myenv

                # Run pytest
                pytest

                # echo 'pytest not runned'
                # exit 1 #comment this line after implementing Jenkinsfile
                '''

            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
