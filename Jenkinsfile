node {
  checkout scm;

  def jobName = "${env.JOB_NAME}"
  def theJob = jobName.replace("/", " ");

  def mvnHome = tool 'latest'
  
  /* Execute maven */
  sh "${mvnHome}/bin/mvn clean install -Prepository -Drt.build.number=${env.BUILD_NUMBER} -DjenkinsProject='${theJob}' -DjenkinsBuild=${env.BUILD_NUMBER}";

  step([$class: 'UpdaterPublisher']);
}