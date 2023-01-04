pipeline {
agent {
label {
		label "qa"
		customWorkspace "/mnt/project-myapp"
		
		}
		
	stages {
		
		stage ('Pull_SRC') {
			
			steps {
				sh " sudo git pull https://github.com/AmitBansodeGIT/project.git "
			}
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "sudo mvn clean package"
			
			}
			
		
		}
		
		stage ('Deploy_with_dockerfile') {
		
				steps {
						
					sh "sudo docker build -t tomcatproject:1 /mnt/project-myapp "

					sh " sudo docker run -p 8080:8080 tomcatproject:1 "
				
				}
	
		}
		
	}
}
