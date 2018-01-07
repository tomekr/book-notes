# Don't Make Me Think Notes

## Things to look up

1. Is there an UX/analytics style gem for Rails applications?
	* Track the number of times a specific link on a specific page is clicked. This *should* give you an idea of how important it is so that you can emphasize it (either by making it bigger, more central, etc.)
2. 

## Chapter 1: Don't Make Me Think

> I should be able to "get it"-what it is and how to use it- without expending any effort thinking about it.

Maybe from the home page we should have a "Getting Started" link. From here we have a step by step tutorial for getting tracks into the site.

* Create an account
* Download the plugin here
* Install it like so...
* Enter your API Key
* Follow the steps here

For our initial user tutorial, have a link to a "sample project" the user can download and open to follow along with the rest of the tutorial.

* Please lets make the tutorial as short and succint as possible

Homepage should have a clear and concise message that shows what Stem does

> Another needless source of question marks over people's heads is links and buttons that aren't obviouslly clickable

* For our dashboard page, should we change to having a dedicated "Go to project" button instead of having the text in the table row clickable?

Eliminate question marks

> The appearance of things (like size, color, and layout), their well chosen names, and small amounts of carefully crafted text should all work together to create a sense of nearly efortless understanding.

* Add a three step indicator to the plugin for how far along the track upload progress the user is:

[O --- O --- check] where circles get filled in with our Stem green

> If you can't make something self evident, make it self-explanatory

* In other words if they can't figure it out instantly then they should be able to quickly figure it out with the help of the above qualities

## Chapter 2: How we really use the web

### Three facts of real world web use

#### Fact of life #1: We don't read pages, we scan them.

* We're usually on a mission
* We know we don't *need* to read everything
* We're good at it (think about how much you scan Reddit)

> What we see when we look at a page depends on what we have in mind, and usually it's only a fraction of what's there.

* What is going to be on our user's mind when:
  * They're coming to our site (as a new user)
  * They're coming to our site (as an existing user)
  * They're coming to our plugin from the DAW

#### Fact of life #2: We don't make optimal choices. We satisfice.

Most of the time we don't choose the best option, we choose the __first reasonable option__, a strategy known as __satisficing__.

#### Fact of life #3: We don't figure out how things work. We muddle through.

> For most of us, it doesn't matter to us whether we understand how things work, as long as we can use them. It's not for lack of intelligence, but for lack of caring. It's just not important to us.

## Chapter 3: Billboard Design 101

There are some important things you can do to make sure they see and understand as much of what they need to know - and of what you want them to know - as possible:

* Take advantage of conventions
* Create effective visual hierarchies
* Break pages up into clearly defined areas
* Make it obvious what's clickable
* Eliminate distractions
* Format content to support scanning

### Create effective visual hierarchies

1. The more important something is, the more prominent it is.
2. Things that are related logically are related visually.
3. Things are "nested" visually to show what's part of what.
  * Every newspaper page uses prominence, grouping, and nesting to give us useful information about the contents of the page before we read a word.

### Format text to support scanning

Important things you can do to make your pages scan-friendly

* Use plenty of headings
* Keep paragraphs short
* Use bulleted lists
* Highlight key terms


## Chapter 4: Animal, Vegetable, or Mineral?

> In general, I think it's safe to say that users don't mind a lot of clicks as long as each click is painless and they have continued confidence that they're on the right track. - following what's often called the "scent of information." Links that clearly and unambiguously identify their garget give off a strong scent that assures users that clicking them will bring them nearer to their "prey." Ambiguous or poorly worded links do not.

## Chapter 5: Omit needless words

> Rule #17. Omit needless words.
> Vigorous writing is concise. A sentence should contain no unecessary words, a paragraph no unnecessary sentences, for the same reason that a drawing should have no unnecessary lines and a machine no unnecessary parts.
- E.B. White, The Elements of Style

## Chapter 6: Street signs and breadcrumbs

> One of the most crucial items in the persistent navigation is a button or link that takes me to the site's Home page. Having a Home button in sight at all times offers reassurancce that no matter how lost I may get, I can always start over, like pressing a Reset button or using a "Get out of Jail Free". card.

* Should the clicking of the home button when authenticated be tracked and analyzed? This could indicate a user is getting lost.

## Chapter 7: The Big Bang Theory of Web Design

As quickly and clearly as possible, the Home page needs to answer the four questions I have in my head when I enter a new site for the first time:

1. What is this?
2. What can I do here?
3. What do they have here?
4. Why should I be here - and not somewhere else?


