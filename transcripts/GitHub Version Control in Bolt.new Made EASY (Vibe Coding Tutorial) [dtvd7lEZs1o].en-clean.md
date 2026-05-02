# GitHub Version Control in Bolt.new Made EASY

## Introduction

Hey there, Bolters. In this tutorial, we're going to cover version control, how to do this within **Bolt** and also use **GitHub**.

## Version Control Within Bolt

Let's start off with version control within **Bolt**. So, you'll notice every time the Bolt agent finishes a command, it explains what it's done in a short little sentence and it adds a bookmark icon next to it. So, if you want to, you can save this option just by enabling the bookmark.

We can then come up to the name at the top, open up **version history**, and here we can see every single change that's been made by the Bolt agent. We've got the option to rename it. So let's say you get to a working point of your app. You could be stoked and say "working." Great. [clears throat] So we'll save that, or we could give it the name of the feature that you've just implemented.

Also notice that we can expand the bookmark versions and see every single bookmark that you've saved here. If you can get into the habit of using version history as you're building your project, I promise you it'll be worth it at some point in time. Also, **bookmarking** your features as you finish building them and then clearing the context is a great habit to get into.

## Why GitHub?

Now, it's time for **GitHub**. And it may seem a little intimidating for you non-developers out there, but there are some key benefits. Firstly, **branching**. Then, you can see the **diff** or the difference in your codebase. And thirdly, it's great for **collaboration**.

## Getting Started with GitHub

To get started, you'll need a **GitHub** account. So, just go to github.com and it's free to create an account. Once you've done that, jump back over into Bolt and we're going to go into the top right and click this little **GitHub** icon. We're going to log... and because we're logged in in another window, it seamlessly connects them just like that.

Now, it's asking us to create a **repository**. A **repository** is your entire codebase for one project. So let's give this the name "community app." Oh, you can't do a space. That's right. Great. So just like that, we've created the **repository**. And if we go back into **GitHub**, I'll look at my repos — that's another short word for them. And you can see "community app," what we just created, has appeared here updated now. So that's the first step.

## Branches

So the first thing we'll cover is **branches**. Now, **branches** is basically creating another version of your existing codebase where you can make changes to that, and then you can **merge** those changes back into the original codebase. So if something went wrong, then you can always delete the **branch**, or you can **branch** off the main again, and you don't need to worry about causing any issues with the existing production **branch**.

So super easy to do. Let's go back up to the **GitHub** logo and we're going to come down here, create a new **branch**. We're going to call this "front end." Now, after we've created it, let's see, we're now working on this **front-end branch**, and we're no longer on the **main branch**. If we want to switch back to the **main branch**, which is the default name for when your first **branch** is created with your repo, you can just hit switch like so. Now, let's switch back. And now we're on the **front-end branch** again.

## Building a Feature on a Branch

Now, let's build a new feature, and we're going to **merge** this into the **main branch** from before. I've noticed that dark mode does not work when I'm submitting a project. Full stop. Please update the project submission page to work in dark mode.

Let's jump over into **GitHub**. While that's working, if we open the community app again, you'll now see it's got two **branches**. It's got the **main branch** and then also the **front-end branch**, which we just created. It will show when they've been updated and if they're behind [clears throat] or ahead.

Now, watch this number here. So, that prompt just finished. Let's check it out. Great. It looks like it's mainly worked. I'll touch those up later. And now, every time **Bolt** finishes one of the prompts, it counts as a **commit** to the **branch**, which is basically saving your progress along the way.

## Pull Requests and Merging

Cool. So, what if we jump back into our **GitHub**? Let's refresh the page. Now we can see that our **front-end branch** is ahead of the **main branch** by one **commit**. What if we want to **merge** these changes into the **main branch**? We're happy with them. We like them. We're ready to go production with them. That's where we do something called a **pull request**.

Let's come into **front-end branch** and it's saying "front-end branch has recent pushes. Compare and do a pull request." We're going to say "added dark mode." Often good to get in a habit to write what the descriptions are. And then we're going to say "create pull request." And this is basically a proposal. It's saying that, hey, these are the changes that I've made and I want to push these changes into main. I want the main project **branch** to **pull** these changes into that **branch**.

Now, it's going to do a bit of a check. It says "no conflicts with the base branch." And that's when we hit "**merge pull request**." Confirm merge. It says the **pull request** was successfully merged and closed. You can delete the **branch** if you don't need it anymore.

But let's jump back into Bolt. Now what I'm going to do is, let's jump back over to the **main branch** and we'll see if that change has come across. And there we go. Dark mode. Your very first **PR**.

## Understanding Diffs

Now, let's understand a little bit about **diffs**. So, let's come back into — we're in the **front-end branch**. We're going to fix this little issue here. Notice I'll use a screenshot this time. We can just drop the screenshot directly into the chat. Look at the screenshot. You'll notice that this hasn't responded to dark mode. Please fix this for me.

So, **Bolt's** done a great job of implementing dark mode on this component here. Let's come back into our **branches**. We can see that our **front-end branch** is now one **commit** ahead. So let's open up the **front-end branch**. Now, not all the time do we have that **PR** component at the top. So we can come in here. This **branch** is one **commit** ahead. Click on this. And by doing so, it'll show us the **diff** or the difference in the code.

And if we look at it using a **unified view**, all the red shows the code that's been removed and all the blue shows the code that's been added. So you can see, if you can understand a little bit of **Tailwind**, that we've added this code here. We're making the text gray 300. Now if we want to change to a **split view**, we can see the code before and the code after.

## Tracking File Changes

Now another thing to pay attention to is you can see which files have been changed. So notice that it'll say "updated image upload TypeScript." So I assume that image upload is a component that was created and it's just changing that one file, which we can see here — one file changed. And now this is kind of a good way to debug. You can look back through your **pull requests** and you can see all the files that have been changed at certain times. So if by chance you introduce a bug, you're then able to basically go back through all of your **pull requests** and you could look through the code and see where it's been introduced.

## AI Code Review Tools

Another thing that's becoming popular are tools like **CodeRabbit**, where you can basically install them into your **GitHub** or connect them, and it is basically another set of AI eyes that will look over all of these code changes and will basically identify, "oh no, there's been a problem that it's changed this file when it shouldn't have." And if you're really going production-level code, that's maybe something that's worth considering.

## Collaboration with GitHub

So, the final thing I want to show you is how to collaborate using **GitHub**. Now, this can be super powerful. Say there's something that's a little bit too technical for you and you're really struggling. There's a fantastic world of freelancers out there. So, you can create a **branch** of your project. You can then share that **branch** with maybe a remote developer working somewhere else, pay them to make the changes that you want, and then you can **pull** those changes back into your **main branch**.

So to do that, we just jump into the settings of your **GitHub repository**, come into **collaborators**, and just like this, you can add someone using [snorts] their **GitHub** username or email.

## Conclusion

And there we have it, folks. There's an overview of how to use **version control** within **Bolt**, but then also take it to the next level — industry standard of using **GitHub** to make sure that your projects stay secure and you can collaborate.

I promise you, it may feel like it's a little bit extra work, but if something does go drastically wrong, it's incredible to come back and resort to a recently saved version. With that, good luck building and I'm excited.
