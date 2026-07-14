---
layout : post  
title : Dating Like an Unethical Data Scientist
subtitle : What to do when you're overwhelmed with information
category : Blog
tags :  data technology personal 
---
* [Why am I subjecting myself to online dating?](#why-am-i-subjecting-myself-to-online-dating)
    * [Making my profile](#making-my-profile)
* [Scoping the data collectiong](#scoping-the-data-collection)
* [What did I find in my data?](#what-did-i-find-in-my-data)
    * [Summary statistics](#summary-statistics)
    * [Richer data analysis (including anecdata)](#richer-data-analysis-including-anecdata)
        * [What did people interact with? And what did they say?](#what-did-people-interact-with-and-what-did-they-say)
        * [Skeletons](#skeletons)
        * [Mini golf](#mini-golf)
        * [Bowsette and the Goth](#bowsette-and-the-goth)
        * [Museums](#museums)
        * [Cocktails and Dancing](#cocktails-and-dancing)
        * [Databases and Dorkery](#databases-and-dorkery)
    * [My personal notes](#my-personal-notes)
    * [Career data](#career-data)
* [Matching and Dating](#matching-and-dating)
    * [Match data](#match-data)
    * [The dating process](#the-dating-process)
    * [The dating highscore board](#the-dating-highscore-board)
* [Information Sharing and Management (gossiping with friends)](#information-sharing-and-management-gossiping-with-friends)
* [What else did I learn?](#what-else-did-i-learn)

# Why am I subjecting myself to online dating?
I met my ex using Tinder for the first time in 2017. I deleted it after 3 days, having met them and immediately fallen madly in love. After 7-and-a-half years with them, we split last year. A few months ago I gave a cute chatty guy at a gig my number... and he never texted. Drats. 

In fairness to him, I was dressed as a clown. It's not for everyone. 

![Photo of me in clown costume](https://kiowa-scott-hurley.github.io/tea-tech-and-trials/img/dating/clown.jpg)

This experience did get me thinking about whether I was ready to try dating again. My friends had regaled me with so many first date stories and shown me their swiping habits and I wanted to join the fun. I caucused them for information on how it all worked, what the social norms were, what the different apps were like... and downloaded Hinge on the second of May.

They'd all told me it was one of their quieter apps, which sounded good. When used Tinder in late 2017, it was basically the only real option. Now we had Hinge and Bumble and Coffee Meets Bagel and...

## My goals
* Learn how to do the online dating thing
* Learn more about the social norms of going on dates
* Hopefully have a bit of fun meeting new people and learning about them
* Learn more about myself and what I like and don't like 

I didn't really expect any of the dates I ended up going on to go well, and consequently didn't think too hard about what I was looking for. I was upfront about this nebulous state with my dates, and set my profile to "Figuring out my dating style" too. 

## Making my profile
I carefully picked out my photos and prompts. A selfie and a full body photo in gothic clothes. A weird clown photo - with a friend. Something at the rail museum, a cosplay. A dorky prompt. I wanted my matches to know exactly what they were signing up for (massive nerd; alt fashion; likes dancing). I had a mini identity crisis as I tried to boil myself down to a concentrated personality. 

![Screenshots of my Hinge profile](https://kiowa-scott-hurley.github.io/tea-tech-and-trials/img/dating/hinge-profile.png)

I was shocked by the number of interactions on my profile within the first few hours. I was overwhelmed... and like any bad data scientist who can't find a good API to process the data, I started a Google Sheet.

![Screenshot of the "Hinge" Google sheet header](https://kiowa-scott-hurley.github.io/tea-tech-and-trials/img/dating/sheets-header.png)

# Scoping the data collection
I decided I'd spend the week capturing data about the people who interacted with my profile in the sheet. In reality, I got tired of manual data collection, so the scope of data was shortened to 48 hours. The data I collected can be described as:

>People who interacted (liked or commented) on my Hinge profile within the timeframe of `2026-05-03T19:00:00+11:00` to `2026-05-05T19:00:00+11:00`

Each sample (uh, person) was a row in my spreadsheet, with the following attributes: 

| Data                         | Data type       | What is it?                                                                                                                                                             |
| ---------------------------- | --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Roses                        | Yes/No          | Hinge has a feature where you can give someone a "rose" - it's like saying "I realllllly like you".                                                                     |
| Reply                        | Yes/No          | Did they actually type words or just "like" something?                                                                                                                  |
| Reply detail                 | Text            | If they typed words, what did they type?                                                                                                                                |
| What did they interact with? | Text            | What part of my profile did they interact with?                                                                                                                         |
| Matched?                     | Yes/No          | Did I match with them?                                                                                                                                                  |
| Name                         | Text            | Their name                                                                                                                                                              |
| Age                          | Integer (years) | Their age                                                                                                                                                               |
| Gender                       | Text            | Their gender (my profile was open to everygender)                                                                                                                       |
| Job (adjusted)               | Text            | Their listed occupation - later simplified into a more general category for data analysis purposes.                                                                     |
| Height                       | Integer (cm)    | Their listed height. I don't care about this (I have crushed on many people my height and shorter) but my friends seem to care. |
| Profile                      | Integer (0-10)  | A rating on the quality of their profile, out of 10                                                                                                                     |
| Hotness                      | Integer (0-10)  | A rating on their hotness, out of 10. I can be shallow too!                                                                                                     |
| Notes                        | Text            | Anything else I felt compelled to comment on.                                                                                                                           |

Early on I collected more information from profiles (sexuality, religion, politics, etc.) but I stopped as I realised I didn't really care how many atheists liked me.

# What did I find in my data?
## Summary statistics

| What?                            | Data summary                                                                                                                                                                                                                                                                           |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|                                        |                                                                                                                                                                                                                                                                                |
| Number of interactions (samples / unique people) | 160                                                                                                                                                                                                                                                                            |
| Roses received                         | 12                                                                                                                                                                                                                                                                             |
| Number of people I matched with        | 10                                                                                                                                                                                                                                                                             |
| Number of people I went on a date with | 5 (note 1 was not in the original 160 interactions)                                                                                                                                                                                                                            |
| Gender                                 | 146 Men (91%)<br>12 Women (6 transwomen)<br>2 Non Binary                                                                                                                                                                                                                           |
| Most common name                       | 7 Dans/Daniels                                                                                                                                                                                                                                                                 |
| Height                                 | Mode: 183cm<br>Mean: 179.66cm<br>Median: 180cm<br>Min: 164cm<br>Max: 201cm                                                                                                                                                                                                             |
| How many people wrote a reply?         | 64/160 <br>30%                                                                                                                                                                                                                                                                   |
| Info                                   | Mode: 7<br>Mean: 5<br>Median: 6<br>Min: 1<br>Max: 9                                                                                                                                                                                                                     |
| Hotness                                | Mode: 2<br>Mean: 4<br> Median: 4<br>Min: 1<br>Max: 8<br><br>Note: only 3 people got an 8/10<br>I find personality is a huge factor in attraction. It's hard for me to imagine rating anyone a 10 on physical appearance alone.|

## Richer data analysis (including anecdata)
### What did people interact with? And what did they say?
Looking at the raw numbers, we see a pattern of what parts of my profile got the most interactions, and which items triggered comments.

| Photo/Prompt                  | Number of interactions  | Did they actually write stuff? |
| ----------------------------- | ------------------- | ------------------------------ |
| Photo: Full body gothic       | 39                  | 2                              |
| Prompt: Dorkiest thing        | 26                  | 20                             |
| Photo: Selfie                 | 14                  | 0                              |
| Photo: Bowsette               | 14                  | 3                              |
| Prompt: Museum                | 13                  | 10                             |
| Photo: Railway                | 12                  | 1                              |
| Prompt: Mini-golf             | 12                  | 12                             |
| Photo: Skeleton               | 10                  | 4                              |
| Prompt: Cocktails and Dancing | 6                   | 4                              |
| Prompt: Scones                | 5                   | 2                              |
| Photo: Clown                  | 4                   | 2                              |
| Prompt: Opening Band          | 3                   | 2                              |
| Other (bad data collection)   | 2                   | ?                              |

Anecdotally speaking, I noticed that: 
* The lowest quality profiles AND replies correlated with liking my full body gothic photo. 
* The highest quality responses correlated with my database and museum prompts.
* I don't think it's captured in this data, but over the next couple of weeks I felt the funniest responses tended to be pitched at the skeleton photo. 

But enough of numbers - let's get to the good gossip and check out some of the responses I got. 

![Screenshot of a funny reply to the Bowsette photo](https://kiowa-scott-hurley.github.io/tea-tech-and-trials/img/dating/bowsette-please.png)

#### Skeletons 
None of these were very original - but they were all lighthearted and funny. 

| Response samples: Skeleton         |
| ---------------------------------- |
| your friend there looks stiff      |
| He was dying to take this photo!   |
| Just two cool dudes hanging out B) |
| oh hey it's me irl                 |

#### Mini golf
Look, I'd change this if I reactivated my profile because it didn't trigger great conversation. The theme was people admitting they sucked, saying the loser had to buy dinner, or saying they hadn't been in years. Standout replies for good and bad reasons: 

| Response samples: Mini golf                                                                        |
| -------------------------------------------------------------------------------------------------- |
| PLEASEEEE                                                                                          |
| Ok... not sure how ok I am with the correct assumption that I will be terrible at mini golf hahaha |
| Is this a challenge?!                                                                              |
| Let's go to unpopular one so we can take all the time we need                                      |

#### Bowsette and the Goth 
These triggered responses about my physical appearance. That's cool and sweet, but does make it hard to start a conversation. 

#### Museums
This triggered museum themed replies to other prompts too, which I liked.

* People who asked me for a museum recommendation instead: 4
* People who suggested museums: 6
* Museums I haven't been to before: 0 

Museum suggestions were pretty good: 
* The Holden Museum
* Mt Lofty Museum
* Yarra Ranges Regional Museum 
* The Vietnam Veterans museum in Phillip Island
* The Holocaust Museum
* The Bayswater Ambulance Museum 

#### Cocktails and Dancing
I liked that this highlighted people who like dancing. Given the high rate of tech people my profile attracted... well, not everyone in that demographic likes to dance. 

#### Databases and Dorkery 
This triggered some of the strongest responses. I've copied almost all of them here. I have ordered this table roughly with responses I like more towards the top. 

| Response samples: databases and dorkery                                                                                                                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The NSA fear you                                                                                                                                                                                                                                   |
| *a literal SQL query to inject a date into my calendar*                                                                                                                                                                                            |
| Oh my god, this is probably the hottest response to a prompt I've read, as someone who uses systems to document their things. Plus I need to show you this cool IG reel I found of someone making a live map of the Metro trains using LED lights. |
| *infodump on tram maps*                                                                                                                                                                                                                            |
| Ooooh do you tap as you use or do an audit style? Please infodump your system <3 also would you be interested in doing one of the longer train rides...                                                                                            |
| Usually people leave this level of dirty talk for a few dates...                                                                                                                                                                                   |
| Ok I am curious about the database thing but also YOOOO A FELLOW TRAM AND TRANSPORT NERD (though I am personally partial to trains)                                                                                                                |
| I absolutely love the database with tags! The nearest I have is my brownie recipe spreadsheet! I used to work im public transport and still geek out on that... Take me to the tram museum?                                                        |
| Wait this is so fucking cool hell yeah I love this so much                                                                                                                                                                                         |
| Best thing I've ever heard!                                                                                                                                                                                                                        |
| *infodump on home assistant system*                                                                                                                                                                                                                |
| How do you know how much product you use? Or do you average it?                                                                                                                                                                                    |
| One day I strive to be that organised and track my usage for things like that                                                                                                                                                                      |
| That's super cool! Why do you track that specifically? Is there anything else that you track in a similar way?                                                                                                                                     |
| That is the best thing I've heard on here! Does it just track which makeup you use or do you also track how much you use                                                                                                                           |
| Ok the database is up there, I don't think I've ever heard of that before.                                                                                                                                                                         |

Special mention for replies I really didn't like: 
| Response samples: bad                          |
| ---------------------------------------------- |
| Finally someone who can keep up with my autism |
| It wasn't a competition                        |

### My personal notes
In the "Notes" section I captured my unfiltered thoughts. As I worked out what the average dating profile looked like, I had less to say. I did think it might be fun to publish some of my inner monologue here. 

| Samples from my notes                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------- |
| Cutie, but not really my type<br>*Note: there was a lot of this in the notes data.*                                                  |
| Looks cute, maybe toooo nerdy                                                                                               |
| 6 cats???                                                                                                                   |
| That is a LOT of beard                                                                                                      |
| very funny reply                                                                                                            |
| The pringles man was cremated into a can???                                                                                 |
| hot but so boring<br>*Note: this profile got one of the three 8/10 hotness scores, and a 1/10 profile score. I did not match.* |
| Unclear if they're cute and bad at selfies or not cute                                                                      |
| My type. I like em with eyeliner on. I want to see more.<br>*Note: this is the only 8/10 hotness I matched with.*              |
| Mouse dissections??? Okay girl go off                                                                                       |


### Career data
Not everyone fills this in and some people fill it with such garbage data that it may as well be empty. Special mention to "Game Master Escape Room" for the coolest entry on the list. I tried to sort people into broader buckets.

There was a bit of overlap with creative/tech jobs, so I've made some executive decisions (web designer, VFX...). I've included some sample job titles in the data for reference too. 
| Item                        | Examples                                                             | Number |
| --------------------------- | -------------------------------------------------------------------- | ------ |
| Creative                    | Designers<br>Performers<br>3D Character Artist                           | 29     |
| Warehousing / Trades        | Carpenters<br>Forklift operator(10)<br>Warehousing<br>Sparky<br>Mechanic (3) | 25     |
| Tech                        | Data analyst<br>IT<br>Programmer<br>QA<br>Web Dev                            | 20     |
| Hospitality                 | Fast food<br>Chef<br>Pokies<br>Barista                                    | 9      |
| Medical                     | Doctor<br>Physio<br>Nurse                                                | 8      |
| Engineer                    |                          | 5      |
| Customer Service and Retail |                                        | 7      |
| Teacher                     |                                                                      | 4      |
| Finance                     |                                                                      | 3      |
| Social services             | Disability support                                                   | 3      |
| Law/Legal                   |                                                                      | 2      |
| Studying                    | PhD                                                                  | 2      |

Hi there forklifters <.< 

# Matching and Dating
## Match data
I thought it might be interesting for people to see who I went on dates with from a profile quality and hotness perspective. 

| Profile quality | Hotness | Average | Matched / Dated? |
| --------------- | ------- | ------- | ---------------- |
| 5               | 6       | 5.5     | Matched          |
| 6               | 3       | 4.5     | Matched          |
| 6               | 7       | 6.5     | Matched          |
| 7               | 3       | 5       | Matched          |
| 7               | 6       | 6.5     | Matched          |
| 7               | 3       | 5       | Matched          |
| 7               | 7       | 7       | Dated            |
| 7               | 8       | 7.5     | Dated            |
| 8               | 6       | 7       | Dated            |
| 6               | 6       | 6       | Dated            |

I tended to match with people who had actually said something interesting in response to me - it was probably the easiest filtering mechanism to use. Exceptions could have been made for people with very interesting profiles or who were extra cute - but that didn't appear in this data. 

If I was talking to someone and interested in them I basically asked them on a date within the first 24 hours of talking. With this approach, I have been on dates with 5 unique people from 2nd May until now (4 of which are captured in the data presented here). People responded well to my very direct approach. I didn't really want to text for weeks - I wanted to organise a date, text between now and then, and see how it went. 

Here is what my May / June calendar ended up looking like, where each unique person has their own emoji and colour: 

![Screenshot of my date calendar](https://kiowa-scott-hurley.github.io/tea-tech-and-trials/img/dating/calendar.png)

## The dating process
Some things I learned about myself while doing this... 

* Dates with activities were a lot better in terms of not needing to make eye contact for 2 hours, and there being natural pause in conversation while we did something else. 
* Dates with walking were good because if you liked the person you could hold their hand. 
    * A note on physical contact: One person didn't hold hands with me until the third date, when I initiated. One person kissed me on the first date. The range was huge in what to expect. This is really hard to navigate when there are no real rules. Speaking of... 
* Dating has made my neurodiversity more apparent to me. 
    * I mostly navigate social norms in a well understood work context with other STEM nerds. 
    * Dating is a different context with a more diverse audience, and context changes from date to date too. 
    * I have no idea how it works. 
    * It was obvious on some (all?) dates that I was being "weird". I mostly leaned into it. 

I told every date about the spreadsheet, the fact I was learning what I was doing, and the fact I was multi-dating. 

Everyone seemed to appreciate the honesty even if they were a bit confused or... well, whatever the normal response to your date admitting you're in their database is. Only one person has had the guts to ask to see their entry.

It was honestly weird to reduce people down to their data this way - but when you have 160 people attempting to talk you in a 2 day span, and your goal is actually going on dates with people face to face, there's a filter mechanism happening regardless.

## The dating highscore board
|Emoji | # of dates   | Comments | 
|---| -----------------------------------------------------------------------------------------------------------------------------|-----------|
| Cartwheel | 1| Really lovely (clever, lots of cool hobbies, originally planned a second date) but I liked other people by the time we met. |
| Skateboard | 2 | Very pretty and interesting to talk with, would have gone on more dates if they'd asked.                                        |
| Laptop | 3 | Some compatibility issues came up but I had fun.                                                                               |
| Duck | 5 | Very cute and sweet and extremely interesting. Someone is gonna fall so hard in love with 'em one day.                          |
| Top Hat | 7 | Interesting. Funny. Gorgeous. 7 dates was not in the experimental plan.                                                           |

# Information Sharing and Management (gossiping with friends)
My friends were all extremely excited to hear about how things were going, but also found it challenging to keep up with who was who in the (Excel) zoo. 

I keep a list in my notes app to keep track of who my friends are seeing.  I don't want to forget that Ryan is the one with tattoos who doesn't like ice cream. To be honest, I was having trouble keeping up with the information at this stage too - so I resorted to a summary Google doc, featuring the date calendar, and 1 page profiles for people I was going on a date with / had been on a date with. 

![Photo of Google docs side bar with date names redacted](https://kiowa-scott-hurley.github.io/tea-tech-and-trials/img/dating/document.png)

![Photo of a heavily redacted date summary](https://kiowa-scott-hurley.github.io/tea-tech-and-trials/img/dating/profile-summary.png)

*Note: this is a screenshot of a real profile which has been heavily redacted. This person was not into fishing as far as I knew. They had a lot of cool hobbies. Sorry if you see this bestie, this is not a reflection on you.*

# What else did I learn? 

Just be yourself~ 

Okay, okay, in seriousness...

This is not a comprehensive list, but I did learn some things about what I'm looking for from a date. 

* A curiosity mindset and a love of learning new things
    * This is part of why I get along with engineers, but it's not exclusive to them. 
* Willing to come to live music at dive bars with me
    * I don't know that I realised how much this mattered to me. I love music. 
* Willing to dance with me (and try new things in general)
* Has a few hobbies 
    * and is excited to talk about them! 
    * No seriously, I want to learn new things from the people I like.
* Has a social life that meets their needs, or is actively working on it.
    * This feels ridiculous to write down but...
    * I'm finding a lot of men especially in my age range are outgrowing their friends or don't have friends, and are feeling lonely as a result. 
    * This isn't about them having lots of friends - I have a few close friends but that interaction mode meets my social needs. Dating is a bonus, not a fix. 
    * I feel like it puts pressure on our connection if I'm one of my dates' only social outlets.
    * It also feels unbalanced when I have a full calendar and the person I'm seeing has nothing else on???

I've also learned that while no one likes being rejected, people tend to be kind and thankful for anything that isn't ghosting. Huge respect to the pleasant and kind responses I had from people who I eventually turned down. 

# What now?
I've paused my profile while I see how the in person dates pan out - the digital data sorting is fun, but the real goal is meeting humans and connecting with them, not filtering columns and rows. 




