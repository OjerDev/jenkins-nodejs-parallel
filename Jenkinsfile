pipeline {
    agent any
    stages {
        stage('need to run parallelly'){
            steps{
                script{
                     boolean isFail = false
                     if ('npm start.isFail()') isFail = true
                    parallel(
                        a:{
                            dir('C:/Jenkins/workspace/test111') {
                                bat """
                                npm start
                                """
                            }
                        },
                        b:{
                            sleep(60) //eg 1 min is enough for run stage B
                            if(isFail) {
                            build job: 'test222'
                            }
                        }
                    )
                }
            }
        }
    }
}