node('maven') {
stage 'buildInDevelopment'
openshiftBuild(buildConfig: 'myapp', showBuildLogs: 'true')
stage 'deployInDevelopment'
openshiftDeploy(deploymentConfig: 'myapp')
openshiftScale(deploymentConfig: 'myapp',replicaCount: '2')
stage 'deployInTesting'
openshiftTag(sourceStream: 'myapp',  sourceTag: 'latest', destinationStream: 'myapp', destinationTag: 'promoteToQA')
openshiftDeploy(namespace: 'qa', deploymentConfig: 'myapp', )
openshiftScale(namespace: 'qa', deploymentConfig: 'myapp',replicaCount: '3')
}
