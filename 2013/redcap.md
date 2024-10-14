---
description: '2013'
---

# Redcap

A conversational SMS interface for letting people in your front door.

I built this when I lived in an apartment building with a buzzer out front, which dialed the resident's phone number. I wouldn't find out I had autism until ten years later (lol); it now makes sense why I built an entire app rather than just answer the phone.

## Readme

Text Redcap when you're expecting a guest. Redcap will buzz them in, and let you know when they've arrived.

### User scenarios

#### Basic

```
Redcap: Someone's at the door - should I let them in?
Me: yes
Redcap: Got it. I've buzzed them in.
```

```
Redcap: Someone's at the door - should I let them in?
Me: no
Redcap: Got it - I'll keep the door locked.
```

```
Redcap: Someone's at the door - should I let them in?
Redcap: I didn't hear back from you, so I kept the door locked.
```

```
Me: 10m
Redcap: Got it - I'll buzz in your guest within the next ten minutes.
```

#### Names

```
Me: john in 10m
Redcap: Got it - I'll buzz John in within the next ten minutes.
Redcap: John just arrived - I've buzzed them in.
```

```
Me: john anytime
Redcap: Got it - I'll buzz John in anytime.
Redcap: If you want John to have a personal security code, text back the code he should use. Otherwise, I'll just ask guests for a name.
...
Redcap: John's here - I've buzzed him in.
```

#### Security codes

```
Me: 9375 in 10m
Redcap: Got it - I'll buzz in a guest with the security code "9375" within the next ten minutes.
Redcap: Your guest just arrived - I've buzzed them in.
```

```
Me: 9375 in 10m
Redcap: Got it - I'll buzz in a guest with the security code "9375" within the next ten minutes.
Redcap: You have a guest, but they entered "9376" instead of "9375". Should I let them in?
```

#### Names with security codes

```
Me: john anytime
Redcap: Got it - I'll buzz John in anytime.
Redcap: If you want John to have a personal security code, text back the code he should use. Otherwise, I'll just check for the name.
Me: 1465
Redcap: Got it - make sure John knows to use the code "1465" when he arrives.
...
Redcap: John's here - I've buzzed him in.
```

### Guest scenarios

#### Prompt

```
"Hi there. Please state your name, or enter your security code."
```

#### Authorized

```
"Got it, thanks." [buzz in]
```

#### Unauthorized - disallowed

```
"Got it, thanks. One moment." [sms to unit user]
"Thanks for calling." [hang up]
```

#### Unauthorized - allowed

```
"Got it, thanks. One moment." [sms to unit user]
[buzz in]
```

### Entities

#### Building

Has a phone number of its own, from which the residents' numbers are dialed.

#### Unit

Is registered with the building. Has a Twilio phone number, which is unique within a building.

#### User

Belongs to a unit. Has a cell phone number that Redcap communicates with via sms.

#### Rule

Belongs to a unit, created by a user. Expires. Might have a name associated, depending on how accurate Twilio's transcription api turns out to be. Might have a security code.

#### Message

Belongs to a user. Can be created by the user with an incoming text message, or can be created by Redcap to communicate with the user.
