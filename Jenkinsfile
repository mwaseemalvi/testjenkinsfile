#!/usr/bin/env groovy

pipeline {
    agent any
    
    properties ([
    parameters ([
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
    ])
    
    ])
    
    stages {
        stage('Checking out the source code'){
            steps {
                //checkout([$class: 'GitSCM', branches: [[name: '*/dac']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'service', url: 'http://git.lab.local.it/pipelines/osm-deploy.git']]])
                checkout scm
            }
          }
        stage('Example') {
            steps {
                echo "${params.Greeting} World!"
            }
        }
    }
}




// node('slave'){
//     properties ([
//         parameters ([
//             string (name: 'VNF_ID',
//                 defaultValue: '1234',
//                 description: 'Virtual Network Function Identifier'
//             ),
//             string (name: 'Component_ID',
//                 defaultValue: '4321',
//                 description: 'VNF Component Identifier'
//             ),
//             string (name: 'Asset_ID',
//                 defaultValue: '1232',
//                 description: 'Enter the Asset ID'
//             ),
//             choice (name: 'Asset_Type',
//                 choices: ['DESCRIPTOR' , 'IMAGE' , 'CONFIGURATION' , 'ROBIN_BUNDLE']
//             ), 
//             string (name: 'File_EndPoint',
//                 defaultValue: 'http://tcap-artifactory.westeurope.cloudapp.azure.com/artifactory/xNF/versa/versa_hub_vnf.tar.gz',
//                 description: ''
//             ),
//             string (name: 'jfrogUser',
//                 defaultValue: 'service',
//                 description: ''
//             ),
//             password(name: 'jfrogPassword',
//                 defaultValue: 'Accenture.1',
//                 description: ''
//             ), 
//             string (name: 'TCAPURL',
//                 defaultValue: 'http://tcap.westeurope.cloudapp.azure.com',
//                 description: ''
//             ),
//             string (name: 'ArtifactoryURL',
//                 defaultValue: 'http://tcap-artifactory.westeurope.cloudapp.azure.com/artifactory/xNF',
//                 description: ''
//             ),
//         ])
//     ]) 
//     stage('Checking out the source code'){
//      //checkout([$class: 'GitSCM', branches: [[name: '*/dac']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'service', url: 'http://git.lab.local.it/pipelines/osm-deploy.git']]])
//      checkout scm
//     }
//     stage('Download Asset')
//     {
//         sh 'chmod u+x AcquireAsset/DownloadCustomerAsset.sh'    
// 		sh './AcquireAsset/DownloadCustomerAsset.sh'
//     }
//    /* stage('Update Antivirus')
//     {
//         sh 'chmod u+x AcquireAsset/restart_clamav.sh'    
// 		sh './AcquireAsset/restart_clamav.sh'
//     } */
//     stage('Scan for Virus')
//     {
//         sh 'chmod u+x AcquireAsset/ScanForVirus.sh'    
// 		sh './AcquireAsset/ScanForVirus.sh'
//     }
//     stage('Checksum validation')
//     {
//         sh 'chmod u+x AcquireAsset/md5Check.sh'    
// 		sh './AcquireAsset/md5Check.sh'
//     }
//     stage('Upload to TCAP Artifactory')
//     {
//         sh 'chmod u+x AcquireAsset/UploadToArtifactory.sh'    
// 		sh './AcquireAsset/UploadToArtifactory.sh'
//     }
// }