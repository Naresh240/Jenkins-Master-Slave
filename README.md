# Jenkins-Master-Slave --> Static Slave

# Pre-Requisites
    Install Jenkins   --> Server1
    Install Java      --> Server2
# Jenkins UI
  ![image](https://user-images.githubusercontent.com/58024415/107875465-0e840a80-6ee6-11eb-9943-339581ba2618.png)
# Create SSH Connectivity between master and Slave server
  Generate SSH Key with in Master server
  Login to Jenkins user
  
    su -s /bin/bash jenkins
  
  Generate SSH key
  
    ssh-keygen
  ![image](https://user-images.githubusercontent.com/58024415/107875601-eba62600-6ee6-11eb-8192-eff5cb1327c8.png)
    
  Copy public key to node server at "/root/.ssh/authorized_keys"
  Check connectivity between two servers:
  ![image](https://user-images.githubusercontent.com/58024415/107875721-99b1d000-6ee7-11eb-8488-783d6954e334.png)
# Create Credentials to connect jenkins slave
  Goto Jenkins Master --> Manage Jenkins --> Manage Credentials 
  
  ![image](https://user-images.githubusercontent.com/58024415/107875912-aaaf1100-6ee8-11eb-9bf1-ff0b06554d5b.png)
  
  Click on Jenkins
  
  ![image](https://user-images.githubusercontent.com/58024415/107875933-cc0ffd00-6ee8-11eb-963e-679ff7bb0214.png)

  Click on 	"Global credentials (unrestricted)"
  
  ![image](https://user-images.githubusercontent.com/58024415/107875939-e3e78100-6ee8-11eb-908f-4ca6b55fa333.png)

  Click on "Add Credentials"
  
  ![image](https://user-images.githubusercontent.com/58024415/107875955-07aac700-6ee9-11eb-92ec-53a9946fbd3b.png)

  Click on "OK"
# Create Jenkins slave
  Goto Jenkins Master --> Manage Jenkins --> Manage Nodes and Cloud
  
  ![image](https://user-images.githubusercontent.com/58024415/107875800-ff05c100-6ee7-11eb-9713-2597b9b5d8e5.png)

  Click on "New Node"
  
  ![image](https://user-images.githubusercontent.com/58024415/107875835-193f9f00-6ee8-11eb-94b5-5d4ca94956b0.png)

  Click on "OK"
  
  ![image](https://user-images.githubusercontent.com/58024415/107876012-5bb5ab80-6ee9-11eb-9692-faeb31d08144.png)

  Click on "save"

  ![image](https://user-images.githubusercontent.com/58024415/107876092-c0710600-6ee9-11eb-9749-0ad74dac0d96.png)

# Create job to run on slave
  Create new job and provide slave
  
  ![image](https://user-images.githubusercontent.com/58024415/107876204-99ff9a80-6eea-11eb-9eab-3fc8ff2d72c9.png)
  
  Click on "Save" and Click on "Build now"
# Check Console Output
  ![image](https://user-images.githubusercontent.com/58024415/107876336-62452280-6eeb-11eb-95eb-a8e195d35c6e.png)
