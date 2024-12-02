# Fixing Avatar Bug

Here is the issue: [Unfriendly Icon Representation - Issue #407](https://github.com/TEN-framework/TEN-Agent/issues/407)
## Problem:

Setting up the environment for this project was quite a challenge. Initially, I faced multiple hurdles, such as signing up with different API platforms and configuring various databases to get the frontend functioning. 


The issue was that the frontend was rendering U for user messages  which was very user friendly and the developers were unaware where ite was coming from.

## First Try:
I tried changing the fallback text in the `AvatarFallback` to null or an empty string (""), assuming this would prevent the fallback text ("U") from showing. However, this approach didn’t work because fallback was still being triggered by the Redux state and Avatar component was automatically using "U" as the fallback for any messages from the user, which was not the intended behavior.

## Debugging:

I then went ahead and added few debug statement to understand the behavior of data types. In chrome frontend, i was able to understand see user id as a data type which is [this]([https://ibb.co/9YV64qL](https://ibb.co/nLMqjqf)). Here it 0 as an agent id

As Agent  user id was default as 0, and added a conditional check in the `AvatarFallback` to show the avatar only if the `uid` is '0'. Making sure the avatar is shown only for Agent messages and not for User messages.

Here is the code for the fix:

```
const isAgent = data.uid === "0" // agent's uid is "0"

  return (
    <div
      className={cn("flex items-start gap-2", {
        "flex-row-reverse": data.type === EMessageType.USER, // User messages are on the right
      })}
    >
      {/* Render avatar only for the agent */}
      {isAgent ? (
        <Avatar>
          <AvatarFallback>AG</AvatarFallback>
        </Avatar>
      ) : (
        <div className="w-10 h-10" /> // no avatar
      )}

      {/* Message content */}
      <div className="max-w-[80%] rounded-lg bg-secondary p-2 text-secondary-foreground">
        <p>{data.text}</p>
      </div>
    </div>
  )
}
```

[testing it locally](https://ibb.co/bNjZCdJ)

I'll make a pull request for this fix soon by following the instructions in the [README](https://github.com/TEN-framework/TEN-Agent/blob/main/README.md)
