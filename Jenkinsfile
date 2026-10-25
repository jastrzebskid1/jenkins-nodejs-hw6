pipeline {
  agent { docker { image 'node:22-alpine' } }
  environment { npm_config_cache = 'npm-cache' }
  stages {
    stage('Install') { steps { sh 'npm install' } }
    stage('Test')    { steps { sh 'npm test' } }
    stage('Build')   { steps { sh 'npm run build' } }
  }
  post { success { archiveArtifacts artifacts: 'dist/*.tgz', fingerprint: true } }
}
