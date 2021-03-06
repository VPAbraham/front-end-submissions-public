# Whateverly
* Students: Karin Ohman, Tiffany Bachmann, and Adam Niedzwiecki
* Evaluator: Brittany, Pam, and Robbie

# Rubric

## Specification Adherence

* [ ] Novice - README is missing or incomplete. Codebase is not organized. User stories from group are never submitted. Application does not solve the presented problem.

* [ ] Advanced Beginner - README is complete. Codebase is organized. User stories are completed; however, may be late. Some user stories may be unclear or hard to understand. Application is close to solving presented problem.

* [x] Proficient - Developers turn in user stories on time and iterate on user stories throughout the life of the project, as needed. User stories have enough detail - such that an outside developer could jump right in and help with user stories/tickets. Application solves the presented problem.

* [ ] Exceptional - Meets all expectations for `Proficient`. Developers may use personas to help guide their user stories. Developers may also incorporate other tools to assist in planning - workflow diagrams, story maps, etc.


Comments:

* Careful in your README when you say "Test Driven Development". By the looks of the commits, a lot of the component structure was built before any tests were written. You can certainly point out testing, but just don't call it TDD.
* Good job using the gif to show features

------------------------------------------------------------------

## UI/UX

* [ ] Novice - The application is confusing or difficult to use. The final project presents an interface that is incomplete.

* [ ] Advanced Beginner - The application may be confusing or difficult to use at times. The application shows effort in the interface, but the result is not effective because UX and/or UI still present an application that is incomplete or difficult to use. It is not clear that the user stories helped to guide UX.

* [x] Proficient - The application has many strong pages/interactions. The application can stand on its own to be used by instructor without guidance from a developer on the team.

* [ ] Exceptional - Meets all expectations for `Proficient`. In addition, the application is fully responsive, and has clearly had special consideration around usability on devices. There no holes in functionality.


Comments:

* Text on splash page is small and kind of long to get anyone's attention.
* Like the markers next to the buttons as a sort of legend.
* The parks list by state is nice, but how useful is it for users? I think somewhat useful for general perusing. A user might be more interested in how far away a park is from a certain point/city/location to see if it's feasible to travel to.
* The "more info" card under the state is not super useful. It might be interesting to some people, but it takes up a good amount of space for what it's giving to the user.
* The map marker tooltips are nice.



------------------------------------------------------------------

## CSS/Sass Style

* [ ] Novice - There are several (10+) instances of duplication and one or two major bugs. Developers write code with unnecessary selectors or tags which do not increase clarity.

* [ ] Advanced Beginner - There is some duplication (5-10 instances) in the codebase. There may be one to two minor bugs. There may be some unnecessary selectors or tags. Application adds organization for the whole stylesheet and within rules.

* [ ] Proficient - Application is thoughtfully put together with comments to help guide organization. There may be some duplication (fewer than 5 instances) present. Comments are present to assist with organization of code.

* [ ] Exceptional - Meets all expectations for `Proficient`. The application has exceptionally well-factored CSS/Sass with all styles separated out into logical stylesheets. There are zero instances where an instructor would recommend taking a different approach.


Comments:










------------------------------------------------------------------

## JavaScript / React Style

