pipeline {
    agent any

    stages {
        stage('check version php') {
            agent {
                docker {
                    image 'php:fpm'
                }
            }
            steps {
                blocks = [
                    [
                        "type": "section",
                        "text": [
                            "type": "mrkdwn",
                            "text": "Hello, Assistant to the Regional Manager Dwight! *Michael Scott* wants to know where you'd like to take the Paper Company investors to dinner tonight.\n\n *Please select a restaurant:*"
                        ]
                    ],
                    [
                        "type": "divider"
                    ],
                    [
                        "type": "section",
                        "text": [
                            "type": "mrkdwn",
                            "text": "*Farmhouse Thai Cuisine*\n:star::star::star::star: 1528 reviews\n They do have some vegan options, like the roti and curry, plus they have a ton of salad stuff and noodles can be ordered without meat!! They have something for everyone here"
                        ],
                        "accessory": [
                            "type": "image",
                            "image_url": "https://s3-media3.fl.yelpcdn.com/bphoto/c7ed05m9lC2EmA3Aruue7A/o.jpg",
                            "alt_text": "alt text for image"
                        ]
                    ]
                ]

                slackSend(channel: "myproject", blocks: blocks)
                sh 'php -v'
            }
            post {
                success {
                    slackSend(channel: "myproject", color: "good", message: "Build success!")
                }
                failure {
                    slackSend(channel: "myproject", color: "danger", message: "Build failure!")
                }
            }
        }
    }
}
