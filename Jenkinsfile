properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/KeerthiKaila/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
    stage ("GetInstances") {

    sh "aws ec2 describe-instances --region us-east-1"
}
    stage ("CreateInstance") {
    sh "aws ec2 run-instances --image-id ami-013be31976ca2c322 --count 1 --instance-type t2.micro --key-name mykeypair --security-group-ids sg-01e9d64d --subnet-id subnet-f4a528da --region us-east-1"

}
}
