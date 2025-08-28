# 🕳️ Alice and the Token of Return — An OAuth 2.1 Wonderland Tale

This repository means to explain OAuth in a fun and creative way. Here's code you can test to get a sense of how things flow [code](./example-code/README.md). But more importantly here's a whimsical story of Alice's journey through the OAuth 2.1 landscape.


## Scene 1: The Chase Begins

Alice spots the White Rabbit darting through the forest, muttering, “I’m late for the introspection endpoint!”  
She follows him, trips over a redirect URI, and tumbles down the rabbit hole…

![Alice and the White Rabbit](./assets/Scene%201%20The%20Chase%20Begins_Alice%20spots%20the%20White%20Rab.png)

## Scene 2: Authorization with the Caterpillar

Alice lands in a cloud of smoke. The Caterpillar is perched on a mushroom, puffing out scope-shaped rings.

> **Alice**: “Excuse me, I need to get home. I’m chasing a rabbit.”  
> **Caterpillar**: “Who are you? And what scopes do you seek?”  
> **Alice**: “OpenID, profile, maybe email?”  
> **Caterpillar**: “Very well. You must first authenticate. Present your credentials to the Queen’s Guard.”

![Caterpillar](./assets/Scene%202%20Authorization%20with%20the%20Caterpillar_Alice%20l.png)

He hands her a scroll:  

    ```sh
GET /authorize?
  response_type=code
  &clientid=aliceapp
  &redirect_uri=https://alice.app/callback
  &scope=openid profile email
  &state=tea_party
```

## Scene 3: The Queen of Hearts — Consent & Code

Alice arrives at the Queen’s garden. The Queen towers over her.

> **Queen**: “Do you consent to give this app access to your royal data?”  
> **Alice**: “I suppose I must.”  
> **Queen**: “Then take this code and be gone!”

![Queen of hearts](./assets/Scene%203%20The%20Queen%20of%20Hearts%20—%20Consent%20%20Code_Alice_.png)

She tosses Alice a glittering token:  

```text
Authorization Code: 7H3R35N0T1M3
```

## Scene 4: Tea with the Mad Hatter — Token Exchange

Alice stumbles into a chaotic tea party. The Mad Hatter is juggling teacups and JSON payloads.

> **Alice**: “I have a code. I need a token.”  
> **Hatter**: “Splendid! POST it to me!”

![](./assets/Scene%204%20Tea%20with%20the%20Mad%20Hatter%20—%20Token%20Exchange_A.png)

He scribbles furiously:  

```text
POST /token
  granttype=authorizationcode
  code=7H3R35N0T1M3
  redirect_uri=https://alice.app/callback
  clientid=aliceapp
  clientsecret=tophat_secret
```

> **Hatter**: “Here you go, dear!”  

```json
{
  "accesstoken": "T0K3N0F_R3TURN",
  "token_type": "Bearer",
  "expires_in": 3600,
  "scope": "openid profile email"
}
```

## Scene 5: Through the Looking Glass — Resource Access

Alice approaches the Looking Glass, token in hand.

![](./assets/Scene%205%20Through%20the%20Looking%20Glass%20—%20Resource%20Acces.png)

> **Mirror**: “Do you bear a valid token?”  
> **Alice**: “Yes, from the Hatter himself.”  
> **Mirror**: “Then pass, and retrieve your rabbit.”

She steps through and finds the White Rabbit sipping tea with the Dormouse.

## Scene 6: The White Rabbit’s Revelation

> **Alice**: “I’ve chased you across endpoints and scopes! Why?”  
> **Rabbit**: “Because, dear Alice, every journey needs a token. And yours was about discovering who you are in the process.”

![](./assets/Scene%206%20The%20White%20Rabbit’s%20Revelation_Alice%20finds_.png)

He hands her a refresh token for future adventures.

## 🏁 The End (or is it?)

Alice returns home, token in hand, rabbit by her side, and a newfound appreciation for the *madness of secure authorization*.

![](./assets/🏁%20The%20End%20(or%20is%20it)_Alice%20returns%20home,%20token%20in.png)