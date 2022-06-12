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
// pipeline {
	// 可以指定容器 或 节点
    // agent any 
	
	// 可以设置parameters 或 enviroment 
	// def unitTestModule = load "load.groovy"
	
    // stages {
		// stage('Pre'){
            // steps { 
				// 下载代码，其他的依赖等
				// 安装工具
				// 做执行检查
				// sh 'pwd&&ls'
                // sh 'echo Pre stage ...' 
            // }
        // }
        // stage('Build') {
            // parallel{
                // stage('Build:Module1') { 
                    // steps { 
						// def log
						// log = load "${WORKSPACE}/load.groovy"
                        // sh 'echo Build Module1 stage ...'
						// unitTestModule.runUnitTest()						
                    // }
                // }
                // stage('Build:Module2') { 
                    // steps { 
                        // sh 'echo Build Module2 stage ...' 
						// unitTestModule.exportReporter()
                    // }
                // }
                // stage('Build:Module3') { 
                    // steps { 
                        // sh 'echo Build Module3 stage ...' 
                    // }
                // }
            // }
        // }
        // stage('Post or Test'){
			// 也可以是Test，比如说网站部署。这里可以做基础功能测试，接口测试，性能测试，安全测试等
			// 华为项目中这一步是打包，各种版本的包，并上传
            // steps {
                // sh 'echo Post or Test stage ...' 
            // }
        // }
        // stage('Deploy') { 
			// 实在不行Test可以放在Deploy去做 | 因为代码可能只有在硬件上烧刻才能部署
			// 这里的test可能只是拿一些旧用例跑一下
            // steps {
                // sh 'echo Deploy stage ...' 
            // }
        // }
    // }
// }
 
 
// jenkins使用 groovy
pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                // groovy 脚本
                sh 'echo hello'
                echo 'Hello World'
                script {
                    // groovy 脚本
                    def browsers = ['chrome', 'firefox']
                    for (int i = 0; i < browsers.size(); ++i) {
                        echo "Testing the ${browsers[i]} browser"
                    }
                }
            }
        }
    }
}