node {

stage('Clone Repository')
{
checkout scm
}


stage('Build docker image'){

sh "docker build -t finalexam:latest ."
}

stage('Docker login to hub and push the image'){
sh "docker login -u 'manyegs' -p 'DevOpsExam2019' "
sh "docker tag finalexam:latest manyegs/finalexam:latest"
sh "docker push manyegs/finalexam:latest"
}

stage('Deploy Docker Image') {
sh "docker container run --detach --publish 3849:80 --name Yego_Exam_2019 manyegs/finalexam:latest "
}


}
