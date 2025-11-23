# Jenkins
### Basic Pipeline
```
pipeline{
    agent any
    stages{
        stage('Hello'){
            steps{
                echo "Hello from Jenkins"
            }
        }
    }
}
```
### Basic Pipeline with multiple stages
```
pipeline{
    agent any
    
    stages{
        stage('Checkout'){
            steps{
                echo "Pulling code from github..."
            }
        }
        
        stage('Install'){
            steps{
                echo "Installing Dependencies..."
            }
        }
        
        
        stage('Build'){
            steps{
                echo "Building application..."
            }
        }
        
        stage('Deploy'){
            steps{
                echo "Deploying to the server..."
            }
        }
        
    }
}
```

Jenkins + git connect clone github repo to local machine using wsl and ssh key
step 1: generate ssh key in wsl
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

step 2: add public key to the github 
GitHub → Settings → SSH and GPG keys → New SSH key
```
cat ~/.ssh/id_ed25519.pub

```

step 3: test github connection
```
ssh -T git@github.com
```

step 4: add private key to the jenkis
