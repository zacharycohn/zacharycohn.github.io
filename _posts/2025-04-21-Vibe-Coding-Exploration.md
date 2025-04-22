---
layout: post
title: Vibe Coding Exploration
---

*This journal-entry style blog post chronicles my first few weeks of building software entirely with AI tools like ChatGPT and v0.dev. I’m including some learnings along the way \- mostly so I don’t forget about them in the future. While I’m numbering the days sequentially, and Day 1 and 2 were adjacent, other days may have gaps in between them as I worked on other projects.*

# Background: 
I work for a (very) small hardware startup \- 4 people. We are currently without a software engineer, but it hasn’t been an issue given the stage we’ve been in and the work we’ve been doing. 

I started my university degree in computer science, but ended up dropping out of the program (and not for the “i’m going to start a billion dollar startup” sort of reasons). I enjoy coding recreationally and writing little one-off scripts professionally, but am absolutely not a software engineer. But I’m also the closest we have, so I decided to use ChatGPT to see how far I could get.

## Day 1: Newfound Enthusiasm   
For \[legitimate reasons\], we decided we needed to quickly build a prototype of a potential hardware/software experience. This involves interacting with speakers and microphones, multiple cameras running on multiple devices, interacting with the video feed, and some 3rd party API calls.

And…… wow. The answer is pretty far. There’s one bug left with one of the 3rd party APIs, and I haven’t integrated the video feed stuff yet (but I have pre-existing code that does what I need there), but otherwise I built the whole prototype in 4 hours. And that’s not even using any coding-specific AI tools, just bog-standard ChatGPT o3-mini-high.

### A few learnings from today:
* I didn’t really read the code it was generating \- partially because a lot of it was a bit over my head, and partially because it was just a lot of code being generated really fast. So I ended up wasting an hour because it decided to write the line (and this is character for character what it typed) *input \= "\[user input here\]"*  instead of… you know. Actually using the user input. So I spent a long time trying to get it to figure out why my input was getting lost, when I should have just looked at the line of code. I got a bit sour about that one.  
* Tomorrow, I’m considering pasting the code into a different ChatGPT session and asking it to code review the first session and look for issues.  
* My first prompt was a bunch of background information, features, requirements, etc. Then I told it “Do not start coding right away. Instead, think about what I asked you to do. What questions do you have for me” It asked some good questions that definitely helped refine the direction of v1. I probably could have asked it to do that one or two more times. I bet there’s some other “before you start coding” steps I could do next time to make this go even better.  
* Its first attempt at writing the API calls failed miserably. After a few rounds of troubleshooting, it did tell me “Well I don’t actually know if this is how this API works \- I just guessed. I’m not familiar with this API.” After some inquiry, I found out the API was released after the training data cut-off date. So I copy and pasted the documentation in. That helped, though I’m not confident that approach isn’t causing different issues. I’d love to use a tool that can actually go out and reference a website I give it.  
* On that note, the hallucinations are tough to catch and frustrating when they happen. It doesn’t know something so it tries to be helpful and make something up, but obviously that doesn’t work. I wonder if adding a set of rules at the beginning of the project might be helpful (“If you don’t know something, don’t make it up \- instead just tell me so I can get you the information you need.“). I don’t know if telling it “don’t hallucinate” would actually help, but it’s worth a try.  
* I did feel a bit like a brainless monkey. I spent most of the afternoon pasting code into SublimeText, running it, then pasting the console output back into ChatGPT. At some point while debugging I even stopped asking it questions or telling it what to do, I just pasted the console output and hit “send”. Is there a way to automate this? Give the AI the outcome I’m looking for (plain language unit and integration tests, basically), have the AI generate the code, then run the code in an environment, then look at the output, then make corrections itself? Then only ask me a question if it gets stuck and needs direction. Because I’d love to set that up, have it run by itself, then go get coffee while it works through the problems and iterations itself. *\[Edit \- apparently that’s called an agent.\]*  
* It was cool to have a \~600 line app written in 4 hours. By myself, at my skill level, it probably would have taken me 1-2 weeks to do this. Maybe longer. But it certainly was not as rewarding as writing code myself. The level of satisfaction when a bug was fixed was “Okay, great, now onto the next bug.” rather than that feeling of intellectual victory and having solved a puzzle..  
* I’d be very nervous about using this as production code. There may be subtle bugs or security issues here that I’m certainly unqualified to catch, but even as an experienced engineer I could see how it would be easy to fall into skimming through the code but not really study it (after all, it’s working\!). The most effective code reviews are on small snippets of code, not huge diff dumps. Coding this way, then reviewing it afterwards, is essentially coding by huge diff dumps.

