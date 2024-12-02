# Fixing Avatar Bug

Here is the issue: [Unfriendly Icon Representation - Issue #407](https://github.com/TEN-framework/TEN-Agent/issues/407)
## Problem:
the issue where a "U" (for User) was  shown in the avatar fallback, even when I tried to remove it. I needed a way to show avatars only for specific messages.

## First Try:
I tried changing the fallback text in the `AvatarFallback` to null or an empty string (""), assuming this would prevent the fallback text ("U") from showing. However, this approach didn’t work because fallback was still being triggered by the Redux state and Avatar component was automatically using "U" as the fallback for any messages from the user, which was not the intended behavior.

## Debugging:

I then went ahead and added few debug statement to understand the behavior of data types. ![debug](https://ibb.co/9YV64qL). Here it shows an arbitrary number for user unique id so i decided to look into this enum.

I checked the `uid` in the message data, which looked like this:
```ts
export interface ITextItem {
  uid: string;
  text: string;
  time: number;
  isFinal: boolean;
}
```
I then went ahead, and assigned '1' to Agent as user id and added a conditional check in the `AvatarFallback` to show the avatar only if the `uid` is '1'. Making sure the avatar is shown only for Agent messages and not for User messages.

Here is the code for the fix:

```
const isAgent = data.uid === "1" // agent's uid is "1"

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
        <div className="w-10 h-10" /> // Empty space for the user (no avatar)
      )}

      {/* Message content */}
      <div className="max-w-[80%] rounded-lg bg-secondary p-2 text-secondary-foreground">
        <p>{data.text}</p>
      </div>
    </div>
  )
}
```
I'll make a pull request for this fix soon by following the instructions in the [README](https://github.com/TEN-framework/TEN-Agent/blob/main/README.md)
