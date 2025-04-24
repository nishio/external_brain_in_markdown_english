---
title: "Digital Democracy 2030 Study Group"
---

- 2025-04-11  [[Cybozu Labs Study Session]]
- I'm going to talk about [[Digital Democracy 2030]], which I've been working on recently.

# Project Summary
.
## Background of launch
.
- Press conference by Takahiro Yasuno on January 16, 2025 to launch the "Digital Democracy 2030" project
- Official Note article:[Takahiro Yasuno, full transcript of the press conference for the launch of the AI project "Digital Democracy 2030"](https://note.com/annotakahiro24/n/nfd4a855cd1a8)
- Video of press conference: [YouTube Live](https://www.youtube.com/live/hlfQBK5dcUU)
## Project Objectives
.
- Realization of a new form of democracy using AI and digital technology
- Implementation in Japan of a [[citizen-participatory policy formation process]] like Taiwan's "[[JOIN]]".
- Visualization of diverse opinions, including the voiceless, and their reflection in policy
- Realizing a Digital Vision of Democracy for 2030

# political echoes
## Response from opposition
.
- National Democratic Party:
    - Secretary General Haruha Katsuya: Mentioned Taiwan's "join-in" and considered participating in the project.
    - Councilor Takae Ito: Consideration of the use of the KDPJ in the policy-making process
    - Representative Yuichiro Tamaki: Supported as "a system that gathers the wisdom and power of all citizens to create policies and laws.
- Constitutional Democratic Party of Japan:
    - Acting Representative Kiyomi Tsujimoto: expressed willingness to participate in the demonstration experiment.
- Japan Restoration Association's response.
    - Representative Hirofumi Yoshimura, Governor of Osaka Prefecture:
        - Express support for the project
        - Proposed to utilize a focus on "reforms to lower social insurance premiums and social security reforms."
        - Willingness to use broad listening and AI to develop policy
## Political Significance
.
- Several opposition parties officially announced their participation.
    - Pointed out as a possible key to regime change
- Nishio comments, "If all major parties support digital democracy, Japan will move forward regardless of which party is in power."
    - I want the ruling party to do it against the opposition.
- Evaluation of Mr. Anno's "Lagrange Point"-like strategy
    - <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4.5/icon' alt='GPT-4.5.icon' height="19.5"/>
        - Lagrangian point-like strategy is "a strategy of taking a position in a situation where there are several large forces, and where these forces check each other and cannot move, or where it is difficult to move aggressively to take a position.
        - In physics, a "Lagrange point" is a point where gravity is in balance and a small object can exist stably. Applying this metaphorically to strategic theory, it refers to a method of finding a place where several strong competitors are in conflict or checks and balances with each other, where it is difficult for them to intervene in order to maintain their balance, and how to avoid competition and establish a stable position there.
    - We do not support any particular party or advocate regime change.

# Main Products
## Broad Listening "Broad Listening AI"
- Overview:
    - Developed in reference to "Talk to the City
    - Functional improvements tailored to the practices of Japanese local governments and politicians
    - Using AI to analyze citizens' voices for policy making
- Technical Features:
    - Deployment to Azure, Docker, and other infrastructure aspects
        - Previous versions were styled to run Python scripts at the analyst's fingertips
        - Reports can now be obtained by CSV upload, followed by import from Google Spreadsheet, so that results can be obtained without the need for engineering work.
    - Ability to visualize large numbers of opinions in a short period of time
    - Design to withstand large scale public comments such as 30,000 is under consideration
## Large-scale deliberation support system "Idobata"
- Overview:
    - Online platform for gathering and discussing the opinions of a large number of people
    - Provides a forum for large-scale discussions in which a large number of citizens can participate
- Technical Features:
    - New functions to support discussions with AI, such as SNS-connected bots and visualization of issues
    - Active testing of "idobata-analyst" in action and suggestions for improvement
## Demonstration
.
- Tokyo AI Strategy Idobata Conference" website will be open to the public (March 10, 2025).
    - Citizen-participatory discussion on the issues of the Tokyo AI Strategy Council
    - Utilized in discussions at the Tokyo AI Strategy Council, of which Yasuno is a member
    - Gathering citizen input on municipal AI strategies

# Project Progress
.
## Activities for Week 1 (March 13 - 19, 2025)
- Community Launch:
    - Set up Slack for development groups & user groups
        - Slack has been a success, attracting more than 250 participants in the first day after the public announcement.
        - A little more than 500 people as of 2025-04-11
            - Analytics for 5/9
            - ![image](https://gyazo.com/8d771103ca59b791988c16d08f69c2ec/thumb/1000)
    - Multiple development channels launched, including "IdoBata" and "Hiroko AI."
    - Diverse members including programmers, designers, PdMs, and municipal officials gathered in a self-introduction channel.
    - Participants with a passion for "participating in OSS development," "solving social issues with AI," "digitally updating government systems," etc. will gather.
- Development of the Idobata system:
    - GitHub repository is opened to the public, and the initial development environment is being developed.
    - Progressive improvements focused on improving ease of use
    - Documentation makes it easier for repository users to get an overview of the project and contribution rules
    - Improvements begin to be made for access from a variety of devices, including mobile compatibility.
- Development of a wide hearing AI:
    - Unification of development environment through Dockerization, consideration of features to facilitate deployment to Azure, etc.
    - Increased discussion on UI improvements
- Community Outlook:
    - Expectations are high that the demonstration experiment will not only be conducted in Tokyo, but will be expanded to other regions as well.

## Week 2 (March 20, 2025 - March 26, 2025) Activity
- Community growth:
    - More participants since last week, active exchanges throughout Slack
    - Significant progress was made, especially in the development of "Idobata" and "Hirohyo AI".
- Idobata development gains momentum:
    - Active discussion on creating new functions to support discussions with AI, including prototype SNS-linked bots and visualization of discussion points.
    - Meet and work sessions are held among developers to test "idobata-analyst" in action and make suggestions for improvement.
- Progress in Broad Listening AI (Broad Listening):
    - Deployment to Azure, Docker, and other infrastructure improvements are proceeding at a rapid pace.
    - Increased opinion analysis using test environments
    - Progress is being made in studying the application of functions to improve the efficiency of public commenting operations (DX) at government ministries and agencies and local governments.
    - Cases of actual in-house and civic group pilot implementation will also be reported.
        - This in-house case study refers to my introduction of Cybozu.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Spread of new linkages:
    - Consultations in collaboration with several municipalities and researchers reported
    - How AI can be used in government and politics" begins to be considered in concrete terms.

## Activity for Week 3 (March 27-April 2, 2025)
- Summary of Activities:
    - A total of 126 messages exchanged on 9 channels
    - Several major development projects and event preparations take center stage
- Progress in broadband AI development:
    - Code maintenance: consultation around formatters such as Prettier and Ruff, Makefile and Docker-related refactoring in progress
    - Deployment operations and data persistence issues: Issues with deploying to cloud environments such as Azure Container Apps were discussed, and the question was raised, "Wouldn't it be better to work with external storage such as S3?" and "Shouldn't we work with external storage such as S3?
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>This is because I did First Penguin and found out that "if you try to follow OSS updates and docker build & push, the generated reports disappear because the container is overwritten", so I knew I needed to deal with it.
            - If docker compose up in the local environment, the local file system is mounted, so the report is not lost even with re-build.
                - -> You may not realize where they are stored. /server/broadlistening/pipeline/outputs/* is the individual data and server/data/report_status.json is the list
            - For example, if you build and deploy a container to Azure Container Apps, the generated reports are stored in the container, so when you build and deploy new source code, the behavior is that "the container is replaced by a new one = the existing reports The existing report will disappear.
                - -> /scripts/fetch_reports.py can save it on hand, so you can do that.
            - I've been running a server that I've been setting up experimentally, volume mounted in a VM.
    - Support for large data: "We want to design the system to withstand large scale pubic comments, such as 30,000 comments," and discussions are underway on how to improve memory usage and clustering performance of embedding.
- Continued development of the Idobata system:
    - Major improvements to the user interface are underway.
    - Enhancement of discussion visualization function: Development of a function that organizes multiple opinions and categorizes and displays them by issue.
    - Consideration of multilingual support: Discussion of multilingual support with a view to future international expansion
    - Proposals for the development of a mobile app version begin to emerge.
    - Increased activity in functional improvements based on feedback from actual user testing
    - Discussions begin on the function of linking "IIDOBATA" and "Hirohiko AI".
- Hackathon Preparation:
    - Preparations are underway for a hackathon to be held in mid-April.
        - This is the [Digital Democracy 2030 MeetUp Offline&Online | Peatix](https://peatix.com/event/4368640) that will take place tomorrow, 12
    - Discussion on participant recruitment and venue arrangements

## Activities for Week 4 (April 2 - 9, 2025)
- Overall community activity:
    - A total of 887 messages were posted across Slack, with lively discussions centered on "Idobata" (252 messages) and "Spreading AI" (95 messages)
    - New channels such as "Beginner's room" and "Design_general" have been added to enhance the system for accepting new participants.
- Development of the Idobata system:
    - PRs for new features and bug fixes merged one after another on GitHub
    - CSV preview functionality, improved sample data, and CI implementation to improve development efficiency are progressing.
    - Discussions expanded to include enhanced mobile support and pilot operation of SNS-linked bots.
- Development of a wide hearing AI:
    - Numerous Issues/PRs closed, including [[Azure Blob Storage]] integration, formatter introduction, and cluster analysis enhancements.
        - Reports generated in the [[Azure Container App]] environment are now persistent.
    - Windows environment support, measures to control excessive summarization, etc. are still under discussion.
    - Increased demand for improved clustering performance and UX improvements when handling large data
- New project "Political Funding Board":
    - Politicalfunds" repository goes live, launching an initiative to make political fund balance reports visible.
    - Future development policies and collaboration plans to be discussed at regular weekend meetings
- [Preparation for the Hackathon (4/12): Discussion on how to proceed with both online and offline activities, management of the reception, work rooms for each theme, etc.
    - Plans are underway to utilize social networking services, group photos, live streaming, etc. to attract participants.
- This week's summary: New members continue to join, and a support environment for non-engineers is in place.
    - The community is becoming even more active with the exchange of ideas and opinions at the regular Saturday night general meetings and events every week.

# Future Prospects
## Transformation of the policy formation process
.
- Standardization of citizen participation in policy making
- Comprehensive policy formation by making the voiceless visible
- Rebooting Democracy with Digital Technology
- Deployment in each region as well as in urban areas
## Vision for 2030
.
- Adoption of digital democracy by all major political parties
- Establish a political system that directly reflects the voices of citizens
- Evolution of Democracy through AI and Digital Technology
- Establishment as common ground across political parties
# Conclusion
.
- Digital Democracy 2030" is not just a technology project, but an initiative that has the potential to redefine democracy in Japan.
- Potential to attract support across party lines and become common ground across political divides
- Sustainable development is expected through open source development and community building
- The innovation and promise of Mr. Anno's "Lagrange Point"-like strategy

disclosing the secret of a trick
- Devin is making this document in its entirety.
    - The reordering of the sections was indicated by looking at what was generated
    - The detailed bi-weekly events are published by the [[OSS Weekly Reporter]] and put on their website, and I give them the URL and let them read it in their browser.
- I use [[o1 Pro]] and [[GPT-4.5]] to correct minor details later.

---
This page is auto-translated from [/nishio/デジタル民主主義2030勉強会](https://scrapbox.io/nishio/デジタル民主主義2030勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.