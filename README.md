# Emmanuel Ahishakiye

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/emmanuelahishakiye/)
[![Twitter](https://img.shields.io/badge/Twitter-Follow-blue?style=for-the-badge&logo=twitter)](https://twitter.com/ema__vx)
[![Instagram](https://img.shields.io/badge/Instagram-Follow-red?style=for-the-badge&logo=instagram)](https://www.instagram.com/_emlucky/)
[![Email](https://img.shields.io/badge/Email-Contact-red?style=for-the-badge&logo=gmail)](mailto:eahishak@u.rochester.edu)
[![Website](https://img.shields.io/badge/Website-Visit-green?style=for-the-badge&logo=google-chrome)](https://eahishakiye.com/)

<div align="center">
    <img src="https://github-readme-stats.vercel.app/api?username=eahishak&show_icons=true&theme=radical" alt="GitHub Stats" />
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=eahishak&layout=compact&theme=radical" alt="Top Languages" />
</div>

## 🎮 Play a Game While You Explore!

<div align="center">
    <canvas id="gameCanvas" width="480" height="320" style="border:1px solid #000000;"></canvas>
</div>

<script>
    var canvas = document.getElementById('gameCanvas');
    var ctx = canvas.getContext('2d');
    var ballRadius = 10;
    var x = canvas.width / 2;
    var y = canvas.height - 30;
    var dx = 2;
    var dy = -2;
    var paddleHeight = 10;
    var paddleWidth = 75;
    var paddleX = (canvas.width - paddleWidth) / 2;
    var rightPressed = false;
    var leftPressed = false;

    document.addEventListener("keydown", keyDownHandler, false);
    document.addEventListener("keyup", keyUpHandler, false);

    function keyDownHandler(e) {
        if (e.key == "Right" || e.key == "ArrowRight") {
            rightPressed = true;
        }
        else if (e.key == "Left" || e.key == "ArrowLeft") {
            leftPressed = true;
        }
    }

    function keyUpHandler(e) {
        if (e.key == "Right" || e.key == "ArrowRight") {
            rightPressed = false;
        }
        else if (e.key == "Left" || e.key == "ArrowLeft") {
            leftPressed = false;
        }
    }

    function drawBall() {
        ctx.beginPath();
        ctx.arc(x, y, ballRadius, 0, Math.PI * 2);
        ctx.fillStyle = "#0095DD";
        ctx.fill();
        ctx.closePath();
    }

    function drawPaddle() {
        ctx.beginPath();
        ctx.rect(paddleX, canvas.height - paddleHeight, paddleWidth, paddleHeight);
        ctx.fillStyle = "#0095DD";
        ctx.fill();
        ctx.closePath();
    }

    function draw() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        drawBall();
        drawPaddle();

        if (x + dx > canvas.width - ballRadius || x + dx < ballRadius) {
            dx = -dx;
        }
        if (y + dy < ballRadius) {
            dy = -dy;
        }
        else if (y + dy > canvas.height - ballRadius) {
            if (x > paddleX && x < paddleX + paddleWidth) {
                dy = -dy;
            }
            else {
                document.location.reload();
                clearInterval(interval);
            }
        }

        if (rightPressed && paddleX < canvas.width - paddleWidth) {
            paddleX += 7;
        }
        else if (leftPressed && paddleX > 0) {
            paddleX -= 7;
        }

        x += dx;
        y += dy;
    }

    var interval = setInterval(draw, 10);
</script>

## 💬 Chatbot

<div align="center">
    <div class="chatbot-container" style="position: fixed; bottom: 20px; right: 20px; width: 300px; height: 400px; background-color: #f1f1f1; box-shadow: 0px 0px 10px rgba(0,0,0,0.1); border-radius: 10px; display: none; flex-direction: column; justify-content: space-between;">
        <div class="chatbot-header" style="padding: 10px; background-color: #0095DD; color: white; border-radius: 10px 10px 0 0;">Chatbot</div>
        <div class="chatbot-messages" style="flex: 1; overflow-y: auto; padding: 10px;"></div>
        <input type="text" class="chatbot-input" style="padding: 10px; border: none; border-top: 1px solid #ccc; border-radius: 0 0 10px 10px;" placeholder="Type a message..." />
    </div>
    <button class="chatbot-toggle" style="position: fixed; bottom: 20px; right: 20px; width: 50px; height: 50px; background-color: #0095DD; color: white; border: none; border-radius: 50%; cursor: pointer;">💬</button>
</div>

<script>
    document.addEventListener('DOMContentLoaded', function () {
        // Chatbot Functionality
        const chatbotToggle = document.querySelector('.chatbot-toggle');
        const chatbotContainer = document.querySelector('.chatbot-container');
        const chatbotInput = document.querySelector('.chatbot-input');
        const chatbotMessages = document.querySelector('.chatbot-messages');

        chatbotToggle.addEventListener('click', function () {
            chatbotContainer.style.display = chatbotContainer.style.display === 'flex' ? 'none' : 'flex';
        });

        chatbotInput.addEventListener('keypress', function (event) {
            if (event.key === 'Enter') {
                sendMessage();
            }
        });

        function sendMessage() {
            const message = chatbotInput.value.trim();
            if (message === '') return;

            addMessage('user', message);
            chatbotInput.value = '';

            setTimeout(() => {
                getResponse(message);
            }, 500);
        }

        function addMessage(sender, message) {
            const messageElement = document.createElement('div');
            messageElement.style.padding = '5px 10px';
            messageElement.style.margin = '5px 0';
            messageElement.style.borderRadius = '10px';
            messageElement.style.backgroundColor = sender === 'user' ? '#0095DD' : '#e1e1e1';
            messageElement.style.color = sender === 'user' ? 'white' : 'black';
            messageElement.textContent = message;
            chatbotMessages.appendChild(messageElement);
            chatbotMessages.scrollTop = chatbotMessages.scrollHeight;
        }

        function getResponse(message) {
            const responses = {
                'hello': 'Hi there! How can I help you?',
                'hi': 'Hello! How can I assist you today? If you have any questions about Emmanuel Ahishakiye or need help, feel free to ask!',
                'help': 'Sure, what do you need help with? You can also contact Emmanuel at eahishak@u.rochester.edu.',
                'who are you': "I am Emmanuel's personal chatbot, here to assist you with any questions or information you need. How can I help you today?",
                // Add more responses as needed
            };

            const response = responses[message.toLowerCase()] || 'Sorry, I did not understand that. Can you please rephrase?';
            addMessage('bot', response);
        }
    });
</script>

## 👀 Interests
- **Web Development**: Crafting responsive and user-friendly web applications.
- **Mobile Development**: Building intuitive and high-performance mobile apps.
- **Machine Learning**: Exploring AI and machine learning to create smarter applications.
- **Open Source**: Contributing to open-source projects and collaborating with the developer community.

## 🌱 Currently Learning
- **Django**: Enhancing my backend development skills with this powerful Python framework.
- **React Native**: Building cross-platform mobile applications.
- **Docker & Kubernetes**: Containerization and orchestration for scalable applications.

## 💼 Professional Experience
- **Jackal Tech Ltd**: Founder and CTO - Leading the development of innovative tech solutions across various sectors including healthcare, education, and finance.
- **Open Source Contributions**: Active contributor to various open-source projects, improving and building tools for the developer community.

## 📫 How to Reach Me
- **Email**: eahishak@u.rochester.edu
- **LinkedIn**: [Emmanuel Ahishakiye](https://www.linkedin.com/in/emmanuelahishakiye/)
- **Twitter**: [@ema__vx](https://twitter.com/ema__vx)
- **Instagram**: [@_emlucky](https://www.instagram.com/_emlucky/)
- **Website**: [eahishakiye.com](https://eahishakiye.com/)

## 📈 GitHub Stats
![Emmanuel's GitHub stats](https://github-readme-stats.vercel.app/api?username=eahishak&show_icons=true&theme=radical)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=eahishak&layout=compact&theme=radical)

## 📝 Latest Blog Posts
- [Understanding Django for Beginners](https://medium.com/@eahishak/understanding-django-for-beginners-123456)
- [Building Scalable Mobile Apps with React Native](https://medium.com/@eahishak/building-scalable-mobile-apps-with-react-native-123456)
- [An Introduction to Docker & Kubernetes](https://medium.com/@eahishak/an-introduction-to-docker-kubernetes-123456)

## 🛠️ Technologies & Tools

<div align="center">
    <img src="https://img.shields.io/badge/-HTML5-05122A?style=for-the-badge&logo=html5" />
    <img src="https://img.shields.io/badge/-CSS3-05122A?style=for-the-badge&logo=css3" />
    <img src="https://img.shields.io/badge/-JavaScript-05122A?style=for-the-badge&logo=javascript" />
    <img src="https://img.shields.io/badge/-React-05122A?style=for-the-badge&logo=react" />
    <img src="https://img.shields.io/badge/-Vue.js-05122A?style=for-the-badge&logo=vue.js" />
    <img src="https://img.shields.io/badge/-Python-05122A?style=for-the-badge&logo=python" />
    <img src="https://img.shields.io/badge/-Django-05122A?style=for-the-badge&logo=django" />
    <img src="https://img.shields.io/badge/-Node.js-05122A?style=for-the-badge&logo=node.js" />
    <img src="https://img.shields.io/badge/-Express-05122A?style=for-the-badge&logo=express" />
    <img src="https://img.shields.io/badge/-React%20Native-05122A?style=for-the-badge&logo=react" />
    <img src="https://img.shields.io/badge/-Flutter-05122A?style=for-the-badge&logo=flutter" />
    <img src="https://img.shields.io/badge/-PostgreSQL-05122A?style=for-the-badge&logo=postgresql" />
    <img src="https://img.shields.io/badge/-MongoDB-05122A?style=for-the-badge&logo=mongodb" />
    <img src="https://img.shields.io/badge/-MySQL-05122A?style=for-the-badge&logo=mysql" />
    <img src="https://img.shields.io/badge/-Docker-05122A?style=for-the-badge&logo=docker" />
    <img src="https://img.shields.io/badge/-Kubernetes-05122A?style=for-the-badge&logo=kubernetes" />
    <img src="https://img.shields.io/badge/-Jenkins-05122A?style=for-the-badge&logo=jenkins" />
    <img src="https://img.shields.io/badge/-GitHub%20Actions-05122A?style=for-the-badge&logo=github-actions" />
    <img src="https://img.shields.io/badge/-AWS-05122A?style=for-the-badge&logo=amazon-aws" />
    <img src="https://img.shields.io/badge/-Azure-05122A?style=for-the-badge&logo=microsoft-azure" />
    <img src="https://img.shields.io/badge/-Google%20Cloud-05122A?style=for-the-badge&logo=google-cloud" />
</div>

## 🎓 Education
- **University of Rochester**: B.Sc. in Computer Science

## 🚀 Projects

<div align="center">
    <a href="https://github.com/eahishak/jackal-tech" style="display: block; text-align: left;">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=eahishak&repo=jackal-tech&theme=radical" />
    </a>
    <a href="https://github.com/eahishak/marvel-streams" style="display: block; text-align: left;">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=eahishak&repo=marvel-streams&theme=radical" />
    </a>
    <a href="https://github.com/eahishak/Emmanuel-Ahishakiye-Portfolio" style="display: block; text-align: left;">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=eahishak&repo=Emmanuel-Ahishakiye-Portfolio&theme=radical" />
    </a>
    <a href="https://github.com/eahishak/MEETEmmanuel" style="display: block; text-align: left;">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=eahishak&repo=MEETEmmanuel&theme=radical" />
    </a>
    <a href="https://github.com/eahishak/ManRobotic" style="display: block; text-align: left;">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=eahishak&repo=ManRobotic&theme=radical" />
    </a>
    <a href="https://github.com/eahishak/Mosaic-Eagle-Sample" style="display: block; text-align: left;">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=eahishak&repo=Mosaic-Eagle-Sample&theme=radical" />
    </a>
    <a href="https://github.com/eahishak/Jackal-Tech--Web-Prototype" style="display: block; text-align: left;">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=eahishak&repo=Jackal-Tech--Web-Prototype&theme=radical" />
    </a>
</div>
