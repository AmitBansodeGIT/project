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
				sh " sudo git pull https://github.com/AmitBansodeGIT/project.git "
			}
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "mvn clean package"
			
			}
			
		
		}
		
		stage ('Deploy_with_dockerfile') {
		
				steps {
						
					sh "sudo docker build -t tomcatproject:1 /mnt/project-myapp "

					sh " sudo docker run -d -p 8081:8080 tomcatproject:1 "
				
				}
	
		}
		
	}
}
