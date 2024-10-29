pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS'  // Tên này phải khớp với tên trong Global Tool Configuration
    }

    stages {
        stage("Install Dependencies") {
            steps {
                sh 'npm install'  // Cài đặt các gói từ package.json
            }
        }
        stage("Build Project") {
            steps {
                sh 'npm run build'  // Chạy lệnh build của dự án
            }
        }
    }

    post {
        success {
            echo 'SUCCESSFUL'  // Hiển thị thông báo khi thành công
        }
        failure {
            echo 'FAILED'  // Hiển thị thông báo khi thất bại
        }
    }
}
