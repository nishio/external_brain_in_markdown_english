---
title: "Videoconferencing Security"
---

There are two major methods: the key-sharing method and the white-list method.
- [University of Tokyo resources [https://scrapbox.io/nishio/Zoom%E3%82%92%E7%94%A8%E3%81%84%E3%81%9F%E3%82%AA%E3%83%B3%E3%83%A9%E3%82%A4%E3%83%B3%E8%AC%9B%E7](https://scrapbox.io/nishio/Zoom%E3%82%92%E7%94%A8%E3%81%84%E3%81%9F%E3%82%AA%E3%83%B3%E3%83%A9%E3%82%A4%E3%83%B3%E8%AC%9B%E7) %BE%A9%E3%82%92%E5%AE%89%E5%85%A8%E3%81%AB%E9%80%B2%E3%82%81%E3%82%8B%E3%81%9F%E3%82%81%E3%81%AB] talks about comparing these two and choosing "key sharing" for the moment
- The "Zoom to Teams" argument implicitly assumes a "move to a whitelist system."
    - (Because with key sharing, Teams is more of a security issue.)

## key sharing scheme
![image](https://gyazo.com/50febd056e6786317cddc2415b01d8fe/thumb/1000)

The method is to share a URL or a number, and the person who has that information (represented by a picture of a key) can enter the room.

This type of system is powerless against the scenario where "the host (organizer) hands out the keys to the participants, and then some of the participants who received them are bad and give them to people they shouldn't have.
- For example, the scenario of "an insider who wants the class to go down is leaking the URL to a message board or chat room where the attacker is located."
- If some students are building up hate against a teacher, it's not surprising that they would consider destroying the class.

This problem occurs not only with Zoom, but with any URL sharing type as well.

## Waiting room system
.
![image](https://gyazo.com/d2584eba574b5c1ee70b3fc91bf22c79/thumb/1000)
A system in which newly joined users enter a waiting room rather than directly into the conference room, and the host manually moves them to the conference room.
It can be called a lobby, virtual waiting room, waiting room, etc.
Used in conjunction with a key-sharing system.

It can be enabled as an option in Zoom; with the 4/4 update, it was enabled from the beginning.

Safer than going directly into the conference room, but there are disadvantages.
- If the number of participants is large, it is not practical for the host to check each person and move them to the meeting room
- If the host does not notice someone who joins late, that person cannot join.
    - In cases where there is only one host teaching a class to students, it is easy to overlook the class because attention is focused on the class.
- In Teams, guests can only see a free input string in the waiting room and cannot turn on the camera.
    - In the "student trying to crash class" scenario, the waiting room doesn't work because the student can tell the attacker the URL and the name of another student he wants to undermine.

> A "waiting room" could be used to ensure that the host approves the meeting prior to participation, but this is not practical for lectures with large numbers of participants, and each time a participant joins after the meeting has started, he or she must be approved.
    - [[For safe online lectures using Zoom]]

## Kick
![image](https://gyazo.com/ad7beca50247428e1b4bbc3f9725d46e/thumb/1000)
The ability for the host to eject undesirable participants from the conference room.
Kick, bang, "remove from conference room," etc., as they call it.
Used in conjunction with a key-sharing system.

    - [[Removing participants in Zoom]] Removed participants cannot return to the conference room
- For Microsoft Teams
    - People who have been "removed from the room" can return to the room with a single click (why did you make it that way...?)
    - see  [[Guest participation in MS Teams]]

## white list method
.
![image](https://gyazo.com/05f3469c90606811694a33ff3eb07c1d/thumb/1000)
A method in which the host creates a "list of trusted participants" in advance, and only those included in that list can participate in the meeting.

This is a drastic measure if one wants to prevent undesirable participants from entering the conference room, but it places a heavy burden on the host.

The University of Tokyo's Center for Information Infrastructure, 2020.4.6, "[[For safe online lectures using Zoom]]" states that this method is "the original measure" but judges that it is not an option for the time being.
> To ensure that no outsiders come into the lectures,
- >  a) Use Zoom's authentication function to allow only those who have signed in to Zoom with a University of Tokyo email address (u-tokyo.ac.jp) to participate.
- > b) Ensure that third parties cannot know or easily guess the information necessary to access Zoom meetings.
>  There are two ways to do this.
> a) is an effective and original measure, but at this point, not all students know how to sign in with their University of Tokyo e-mail address and participate in online lectures. Therefore, there is a possibility that some students will not be able to participate in the lectures even though they should be able to. Therefore, the immediate countermeasure is b).

The burden on the host depends on the organization and the size of the meeting.
- For example, if the members are already managed by Active Directory (AD) and the users of the videoconferencing system are also single sign-on with AD integration, there is little burden on the host.
- Even in the absence of such systemic support, if the number of participants is small, they would be able to register individually.

---
This page is auto-translated from [/nishio/ビデオ会議のセキュリティ](https://scrapbox.io/nishio/ビデオ会議のセキュリティ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.