pipeline {
    agent any
    parameters{
        string(name: 'HostedZoneId', defaultValue: params.HostedZoneId ?: '')
        string(name: 'CertificateARN', defaultValue: params.CertificateARN ?: '')
        string(name: 'Environment' defaultValue: params.Environment ?: 'dev')
    }
    stages{
        stage("Deploy Base Infrastructure"){
            steps {
                sh "aws cloudformation deploy --stack-name BaseInfrastructure --region ${AWS_REGION} --template-file baseInf.template --parameter-overrides HostedZoneId=${params.HostedZoneId} CertificateARN=${params.CertificateARN} Environment=${params.Environment} --no-fail-on-empty-changeset --capabilities CAPABILITY_NAMED_IAM"
            }
        }
        stage("Deploy Database"){
            steps {
                sh "aws cloudformation deploy --stack-name Database --region ${AWS_REGION} --template-file database.template --parameter-overrides Environment=${params.Environment} --no-fail-on-empty-changeset --capabilities CAPABILITY_NAMED_IAM"
            }
        }
    }
}