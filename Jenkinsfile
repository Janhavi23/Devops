//test comment
node('master') {            //definition of job to be done
    stage('Git Clone') {    //seperation of the jobs to different stages for easier debugging
        git branch: 'master', changelog: true, url: 'https://github.com/Janhavi23/Devops.git'
        sh "ls"
    }

    stage('Project Name') {
        def projects = readJSON file: "${env.WORKSPACE}/jsonfile.json"

        echo "current workspace is ${env.WORKSPACE}"
        echo "Project name is ${projects.projects.project[0].name}"
    }
    
    stage('RUN Python Script') {
        sh "chmod 777 hello-nmit.py"    //everything in a sh is a command
        sh "./hello-nmit.py"
    }

}
