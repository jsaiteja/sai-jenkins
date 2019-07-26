pipeline{
  agent{
    node{
    label 'master'
    }
  }
  
  
  stages{
    
    stage('terraform started'){
      steps{  
      sh 'echo "started"'
      sh 'pwd'
      }
    }
    
    stage('git clone'){
      steps{
        sh 'sudo rm -r *;sudo git clone https://github.com/jsaiteja/sai-jenkins.git'
      }
    }
    stage('CFT'){
      steps{
        sh 'ls'
        sh 'pwd'
        
        sh 'aws cloudformation create-stack --stack-name createec2 --template-body /var/lib/jenkins/workspace/q2_pipeline_ec2/sai-jenkins/cerate_ec2_cft.json --region us-east-1'
      }
    }
    
 }
  
}