Overall, for my first experience doing any serious amount of coding with gen AI, it was pretty impressive. I’m interested in what tools I should try next that are a little more designed for what I’m trying to do

## Day 2: Harsh Reality  
Well, talk about a crash after the high. Today was awful. That “one remaining API bug” I mentioned yesterday? I gave up after 6 hours of trying to fix it. If you brainstormed all the things an LLM could do to sabotage you, I probably hit most of those today. Ultimately, it wasn’t a critical part of the demo, so I decided to come back to it later and not waste any more time.

Everything from “it turns out I just simulated what this API implementation could look like instead of using the actual documentation provided” to “Oh, that didn’t work? Okay, I refactored the whole app to use a different API” to hallucinating endpoints that don’t exist to not including all the necessary information in the API calls. 

### Things I learned today: 
* If something doesn’t work, you can toss it back to the AI with the message “here’s the error output, go fix it” two or three times. But after that, if it still doesn’t work, you probably should stop being lazy, put on your troubleshooting hat, and work together to tease apart the problem, understand it together, and then the fix may become clear to one of you.  
* Sometimes I am smarter than the AI. The symptom is over here, but based on my experience and general knowledge, it smells like the problem might actually be related to something else. I can say “fix it” over and over and over again and it will keep focusing on the wrong things.   
* Whenever you’re about to do something complicated, or working on a tough bug it can’t figure out, the phrase “Don’t write any code. Instead…..” is really helpful. Examples include: “... brainstorm all the ways you could approach this problem” and “... carefully review the code. List all your hypotheses as to what could be causing this bug.” Sometimes it has good ideas, and sometimes it has ideas you absolutely don’t want it to pursue. This lets you pick and choose what changes it implements and avoid unnecessary refactors and changes.  
* Sending the code to another AI, who I prompted to be an extremely detail oriented senior software engineer who does excellent code reviews, was still helpful for this project. I could go back and forth with my AI Code Reviewer, then when we got to a potential solution, I passed it back to my AI Engineer. That kept the context and chat history, and therefore the direction, cleaner for my AI Engineer. 

\[Edit: a week or two later, I did finally come back to this part of the project. With some fresh eyes, a bit of distance, some more precise prompting, and doing more manual code review, I was able to get the bug fixed.\]

## Day 3: A More Complex App  
I had a big part of my demo built. Now I needed a prototype PWA/mobile app. This was going to be decidedly more complex than some python scripts, and I was getting tired of copy and pasting so much code from my browser to Sublime, so I decided I needed a new tool. 

I tried Cursor, but having never used VSCode… the learning curve was pretty steep. I needed to learn a whole IDE, on top of Cursor. After about 30 minutes, I decided I probably needed an intermediary step before coming back to Cursor. 

