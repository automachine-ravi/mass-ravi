pipeline {
    agent none
    stages {
        stage ("java project") {
        agent {label 'master' }    
            steps {
                parallel (
                    CODEPULL: {
                        echo "pulling code from GIT branch1 for java projects"
                        },
                    BuildMAVEN: {
                        echo "buld the war pkgs"
                        },
                    DeplloyTOMCAT: {
                        echo "deploy war to the tomcat"
                        }
                )
            }
        }
        stage ("C# project") {
            agent { label 'master' }
            steps {
                parallel (
                    CODEPULL: {
                        echo "pulling code form C# Branch"
                        },
                    BUildMSBUILD: {
                        echo "build with msbuild to generate Msi, exe dll pkgs"
                        }
                )
            }
        }
        stage ("Python Project") { 
            agent {label "master"}
            steps {
                parallel (
                    CODEPULL: {
                        echo "pulling the code form Python Branch"
                        },
                    BUILDPYBUILD: {
                        echo "building the code form PYBUILD"
                        }
                )
            }
        }
        stage ("nodejs project") {
            agent { label 'master' }
            steps {
                parallel (
                    CODEPULL: {
                        echo "pulling the code form nodejs branch"
                        },
                    BUILDNPM: {
                        echo "build with npm build to generate .js"
                        }
                )
            }
        }
    }
}