* [ ] Novice - There is a significant amount of duplication and one or two major bugs. JavaScript does not follow the principles of `DRY` (Don't Repeat Yourself)

* [ ] Advanced Beginner - There is some duplication and there may be one or two major bugs. The application has large components and logic could be broken apart into smaller, stateless components. JavaScript may be hard to read/follow.

* [x] Proficient - Application has little to no duplication and no major bugs. Application has several components built out that logically break apart the functionality. JavaScript may be hard to follow at times but is generally easy to read/understand. 

* [ ] Exceptional - Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There are zero instances where an instructor would recommend taking a different approach to design and component architecture. DRY and SRP (Single Responsibility Principle) practices are incorporated, making JavaScript very easy to follow/read.


Comments:

* Lots of [h3s](https://github.com/kaohman/national-parks/blob/master/src/UsState.js#L7-L12) here. This would be really rough for a user on a screen reader to differentiate what's important here. Also, just because you're breaking your code out into components, doesn't mean everything deserves an h1. The h1 & h2 should pretty much be reserved for your overall app title and subheading. Remember all these components come together to create one cohesive page, and if there are h1's all over the place it's hard to tell what's important.

* Really nice tiny methods [here](https://github.com/kaohman/national-parks/blob/master/src/ParkMap.js#L17-L31)

* The render method [here](https://github.com/kaohman/national-parks/blob/master/src/ParkMap.js#L33) is a little intense. Could you move these icon variables out somewhere into a separate method? The only thing that's changing about each of them is the color. Could you loop through an array of those colors and generate each icon within the loop to reduce some of this duplicate code? We also have a lot going on within this [map](https://github.com/kaohman/national-parks/blob/master/src/ParkMap.js#L81-L103), where again, it seems like all that's changing is the color of the icon. I'd refactor to something like this:

```
let icon = this.determineIconColor(park) // this method would do some of that conditional logic and return either the green, violet, or blue icon

return <Marker position={[lat, lon]} icon={icon} onClick={this.getPark} key={park.urlCode} id={park.urlCode}>
  <Tooltip>{park.parkName}</Tooltip>
</Marker>
```

* I'd say overall your render methods are a little gnarly and need some cutting down. You can always create methods on your components that simply return a chunk of JSX to slim down what's actually happening in `render`.


* [This method](https://github.com/kaohman/national-parks/blob/master/src/FilterControls.js#L21-L23) is redundant. You can just directly invoke `this.props.setMapToState()` instead of wrapping it in another method to call it




------------------------------------------------------------------

## GitHub Collaboration/Workflow

* [ ] Novice - Developers do not tag instructors in the two required PRs by due dates listed in the project outline or tagged PR has fewer than 200 lines of code. The developer creating the PR does not summarize the changes or why the changes were made. Reviewers are not leaving line-by-line feedback/comments _or_ are merging the PR before changes are made.

* [x] Advanced Beginner - Developers tag instructors in both required PRs by due dates _or_ in one of the two required. PR has less than the required lines of code in PR. Reviewers do not leave line-by-line feedback. May be merging PR before feedback is incorporated.

* [ ] Proficient - Developers tag instructors in both required PRs by due dates. PR is between 350 - 450 lines of code. The developer creating the PR summarizes the changes made, why those changes were necessary, and asks for insights. Reviewers leave line-by-line comments/feedback and wait to merge PR until feedback is incorporated.

* [ ] Exceptional - Meets all expectations for `Proficient`. The feedback is both kind _and_ insightful. There may be numerous threads of conversation where developers go back and forth to find the best solution to the problems they are solving together.


Comments:

Contribution breakdown:  
Karin: 42 commits  
Tiffany: 25 commits  
Adam: 4 commits  

- This is a pretty significant disparity in contributions in a 3 person project. From the PRs, it looks like a portion of this might be due to portions of code being written/reviewed together; however, even if that is the case - group members should still be switching who the driver of the project is when pairing/reviewing in person. 
- A good number of feedback/comments on each of the PRs. However, there is still a lot of one-sided conversation happening and questions from PR creators that go unanswered by reviewers. Also a significant amount of comments that are simply thanking the person for adding/updating a feature with the reviewer restating (in their own words) the changes that were made.
- Tagged instructors 12/20 (2 days late) and 12/24. First was over 700 (which includes 500 lines to updates on package-lock.json file) while second was just over 900 lines.

------------------------------------------------------------------

## Testing

* [ ] Novice - There is little or no evidence of testing in the application.

* [ ] Advanced Beginner - Project has sporadic use of tests at multiple levels. The application contains numerous holes in testing and/or many features are untested.

* [ ] Proficient - Project has a running test suite that tests multiple levels but fails to cover some features.

* [X] Exceptional - Project has a running test suite that exercises the application used Enzyme. The test suite covers almost all aspects of the application.


Comments:


* Testing looks good with most things covered and high-quality tests. 
* Great job consistently testing for default state, and updates to state. App testing coverage looks good!
* Make sure to test for conditional logic in methods (and all possible outcomes based on logic) like in testing for method `saveNewParksArray` in `Button`
* Additional assertions could be added to make sure that mock functions are being called a set number of times when a method is invoked.

------------------------------------------------------------------

## Presentation

* [ ] Novice - Not all presenters speak. Presenters give too much or too little information about the application. Presenters do not use audio/visual aids or media.

* [ ] Advanced Beginner - Everyone in the group speaks. Presenters do a live demo of the application. The group may speak about the planning/challenges/rewards of the project; however, the delivery does not seem thought out/well-planned. 

* [ ] Proficient - Everyone in the group has an opportunity to speak during the presentation. The group has a visual of the application to demo (e.g. slides, recordings of interactions, live demo). The group talks about the app, speaking to the challenges, rewards, and collaborative aspects of the project.

* [x] Exceptional - Meets all expectations of `Proficient`. In addition, the presentation runs smoothly w/no hiccups - indicating that it was planned/rehearsed/polished. The presentation is so engaging that there is no time that the evaluators find themselves checking the time/clock.


Comments:

- LOVE the added touch of the national park shirts - fun yet professional 
- Nice hand gesturing while presenting!!! Your charisma is 👌
- No need to mention the tech stack based on your audience - though mentioning leaflet is important
- Love the fact that you created personas and that you incorporated and talked about your users as part of your presentation
- Great job talking and describing the way that the app works as the recorded demo plays. Yay for not doing a live demo!
- Slides - good bullet points, easy to scan, not too little or too much information
- Nice job whiteboarding the different components - though it would likely be a bit easier to add this as a slide and use that as a visual aide during the demo. Gives you the extra security of creating less room for possible errors/mistakes