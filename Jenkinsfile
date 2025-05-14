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
14             sh "git clone https://github.com/MaBouz/exp1.spring.git"
15         }
16      }
17       stage ("Generate backend image") {
18           steps {
19               dir("exp1.spring"){
20                   sh "mwn clean install"
21                   sh "docker build -t docexp1.spring ."
22               }
23           }
24       }
25       stage ("Run docker compose") {
26           steps {
27               dir("exp1.spring"){
28                   sh " docker compose up -d"
29               }
30           }
31       }
32   }
33 }
