pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage("Install Dependencies") {
            steps {
                // Cài đặt toàn bộ dependencies
                sh 'node --no-warnings $(which npm) install'
            }
        }

        stage("Run Lint") {
            steps {
                // Kiểm tra lỗi quy tắc mã với ESLint
                sh 'node --no-warnings $(which npm) run lint'
            }
        }

        stage("Run Unit Tests with Jest") {
            steps {
                // Chạy kiểm thử đơn vị bằng Jest và tạo báo cáo coverage
                sh 'node --no-warnings $(which npm) test -- --coverage'
            }
        }

        stage("Run E2E Tests with Cypress") {
            steps {
                // Chạy kiểm thử End-to-End bằng Cypress
                sh 'node --no-warnings $(which npm) run e2e'
            }
        }

        stage("Build Project") {
            steps {
                // Build dự án Next.js
                sh 'node --no-warnings $(which npm) run build'
            }
        }
    }

    post {
        success {
            echo 'SUCCESSFUL'
        }
        failure {
            echo 'FAILED'
        }
    }
}
