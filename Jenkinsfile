pipeline {
    agent any

    tools {
        nodejs 'NodeJS' // Chọn NodeJS tool đã được cài trong Jenkins
    }

    stages {
        stage("Install Dependencies") {
            steps {
                // Cài đặt tất cả dependencies của dự án
                sh 'node --no-warnings $(which npm) install'
            }
        }

        stage("Run Lint") {
            steps {
                // Chạy ESLint để kiểm tra quy tắc mã nguồn
                sh 'node --no-warnings $(which npm) run lint'
            }
        }

        stage("Run Unit Tests with Jest") {
            steps {
                // Chạy kiểm thử đơn vị với Jest và tạo báo cáo coverage
                sh 'node --no-warnings $(which npm) test -- --coverage'
            }
        }

        stage("Run E2E Tests with Cypress") {
            steps {
                // Chạy kiểm thử End-to-End với Cypress
                sh 'node --no-warnings $(which npm) run e2e'
            }
        }

        stage("Build Project") {
            steps {
                // Thực hiện build dự án Next.js
                sh 'node --no-warnings $(which npm) run build'
            }
        }
    }

    post {
        success {
            // Thông báo khi pipeline hoàn tất thành công
            echo 'SUCCESSFUL'
        }
        failure {
            // Thông báo khi pipeline gặp lỗi
            echo 'FAILED'
        }
    }
}
``
