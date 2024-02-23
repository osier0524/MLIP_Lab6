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

                # Activate conda
                source /home/team03/miniconda3/etc/profile.d/conda.sh

                if ! /home/team03/miniconda3/bin/conda env list | grep -q 'myenv'; then
                    echo "Creating Conda environment"
                    /home/team03/miniconda3/bin/conda create -n lab6env python=3.8 pytest numpy pandas scikit-learn -c conda-forge -y
                else
                    echo "Conda environment 'myenv' already exists, skipping creation."
                fi

                source /home/team03/miniconda3/bin/activate myenv

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
