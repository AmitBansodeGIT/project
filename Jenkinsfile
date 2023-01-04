pipeline {
agent {
label {
		label "qa"
		customWorkspace "/mnt/project-myapp"
		
		}
		}
		
	stages {
		
		stage ('Pull_SRC') {
			
			steps {
				sh "git pull https://github.com/AmitBansodeGIT/project.git
			}
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "mvn clean package"
			
			}
			
		
		}
		
		stage ('Deploy_with_dockerfile'){
		
				steps {
						
					sh "sudo docker build -t tomcatproject:1 /mnt/project-myapp "

				}
			steps {
					sh " sudo docker run -p 8080:8080 tomcatproject:1 "
				
				}
	
	
	
	}
		
}
