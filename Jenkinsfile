pipleline 
{
    agent any
    stages 
    {
        stage ('Continous Download')
        {
            steps
            {
                script 
                {
                    try 
                    {
                    git branch: 'main', url: 'https://github.com/Padmanabham95/Jenkins_prac.git'  
                    }
                    catch (Exception e1)
                    {
                    emailext body: 'FYI', subject: 'Git download failure', to: 'dev@gmail.com'
                    exit(1)
                    }
                }
            } 
        } 
        stage ('Continous Build')
        {
            steps
            {
                script 
                {
                    try 
                    {
                    sh 'mvn package'
                    }
                    catch (Exception e2)
                    {
                    emailext body: 'FYI', subject: 'Maven Build failured', to: 'dev@gmail.com'
                    exit(2)
                    }
                }
            } 
        } 
    }
}
