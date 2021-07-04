node {
  def commit_id

  try {
      stage('Preparation') {
        checkout scm
        sh "git rev-parse --short HEAD > .git/commit-id"
        commit_id = readFile('.git/commit-id').trim()
      }
      stage('test') {
        sh './mvnw install && ./mvnw test && ./mvnw package'        
      }
    } catch(e) {
      throw e;
   }                                     
}     
