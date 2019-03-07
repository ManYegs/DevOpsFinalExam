node {

stage('Clone Repository')
{
checkout scm
}


stage('Build docker image'){

sh "docker build -t FinalExam:latest ."
}

stage('Docker login to hub and push the image'){
sh "docker login -u 'manyegs' -p 'DevOpsExam2019' "
sh "docker tag FinalExam:latest manyegs/FinalExam:latest"
sh "docker push manyegs/FinalExam:latest"
}

stage('Deploy Docker Image') {
sh "docker container run --detach --publish 3849:80 --name Yego_Exam_2019 manyegs/FinalExam:latest "
}


}
