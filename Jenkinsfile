pipeline{

   agent any

    tools{
      maven 'mymaven'
    }
    stages{
        stage('Test Code')
        {
            
            steps{
               script{
                int maxRetries = 3
                int retries = 0
                boolean success = false 
                while(retries<maxRetries && !success) // writing a loop for a condition to come true
                {
                    try{  // write that code which may fail
                     sh 'mvn test'
                     success = true
                    }
                    catch(Exception e){  // write the code to be executed while handling the execption
                        retries++
                        sleep(10)  // wait for 10 seconds, before retrying
                    }
                }
                if(!success)
                {
                    error("all the attempts failed")
                }
                
               }
            }

        }
    }
}
