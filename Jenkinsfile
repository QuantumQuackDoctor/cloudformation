pipeline {
    agent any
    parameters{
        string(name: 'HostedZoneId', defaultValue: params.HostedZoneId ?: '')
        string(name: 'CertificateARN', defaultValue: params.CertificateARN ?: '')
    }
    stages{
        stage("Deploy Base Infrastructure"){
            sh "aws cloudformation deploy --stack-name BaseInfrastructure --region ${AWS_REGION} --template-file baseInf.template --parameter-overrides HostedZoneId=${params.HostedZoneId} CertificateARN=${params.CertificateARN} --no-fail-on-empty-changeset"
        }
    }
    stages{
        stage("Deploy Database"){
            sh "aws cloudformation deploy --stack-name Database --region ${AWS_REGION} --template-file database.template --no-fail-on-empty-changeset"
        }
    }
}