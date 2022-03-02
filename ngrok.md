# ngrok - secure introspectable tunnels to localhost

#### Ngrok is a cross-platform application that exposes local server ports to the Internet.
#### Say you were developing a couple of website pages and you wanted to show it to your friend, but you didn’t have all the infrastructure already set up— This is where ngrok comes into picture. So let us begin.

## Steps:

#### Follow the below instructions:

- Visit this link to download ngrok : https://ngrok.com/download
- Extract the downloaded file depending on your operating system.
- Run this command : curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null &&
              echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list &&
              sudo apt update && sudo apt install ngrok   
              
- Open file ngrok.yml - enable "Show hidden files" option
    (E.G: /home/solicitous/.ngrok2/ngrok.yml)

- TAdd the following commands in above mentioned file.("/home/solicitous/.ngrok2/ngrok.yml")
        authtoken: 25oeyjfTMdrpAaodOuq***************24u29f9Kpi (don't replace the auth token as it is unique for every system)

        tunnels:
        first:
            addr: 8000("you can add any port address as you wish")
            proto: http    
        second:
            addr: 5000
            proto: http
        third:
            addr: 8501
            proto: http

    ## NOTE: Put This Port in Your Project's Port (i.e both ports should be same)

- Run your project on your system
    # It should look something like this:
            python3 app.py 
        * Serving Flask app "app" (lazy loading)
        * Environment: production
        WARNING: This is a development server. Do not use it in a production deployment.
        Use a production WSGI server instead.
        * Debug mode: on
        * Running on http://127.0.0.1:8000/ (Press CTRL+C to quit) (For me,I have taken port 8000)
        * Restarting with stat
        * Debugger is active!
        * Debugger PIN: 181-399-184

- after the above step, Run : 
    # "ngrok start --all"
    # It should look something like this:
            Account                       xyzzz@gmail.com (Plan:Free)                                                                                                                                       
        Version                       2.3.40                                                                                                                                                                 
        Region                        United States (us)                                                                                                                                                     
        Web Interface                 http://127.0.0.1:4040                                                                                                                                                  
        Forwarding                    http://5418-103-51-75-100.ngrok.io -> 
                            http://localhost:3030                                                                                                            
        Forwarding                    https://5418-103-51-75-100.ngrok.io -> http://localhost:3030        


- Both your project in your local and ngrok should be running continuously 
   
-  # Your project is running on this url which varies from user to user
(http://5418-103-51-75-100.ngrok.io) http://localhost:8000 

- Even if one. either project or ngrok isn't running, you'll get this error:
# "Failed to complete tunnel connection"
if this happens, don't worry and run the above steps again


- Even if someone has any doubts regarding this, I've attached a video so go through it once.


## Authors:

- [Shubham Nivangune](https://www.instagram.com/shubham_nivangune16)
- [Prathamesh Kodilkar](https://www.instagram.com/prathameshkodilkar)
- [Pushkar Sonpatki](https://www.instagram.com/pushkarsonpatki_)
- [Raj Raut](https://www.instagram.com/raj_raut7719)  
