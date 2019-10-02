#!/usr/bin/env groovy
def config = [
    scriptVersion              : 'bugfix/SITJ-650',
    iqOrganizationName         : 'Team AOS',
    pipelineScript             : 'https://git.aurora.skead.no/scm/ao/aurora-pipeline-scripts.git',
    downstreamSystemtestJob    : [branch: env.BRANCH_NAME],
    credentialsId              : "github",
    javaVersion                : 11,
    nodeVersion                : '10',
    debug                      : true,
    jiraFiksetIKomponentversjon: true,
    chatRoom                   : "#aos-notifications",
    compileProperties          : "-U",
    openShiftBuilderVersion    : "bugfix_SITJ_650_velger_feil_ved_retag-SNAPSHOT",
    versionStrategy            : [
        [branch: 'master', versionHint: '1'],
        [branch: 'bugfix/AOS-3687', versionHint: '0']
    ]
]
fileLoader.withGit(config.pipelineScript, config.scriptVersion) {
  jenkinsfile = fileLoader.load('templates/leveransepakke')
}
jenkinsfile.run(config.scriptVersion, config)