I did some research and decided to experiment with [v0.dev](http://v0.dev). It’s made by Vercel, who maintains Next.js and a cloud PaaS (platform as a service) product. It seemed like it could do it all \- you talk to it, it builds your app, it shows an interactive localhost-style preview, then you can press literally a single button that says “Deploy” and it builds and deploys it for you to Vercel \- no setup or configuration needed.

I spent an hour playing with it this morning without telling anyone, and my mind was absolutely blown. I wrote up a description of the prototype app I wanted, hit “send”, watched as it pumped out code for 3 minutes, and then…. I had a working app. I didn’t dictate the design, but the layout was almost exactly as I imagined it. Most of the features worked as I described. 

It took another 2 hours of bug fixing and feature tweaking, but within about 3 hours I had a huge portion of our whole prototype app built. Another 3 hours on the most complex feature that interacts with an API and I was basically finished with it.

Now, some disclaimers: 

* This is greenfield. New development. There’s no existing codebase.   
* This is a prototype app \- not a production app. So there’s lots of shortcuts here and I don’t really care about scalability or security.  
* This is not a particularly complex app. It’s a CRUD app that makes some API calls and displays the data it gets back.

But all that being said, we had a software engineer build a similar prototype app over the summer in about six weeks. This took me 6 hours. (Granted, some of that 6 weeks was time spent figuring out and iterating on the UX and the features. I was able to take advantage of all that learning for this project. But it would still take a day or two to implement some features, only to find out it didn’t feel right and we’d try something else.

### My big learnings: 

* This is so much faster than even low fidelity prototyping in Figma. When we were designing the app over the summer, we built clickable prototypes in Figma that felt great, but when it got translated into code and we got to actually use it, it didn’t feel right anymore. This jumps you straight to “does this feel right” a thousand times faster than clickable prototypes. I do still think ultra-low fidelity prototyping is useful first though \- mapping things out with pencil and paper. \[edit: tomorrow I’ll talk about another way to accelerate the start of a new project\]  
* It feels incredible to be calling out “I built a login system” or “This feature is done” or “that feature is complete.” every few minutes. I was having an unrelated brainstorming session with my CEO, and every so often I’d tap-tap-tap a few things on the keyboard. Then a few minutes later, another feature was implemented.  
* The “Fix it” button is MAGICAL. I had it implement an API feature, I ran the app, and the API call failed. Then a little modal popped up with the error and a button that said “Fix it?” I squinted at it, then clicked the button. It pasted the error message and the logs into the chat, thought a bit, then fixed the error. Absolutely magical product experience.  
* That being said, the “Fix it” button doesn’t work just as often as it does work. A lot depends on the specific error, error message, and what information gets logged. If clicking “Fix It” doesn’t work after the second time, it’s time to ask it to add more console logging or take a different approach. I definitely have wasted a lot of time hoping the *this time* when I click “Fix It”, it will work \- like I’m rolling a 20-sided die and waiting to hit a 20\.

## Day 4: A Passing Idea  
While talking about our long-term plans, my CEO said “maybe one day we could build an app that does X.” 

That night, my 7 month old decided she would only sleep if she was being held. So it was 3am, I’m sitting on the couch with a sleeping infant in my lap, and I just finished the last episode of *AP Bio*. I remember that app idea my boss had and think “Huh. I bet I could build that before the family wakes up.”

So I go to ChatGPT (o3-mini-high) and write down a high level description of the app. I include as much detail as I can think of on the primary feature. Then I ask it “please convert this into a detailed product and technical spec. But first, ask me a series of questions to deepen your understanding of the requirements, the features, and the goals of this application.” 

It went through and asked me about a dozen really good questions. Some were technical (do you want the backend to work this way or that way, do you want this to be a one-to-one or one-to-many relationship), some were product-driven (should users be able to do X or Y?), and others were suggestions of other features I might want to consider that I hadn’t mentioned. 

After I finished answering the questions, it generated a 2-3 page outline of the product and engineering requirements. It’s something I could have done, and have done many (many) times in my career, but A. would have taken me a few hours to distill down and write so concisely and clearly, B. it’s the sort of grind-y work I find a bit mind-numbing at this point.

I copy-pasted that document into v0 and said “build it.” 

And it…. just… did. 

I spent maybe a half a dozen iterations on some of the UX patterns, then about a dozen iterations on the core feature which involved some fairly complex code. But by the time I went to work that day, I had a working version of the “maybe one day” idea my CEO mentioned off-hand the day before.

### Learnings: 

* ChatGPT is very good at the “dump it all your ideas then have it clean them up into a structured document to send to the AI Engineer” sort of work. It’s also very good at asking follow up questions if you prompt it to. I think in the future I might nudge it to ask more follow up questions.   
* You do need to read the spec it prints out though. It does sometimes leave things out. Or sometimes doesn’t phrase something as clearly as you think it should be phrased. Or it will include something you don’t want it to include. I’ll often have it revise the product spec two or three times before sending it to v0.   
* The more complex the code, the worse job it’s going to do, and the worse it will be at debugging. The CRUD app was very straightforward. This app had a particularly complex feature that required some specialized-but-common libraries. It was eventually able to get it working, but it definitely had trouble using those libraries correctly and consistently.   
* It feels like giving it as much detail as you reasonably can up front, and then as narrow instructions as possible for each subsequent iteration, is a good path forward. The upfront context lets it build the architecture, the structure, and all the low-hanging fruit features of the app. Then when you want to fix a bug, add a new feature, or refactor something, get surgical to make sure it doesn’t introduce a bunch of unnecessary or unrelated changes.  
* One example of this is what I call “Refactor wars.” You ask it to build a feature. It does, but it doesn’t work. You tell it to fix it. It says “Okay, I did a huge refactor and improved how this works by rewriting a gigantic portion of the application.” You tell it the feature is still broken. “Okay, I did a huge refactor back to the old way and improved how this works by rewriting a gigantic portion of the application.” Back and forth, forever. Or it constantly swaps between using Library A and Library B, when maybe the problem isn’t even related to the use of those libraries. 

## Day 5: Personal App  
Last night, my dog decided not to pee on her evening walk. That means at 4am this morning, I wake up to a pitbull panting in my face. I push her away, but I can feel her breathing on me. She only does this when she needs something. So I take her out to pee. She has a 73 second pee \- she really had to go. 

We get back inside, but it was 47 degrees out there and now it’s 4:30 and I’m wide awake. I sit on the couch, open my laptop and think about what to do. I have about 2 hours until the kids wake up. I reflect on how my wife and I are trying to get better at meal planning, but don’t have a great system for that right now. 

So I decide to build a meal planning app. 

I fire up ChatGPT and spend 30 minutes typing away on my laptop all the features I want and pages I need and how I envision this meal planning app works. 

Then I feel warm air on my leg. I look over my laptop and see my dog, panting again. I sigh. She also didn’t poop last night.

So we suit up and go outside again. I figure I might as well get her full morning walk in at this point. So I pull out my phone, copy the spec from ChatGPT, open up v0 on my phone, and paste the spec in. I put the phone in my pocket. Five minutes later, I open my phone again and check on it. I look at the preview, and there’s a login screen staring back at me. I log into my new app, and the whole thing is there. 

Like I’ve said before, there’s a few features that got messed up, and a few bugs, but in general… the entire app, almost exactly how I envisioned it, is there in front of me. 

I do a few iterations from my phone on the rest of the walk. By the time I get home, the kids are up (early). I sneak a few more iterations in from my phone while they eat or while they’re reading books. Then I drop them off at daycare, hop on my scooter and head to the light rail to commute to work. While I’m on the \~18 minute train ride, I do a few more iterations. I get off the train and do another iteration from the elevator. Two more at the landing before I leave the station, and I realize v1 of the app is done. 

I hit the deploy button, hop on my scooter, and zoom off. A few minutes later, I stop at an intersection with a particularly long wait. I pull out my phone and grab the public Vercel URL. I send it to my wife and friends. 

“Hey. Look what I built this morning. Almost entirely from my phone.” 

Again \- it’s still a prototype-quality app. There’s no database (although v0 does integrate with Supabase, which I’m hoping to try soon), the login system is elementary, I haven’t done any review to find and fix security issues. 

But still. It’s mindblowing. I had an idea at 4:30am, and by 9am I had built and deployed it exclusively from my phone (with the exception of building the product spec on my laptop). And my friends were using it\! 

### Learnings: 

* v0 works, but doesn’t work great, on the phone. Just so you know. I find it works best in Chrome if I enable Desktop mode. The mobile-optimized view has a bunch of navigation and latency issues that make it really difficult to use. But even the Desktop version doesn’t *love* when your screen turns off. It will work in the background, but there’s a much greater risk v0 crashes or gets stuck and loses the progress on the current iteration. v0 definitely wants to be a desktop browser webapp though. But that makes it all the more impressive what you can do from your phone. (But seriously, Vercel, please improve the mobile experience)  
* I found I used voice-to-text a lot to write the prompt for iterations (obviously not on the train though. I’m not a monster). It felt nicer than typing it all out on my mobile keyboard.  
* I’m going to build so many little utility apps with this, then install them as PWAs on my phone to make them easily accessible.   
* All this is on v0’s $20/m plan. They don’t do a great job describing some of the limits of that plan, but I haven’t hit any limits yet.   
* You can deploy to custom domains. I haven’t tried it yet, but it opens up a lot of options.

## Concluding thoughts:   
This was long. Thanks for sticking with it\! A few things I’ve pondered as I’ve gone though this experience: 

### Junior devs  
It used to be kids learned to code by struggling with some tutorials until they passed college or their bootcamp and became junior devs, who learned how to be mid-level devs through practice, experience, and mentorship from senior devs. 

How does any of this work now? Why would a 12 year old struggle to learn to code when they can get the app they want by just describing what they want to a website. How does a junior dev code review, understand, and learn when the AI generates thousands of lines of code in a few minutes. Why would companies hire a junior dev when these tools can pump out similar quality code in minutes for $20/m. 

Then, in a decade or two, how do you have enough engineers who understand how things work? Or do you just end up with AI generating the code to power the next AI to generate the code to power the next AI, and we don’t even have the faintest idea of how any of it works. Not because it’s too advanced for the human mind to understand, but because we essentially stopped the production of new software engineers, and all the existing ones who did understand have since retired?

Arthur C. Clark said “Any sufficiently advanced technology is indistinguishable from magic.”  But what if we’re hurdling towards a future where “any sufficiently advanced technology is indistinguishable from magic because the next generation never bothered to learn and now we’ve forgotten how it works?” Not as catchy.

But I don’t know. It doesn’t feel great.  

### New problems to solve?   
B2B sales is tricky. For bigger customers, the sales cycle can take a long time. For smaller customers, it can be hard to reach enough of them at scale. If you’re going after small businesses, you need to charge enough that it’s worth the investment (in both the product and the sales cycle). That means the problem has to be big enough to justify the expense to the small business. 

That’s fine \- there are plenty of those big problems that are worth spending big money on. But there’s also a million tiny problems small business owners face. Problems that are worth paying to solve, but not a lot. Or problems that are very specific to their business. We’re talking about “utility” software here.

Historically, it was hard to build a business at the combination of “low price point \+ small business Go To Market motions \+ solve unique problems for each customer \+ the expense of building software.” 

But is there a business model where you pay me a day-rate and I sit down with you for an hour, learn about your problems, then build a very targeted app for you in the next 3 hours. I spend an hour testing it on the floor, then spend 2 hours iterating and improving it. That leaves enough time for lunch\! The app gets deployed, then for a small monthly fee I keep it running for you.

Maybe I take auditing shipments from a two person job to a one person job. Or I cut your weekly ordering process from 4 hours to 1\. How much is that worth to a small business owner? 

This is the sort of software that might have taken a few days to a week before. And it’s hard for a small business owner to pay for a week worth of software engineering time. But one day? A new business model might be possible where it wasn’t before.

### Can or Can Not, There Will Be Try  
There’s a lot of discussion around what these AI development tools can do. It’s exciting and intoxicating to see code fly by you like you’re in the 1995 masterpiece *Hackers* and see a working app fall out the other side minutes later \- but I think the more interesting question is what can they *not* do? 

People will try to whack everything \- nail or otherwise \- with this hammer. [Some people have already experienced the consequences](https://x.com/leojr94_/status/1901560276488511759). Like I said earlier, greenfield and prototype software is certainly a sweet spot for these tools. No legacy codebase to consider, no other code to interface with, you don’t really care about security or scalability. But how does it do in an existing, complex, or legacy codebase? In a situation where it’s not aware of the build and deployment details. In a regulated environment, or when handling sensitive customer data. 

v0 obviously isn’t that tool \- just look at the name. Something like Cursor would be more appropriate for some of those situations, and I don’t know as much about that (yet). But there are already a million Youtube videos out there about “how to build an X app in 7 minutes with Y tool.” To any content creators reading this \- it’s a far more interesting discussion to talk about how this can be effectively used in a large, complex, legacy codebase (which are way more common than total greenfield development).

On that note though, I’d love to see companies like Vercel partnering with companies that offer automated security scanning software. While that doesn’t replace a human-driven pentest or code review, it would be awesome to have v0 generate some code, then scan it for vulnerabilities, then iterate on the code to fix any reported issues, then repeat that until the scan comes back green. Integrated security scanning as part of the code writing/generation/revision process would go a long way in pushing the boundary of what you can feel safe using these apps for.
