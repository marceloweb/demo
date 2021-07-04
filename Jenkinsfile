node {
  def commit_id

  try {
      stage('Preparation') {
        checkout scm
        sh "git rev-parse --short HEAD > .git/commit-id"
        commit_id = readFile('.git/commit-id').trim()
      }
      stage('test') {
        sh './gradlew test && ./gradlew build'        
      }
    } catch(e) {
      throw e;
   }                                     
}     
