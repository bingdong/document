# robot framework tips
## self defined html logs

```python
if logHtml is True:
			bgColor = 'rgba(238,17,17,0.3)' if any(f in str(response) for f in ConnectionCache.__fCmd) else 'rgba(0,163,0,0.3)'
			logId = datetime.now().strftime('%Y%m%d%H%M%S%f_{}'.format(randint(0, 100000)))
			htmlText = str(response).replace('\r', '')
			htmlText = htmlText.replace('<', '&lt;')
			htmlText = htmlText.replace('>', '&gt;')
			options = {'bgColor': bgColor, 'logId': logId, 'toggleId': logId, 'command': command, 'parameters': parameters, 'response': htmlText, 'rpc': rpc}
			logger.info('''<div id="{logId}" class="keyword" style="white-space: normal;background-color: {bgColor};"><div class="element-header closed" onclick="toggleKeyword('{toggleId}')"><div class="element-header-toggle" title="Toggle visibility" style="margin-top:-4px;background-color:white;"></div><div onclick="stopPropogation(event)" style="margin-left:20px;"><b>{command}{parameters}</b></div></div><div class="children populated" style="display: none;"><p style="white-space: pre;">\n{rpc}{response}\n\n</p></br></div></div>'''.format(**options), html=True)

```

## rich documentation support
version after 2.7, more regular documentation is supported. refer to 
[link](http://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html#id821)

![test](res/pic/robot_inner_style.jpg)

