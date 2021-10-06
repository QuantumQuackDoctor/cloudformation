pipeline {
    agent any
    parameters{
        string(name: 'HostedZoneId', defaultValue: params.HostedZoneId ?: '')
        string(name: 'CertificateARN', defaultValue: params.CertificateARN ?: '')
        string(name: 'DBUsername', defaultValue: params.DBUsername ?: '')
        string(name: 'DBPassword', defaultValue: params.DBPassword ?: '')
    }
    stages{
        stage("Deploy Template"){
            sh "aws cloudformation deploy --stack-name BaseInfrastructure --region ${AWS_REGION} --template-file baseInf.template --parameter-overrides HostedZoneId=${params.HostedZoneId} CertificateARN=${params.CertificateARN} DBUsername=${params.DBUsername} DBPassword=${params.DBPassword} --no-fail-on-empty-changeset"
        }
    }
}