1 pipeline {
2     agent any
3     tools {
4         maven 'maven'
5     }
6     stages {
7       stage ("Clean up"){
8         steps {
9             deleteDir()
10         }
11      }
12      stage ("Clone repo"){
13         steps {
14             sh "git clone https://github.com/ahmedlk4785/exp1spring.git"
15         }
16      }
17       stage ("Generate image") {
18           steps {
19               dir("exp1spring"){
20                   sh "mwn clean install"
21                   sh "docker build -t tp2jenk ."
22               }
23           }
24       }
25       stage ("Run docker compose") {
26           steps {
27               dir("exp1spring"){
28                   sh " docker compose up -d"
29               }
30           }
31       }
32   }
33 }
