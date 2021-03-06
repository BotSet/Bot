# The LINE bot SDK for Java

## What's this?

This is a client library for the LINE Bot API.

## SYNOPSIS

```
@SpringBootApplication
public class EchoApplication {
    public static void main(String[] args) {
        SpringApplication.run(EchoApplication.class, args);
    }

    @RestController
    public static class MyController {
        @Autowired
        private LineBotClient lineBotClient;

        @RequestMapping("/callback")
        public void callback(@LineBotMessages List<Message> messages) throws LineBotAPIException {
            for (Message message : messages) {
                Content content = message.getContent();
                if (content instanceof TextContent) {
                    TextContent textContent = (TextContent) content;
                    lineBotClient.sendText(textContent.getFrom(),
                            textContent.getText());
                }
            }
        }
    }
}
```

## Modules

This project contains following modules:

 * line-bot-api-client: API client library for LINE Bot API
 * line-bot-model: Model classes for LINE Bot API
 * line-bot-servlet: Java servlet utilities for Bot servers
 * line-bot-spring-boot: spring-boot's auto configuration library for Bot servers

There's some sample projects:

 * sample-spring-boot-echo: Simple echo server.
 * sample-spring-boot-kitchensink: Full featured sample code.

## Requirements

This library requires Java 8 or later.

## Versioning

This project respects semantic versioning.

See http://semver.org/.

## LICENSE

See LICENSE.txt
