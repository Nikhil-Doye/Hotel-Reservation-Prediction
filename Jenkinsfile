pipeline{
    agent any

    environment{
        VENV_DIR = 'venv'
        GCP_PROJECT = 'dark-form-456022-r7'
        GCLOUD_PATH = '/var/jenkins_home/google-cloud-sdk/bin'
    }

    stages{
        stage('Cloning Github Repo to Jenkins'){
            steps{
                script{
                    echo 'Cloning Github Repo to Jenkins.............'
                    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/Nikhil-Doye/Hotel-Reservation-Prediction']])
                }
            }
        }

        stage('Setting Up Virtual Environment and installing dependencies'){
            steps{
                script{
                    echo 'Setting Up Virtual Environment and installing dependencies.............'
                    sh '''
                        python -m venv ${VENV_DIR}
                        . ${VENV_DIR}/bin/activate
                        pip install --upgrade pip
                        pip install -r requirements.txt
                    '''
                }
            }
        }

         stage('Building and pushing docker image to GCR'){
            steps{
                script{
                    withCredentials([file(credentialsId : 'gcp-key', variable : 'GOOGLE_APPLICATION_CREDENTIALS')]) {
                        echo 'Building and pushing docker image to GCR.............'
                        sh '''
                            export PATH=$PATH:${GCLOUD_PATH}

                            gcloud auth activate-service-account --key-file=${GOOGLE_APPLICATION_CREDENTIALS} 
                            
                            gcloud config set project ${GCP_PROJECT}

                            gcloud auth configure-docker --quiet
                            
                            docker build -t gcr.io/${GCP_PROJECT}/hotel-reservation-prediction:latest .

                            docker push gcr.io/${GCP_PROJECT}/hotel-reservation-prediction
                        '''
                    }
                }
            }
        }
    }
}