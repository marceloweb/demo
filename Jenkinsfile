node {
  def commit_id

  try {
      stage('Preparation') {
        checkout scm
        sh "git rev-parse --short HEAD > .git/commit-id"
        commit_id = readFile('.git/commit-id').trim()
      }
      stage('Run Tests') {
        sh './gradlew test && ./gradlew build'        
      }
      stage('Code Review') {

      }
    } catch(e) {
      throw e;
   }                                     
}     
