---
{"dg-publish":true,"permalink":"/my-resource/express/","dgPassFrontmatter":true}
---

# What is Express
## Node.js 기반의 웹 애플리케이션 프레임워크
- 간결한 설정
- 빠른 개발
- 다양한 확장 기능
# Usecase
## [[MyResource/REST API\|REST API]]
## Web Service
## Realtime Web API
# How to use Express
## [[npm\|npm]] install express


## [[MyProject/ExpressRouting\|ExpressRouting]]

# Extension
## Middleware
## [[MyResource/TemplateEngine\|TemplateEngine]]
## Link DataBase
## File System

# Library
## NodeMon
실행할 서버 js 파일 이름 index로 변경
- npm install nodemon
- package.json의 "scripts"항목dp "start": "nodemon index.js"추가
## JsonWebToken
- npm install jsonwebtoken
## [[MyResource/Passport.js\|Passport.js]]
- npm install passport
- npm install `${strategie}`
## dotenv
npm install dotenv
.env 파일에 선
## Sequelize
Data Base [[MyResource/ORM\|ORM]]
npm i sequelize sequelize-cli
npx sequelize init
config.json파일 수정
MySql 연결
```javaScript
const sequelize = require("./models").sequelize;
sequelize.sync();
```

>[!note] models/index.js
> ```javaScript
>const initModels = require('./init-models'); 
>// init-models.js에서 메서드 호출.
>const { Sequelize } = require('sequelize');
>
>// config/config.json 설정값 호출.
>// config객체의 env변수(development)키의 객체값 호출
>// 'development'가 아닌NODE_ENV가 있다면 해당 키의 객체 값 호출
>const env = process.env.NODE_ENV || 'development';
>const config = require("../config/config.json")[env]
>
>// new Sequelize를 통해 MySQL 연결 객체를 생성한다.
>const sequelize = new Sequelize(config.database, 
>	config.username, 
>	config.password, 
>	config
>);
>
>// 모델과 테이블간의 관계가 맺어진다.
>const models = initModels(sequelize);
>
>module.exports = models;
## SequalizeAuto
npm i sequelize-auto
orm.js 파일 작성
```javaScript
const SequelizeAuto = require('sequelize-auto');
const auto = new SequelizeAuto("DB_NAME", "DB_USER_NAME", "DB_PASSWORD", 
	{ 
	host: "127.0.0.1", 
	port: "3306", 
	dialect: "mysql", 
	} ); 
auto.run((err)=>{ if(err) throw err; })
```
$ node orm.js



	


# Structure
## src
app.js
-modules
-