## Chapter 8: The Farmer and the Cowman Should be Friends

If you can, avoid long discussions/meetings about UX and instead do USABILITY TESTING. Make a crude version or two and test them on users to see how well they work.

## Chapter 9: Usability testing on 10 cents a day

Keep testing simple - so you do enough of it

**FOCUS GROUPS ARE NOT USABILITY TESTS**

What's the difference?

* In a **focus group**, a small group of people (usually 5 to 10) sit around a table and talk about things, like their opinions about products, their past experience with them, or their reactions to new concepts. Focus groups are good for quickly getting a sampling of users' feelings and opinions about things.
* **Usability tests** are about watching one person at a time try to use something (whether it's a Web site, a prototype, or some sketches of a new design) to do typical tasks so you can detect and fix the things that confuse or frustrate them.

Main things about usability tests:

* If you want a great site, you've got to test
* Testing one user is 100 percent better than testing none
* Testing one user early in the project is better than testing 50 near the end

DIY Testing

1. Time spent for each round of testing
	* One morning a month includes testing, debriefing, and deciding what to fix
2. When do you test?
	* Continually, throughout the development process
3. Number of rounds of testing
	* Once every month
4. Number of participants in each round
	* Three
5. How do you choose the participants?
	* Recruit loosely, if necessary. Doing frequent testing is more important than testing "actual" users
6. Where do you test?
	* On-site, with observers in a conference room using screen sharing software to watch
7. Who watches?
	* Half day of on-site testing means more people can see the tests "live"
8. Reporting
	* A 1-2 page email summarizes decisions made during the team's debriefing
9. Who identifies the problems?
	* The entire development team and any interested stakeholders meet over lunch the same day to compare notes and decide what to fix
10. Primary Purpose
	* Identify the most serious problems and commit to fixing them before the next round of testing
11. Out-of-pocket costs
	* A few hundred dollars or less per round

Why some of your participants should include people who aren't in your target audience:

* It's usually not a good idea to design a site so that only your target audience can use it
* We're all beginners under the skin
* Experts are rarely insulted by something that is clear enough for beginners

Average one-hour test session stipend is $50-$100 for "average" Web users

### Facilitators

* Keep the participants comfortable and focused on doing the tasks
* Main job is to encourage them to think out loud as much as possible


### Possible Stem Tasks

* You have an existing account with the email `oontz@example.com` and the password `correcthorsebatterystaple`.
	* Log in to the website and create a new project
	* Log in to the website, download the Stem plugin, and add it to a track in your DAW of choice
	* Find a project that looks interesting and request to join it
* You have an existing account with the email `oontz@example.com` and the password `correcthorsebatterystaple`. You're on the project, "Taylor Swift You Will Be Mine".
	* Create an [INSTRUMENT] track and upload it to the project

### Steps for the test:
1. Welcome (4 minutes)
2. The Questions (2 minutes)
3. The Home page tour (3 minutes)
4. The tasks (35 minutes)
5. Probing (5 minutes
6. Wrapping up (5 minutes)


#### The debriefing:

Main takeaway, **FOCUS RUTHLESSLY ON FIXING THE MOST SERIOUS PROBLEMS FIRST**

## Chapter 10: Mobile: It's not just a city in Alabama anymore

TKTK [TO READ LATER]

## Chapter 11: Usability as common courtesy

## Chapter 12: Accessibility and you

Four things you can do right now:

1. Fix the usability problems that confuse everyone
  * If something confuses most people who use your site, it's almost certain to confuse users who have accessibility issues.
2. Read an article
  * Mary Theofanos and Janic (Ginny) Redish watched 16 blind users using screen readers to do a number of tasks on a variety of sites and reported what they observed in an article titled "Guidelines for Accessible and Usable Web Sites: Observing Users Who Work with Screen Readers"
  * That article can be found [here](http://redish.net/images/stories/PDF/InteractionsPaperAuthorsVer.pdf).
3. Read a book
  * A Web for Everyone: Desigining Accessibe User Experiences
  * Web Accessibility: Web Standards and REgulatory Compliance
4. Go for the low-hanging fruit
  * Add appropriate alt text to ever image
  * Use headings correctly
  * Make your forms work with screen readers
  * Put a "Skip to Main Content" link at the beginning of each page
  * Make all content accessible by keyword (Remember, not everyone can use a mouse)
  * Create a significant contrast between your text and background
  * Use an accessible template

## Chapter 13: Guide for the perplexed



