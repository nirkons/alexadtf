# Alexa DTF

Dynamic timed functions for Alexa + HomeAssistant

HomeAssistant Discussion:  https://community.home-assistant.io/t/alexa-dtf-dynamic-timed-functions

## Installation

Requirements:
* Alexa connected to Homeassistant
* Node-Red Addon installed with homeassistant component
* An Amazon developer account (Free)

Let's begin, 
assuming you have node-red setup already, if not, you can install it via the addon store in HomeAssistant.

**Node-Red**:

* Click on the hamburger menu at the top right corner, under that select Import and choose the [FlowsJson](flows.json) from this repository.
* Double click the webhook node and generate a webhook ID (copy it) and save the node, then hit the Deploy button on the top right corner.
Your webhook URL will be: 
'https://YOURHOMEASSISTANTURL.DOMAIN/api/webhook/WEBHOOKID'

**Alexa Skill**:
* Create/Log in to your Alexa developer console at https://developer.amazon.com/alexa/console/ask 
* Hit Create skill, enter a skill name, under 'Choose a model to add to your skill' select "Custom" and under "Choose a method to host your skill's backend resources" select "Alexa-Hosted (Python)"
* Under "Choose a template to add to your skill" select "Hello world skill", let it create the skill.
* Under invocation name, you can choose whichever skill name you prefer, I chose "Yourself" as the invocation so it would be "Alexa, ask yourself to..."
* Under "Interaction model" click "JSON Editor" and paste the JSON code from [AmazonSkill](AmazonSkill.json) 
 in this repository
* Click Build model and let it build
* Go to the "Code" page and replace all the code in "lambda_function.py" with the code from [lambda_function.py](lambda_function.py)
 from this repository while changing the "base_url" value to your HomeAssistant webhook endpoint from Node-Red.
* Click Deploy and let it finish.
* Head over to the "Test" page and select "Development" instead of "Off" in the dropdown menu at the top.



## Usage
Since I chose the invocation name to be "Yourself", the usage would be:
* Alexa, ask yourself to turn {on} the {AC} in {1 hour}
* Alexa, ask yourself to set the {bedroom AC} to {25} in {6 hours}.
* Alexa, ask yourself to turn {off} the {computer} in {3 and a half hours}
* Alexa, ask yourself to turn {off} the {TV} in {20 minutes}.


## Contributing
Pull requests are welcome.

## Donation
If this project helped your life in any way and you want to support its development

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=H47Y39R579B6Y&currency_code=USD&source=url)

## License
[GPL 3.0]


