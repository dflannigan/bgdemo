node('maven') {
stage 'build'
openshiftBuild(buildConfig: 'myapp', showBuildLogs: 'true')
stage 'deploy'
openshiftDeploy(deploymentConfig: 'myapp')
openshiftScale(deploymentConfig: 'myapp',replicaCount: '2')
}
