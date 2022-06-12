// 测试案例
// pipeline {
    // agent any

    // environment {
        // DISABLE_AUTH = 'true'
        // DB_ENGINE    = 'sqlite'
    // }

    // stages {
        // stage('Build') {
            // steps {
                // sh 'printenv'
            // }
        // }
    // }
// }


// 串行 blue ocean 多任务部署
// pipeline {
    // agent any

    // stages {
        // stage('Build') {
            // steps {
                // sh 'echo Build stage ...'
            // }
            // post {
	        	// always {
	        		// echo "post condition executed: always ..."
	        	// }
	        	// changed {
	        		// echo "post condition executed: changed ..."
	        	// }
	        	// aborted {
	        		// echo "post condition executed: aborted ..."
	        	// }
	        	// regression {
	        		// echo "post condition executed: regression ..."
	        	// }
        	// }
        // }


        // stage('Test'){
            // steps {
                // sh 'echo Test stage ...'
            // }
            // post {
            	// aborted {
            		// echo "post condition executed: aborted ..."
            	// }
            	// failure {
            		// echo "post condition executed: failure ..."
            	// }
            	// success {
            		// echo "post condition executed: success ..."
            	// }
            // }
        // }

        // stage('Deploy') {
            // steps {
                // sh 'echo Deploy stage ...'
            // }
        // }
    // }
	
    // post {
		// unstable {
			// echo "post condition executed: unstable ..."
		// }
		// unsuccessful {
			// echo "post condition executed: unsuccessful ..."
		// }
		// cleanup {
			// echo "post condition executed: cleanup ..."
		// }
    // }
  // }
  
// 并行任务
pipeline {
    agent any 

    stages {
        stage('Build') {
            parallel{
                stage('Build:Module1') { 
                    steps { 
                        sh 'echo Build Module1 stage ...' 
                    }
                }
                stage('Build:Module2') { 
                    steps { 
                        sh 'echo Build Module2 stage ...' 
                    }
                }
                stage('Build:Module3') { 
                    steps { 
                        sh 'echo Build Module3 stage ...' 
                    }
                }
            }
        }
        stage('Test'){
            steps {
                sh 'echo Test stage ...' 
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo Deploy stage ...' 
            }
        }
    }
}
 