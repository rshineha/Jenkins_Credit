pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "In the Build stage, it is imperative that the code is able to be compiled correctly, this includes ensuring translation of high-level programming language into machine code, the dependencies such as libraries are working, and packing the compiled code to be able to distribute. Maven can be used to simplify the configuration process for the tasks above."
            }
        }
        stage("Unit and Integration Tests"){
            steps{
                echo "In this stage, the codes functions and smaller components are broken down (e.g: functions/classes) and unit tested individually to verify that it performs exactly as needed. Integration testing is carried out to ensure that all the components of the program work together without issues. In web application development, Selenium is used to create simulations of users interacting with different functions of the website to test website functionality."
            }
            post{
               always{
                emailext (
                    to: 'shinehar27@gmail.com',
                    subject: "Unit and Integration Test Status",
                    body: "Unit and Integration Test complete with status: ${currentBuild.currentResult}",
                    attachLog: true
                )
               } 
            }
            }
        stage("Code Analysis"){
            steps{
                echo "Not to be confused with the Unit and Integration testing stage, this stage is analysis of static code, so there will be no execution of the code. Any vulnerabilities, issues and bugs will be found in this stage. Other categories relating to good coding standards such as duplication are analyzed to ensure it is up to industry standards and compliance. A tool for this would be SonarQube as it works well with Jenkins pipelines by installing plugins."
            }
        }
        stage("Security Scan"){
            steps{
                echo "This stage focuses on identifying weak spots in the code that can be exploited by attackers, therefore security analysis of the code will be carried out for static code, dynamic code - where the code is executed and running and may be vulnerable to DDoS, XSS and injection attacks - and the dependencies are also scanned. While there is no tool to cover everything, a tool such as Synopsys can cover a lot of security scans for static and dynamic code analysis."
            }
            post{
               always{
                emailext (
                    to: 'shinehar27@gmail.com',
                    subject: "Security Scan Status",
                    body: "Security Scan complete with status: ${currentBuild.currentResult}!",
                    attachLog: true
                )
               } 
            }
            }
        stage("Deploy to Staging"){
            steps{
                echo "In this stage, the code is deployed to staging environments where the code will be run on a simulation of what actual production would entail from software to hardware configurations. This can be done using AWS CodeDeploy to recreate server infrastructure, different deployment strategies and configurations. As such, smoke tests are able to be carried out to identify deployment issues before the actual, public deployment."
            }
        }
        stage("Integration Test on Staging"){
            steps{
                echo "Integration testing of the overall function of the application is tested in a staging environment to ensure that the application works successfully with external infrastructure like databases. Automatic testing is also done in this environment to ensure that the application responds consistently without issues or failures. Any errors at this stage can be recognized and fixed before official deployment. A tool used is Selenium as it allows the application to be tested using different browser platforms that could be used by the public, such as Chrome/Safari."
            }
        }
        stage("Deploy to Production"){
            steps{
                echo "The final stage where the application is deployed to the production environment, where configurations are finalized and the product is deployed. It is also important in this stage to have a backup/rollback plan and that the application is observed for errors and efficiency. AWS CodeDeploy could be used as it can carry out the above functions."
            }
        }
    }
}
