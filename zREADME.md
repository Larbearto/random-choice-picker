1. grab all the elements with the id of 'tags'
2. grab all the elements with the id of 'textarea'
3. Automatically focus on the textarea when page is loaded. textarea.focus()
4. add event listener for the textarea 'keyup' event which is when you press down which will then create tags for
5. create a function for createTags(input)
6. when i type in and input a comma, i want to split that comma and create an array of whatever is on either side of these comments. Each will be its own value.

All right.

So in this video, we want to create our tags.

We want to be able to type in here and split by a comma and create tags below.

So one thing I want to do in the CSS, though, is on the H three.

I'm just going to add a text, a line of center just to center that I think that looks a little better.

And then in our script file, we want to get the tags element, which is this right here, this div

with the ID of tags.

So let's call this tags L and set that to document dot get element by DX and we want the ID of tags.

And then I also want the text area.

So we have an ID of text area and let's call this text area.

And those are the only two things we want to bring in.

So then I want to automatically focus on the text area.

So we're going to call the focus method, which if we go to the page, it'll automatically put the cursor

in there and we can start typing.

Now we want an event listener on the text area, so add event listener and we want to listen for a key

up.

So you have key down and key up.

We're listening.

When, when you press down and then you let go, that's going to fire this off.

And when that happens, it's pass in our event parameter here.

When that happens, we're going to call a function called create tags and we want to pass in dot target

dot value, which is going to be whatever we type in.

So if we create a function called create tags, say input, and we console.log the input.

If we go down here and we open up our console and I start to type, you should see what we type down

here.

All right.

Now, the way we're going to do this is we want to take whatever, whatever we type in, and then we

put a comma.

We want to split at that comma and create an array of whatever is on either side of these comments.

So this would create an array with this as the first value.

This is the second we can do that using split.

So let's say const tags and let's set that to input, which is a string.

We want to split it by the comma and turn it into an array.

So now if I console.log here tags and I go and I say let's just put a one in here.

Whoops, what happens?

Spit is not a function.

So split if I put a one, you can see we have an array with one value of one, which is a string.

If I put a two, it's going to just be an array with a 12.

But if I put a comma and then a two, then we have an array with two values, one and two, so it's

going to split it by the comma.

Now I don't want to be able to have space like that.

So what we'll do is add on to this dot filter and filter is also a high odor array method that allows

you to return certain things based on a conditional.

So we'll say for each tag, let's say tag dot trim, which will just trim off any white space.

If that is not equal to an empty string, then we'll return that.

And then we just want a map which will just manipulate the array.

So for each tag we want to return an array with the tag, but we want to trim.

So we're just saying it can't be an empty string.

Also, we're going to trim any white space.

So now if I save that and I do one space, you can see that it's not actually added the spaces in there.

And I could put comma to space and the space is not added in there.

And if I just do like comma and then another comma, it doesn't add another it doesn't do anything because

of our filter.

All right.

So now that we've established that, let's get these tags put into our HTML.

So we'll get rid of that and let's take the tags element and clear it.

Otherwise, they're just going to pile up.

So before we do anything, we'll just clear that and then we'll take our tags, which is an array and

we want to loop through loops with for each, for each.

So for each tag let's create a tag element with document, dot create element and we want to create

a span.

We also want to add a class to that.

So let's take the tag element and let's class list, dot add.

The class of tag and then we want to set the the inner text of that.

So we'll take the tag element and set the inner text to whatever the tag is because we're looping through

it here.

We get each one and we're going to put that as the inner text.

And then finally we want to take the tags element.

So make sure you have the SE here.

This is the, the ID of the div with the ID of tags and we want to append child and we're going to add

each of those tag elements in.

So if I go ahead and I do.

Hello.

So it starts to type down there as a tag.

If I do a comma and I put in world, that's going to be the second tag.

So it's going to separate it by the commas.

All right.

So we have the ability to create these tags.

What we want to do next is have the ability to hit enter and then have it randomly select and it's going

to highlight and it'll give that cool little animation as well.

So we'll do that in the next video.
Okay.

So we're able to create our tags here with commas.

Now we want the random select functionality.

So in our event listener, let's check to see if we hit Enter.

So we'll say if.

And then on this event object, we have a key property and we're going to say if the key is equal to

enter.

All right.

Now, if we hit enter, we're going to call a function called Random Select, which you haven't created

yet.

I also want to clear the input.

So we're actually just going to wait a couple of milliseconds before we do that.

So in the set timeout we'll pass in an arrow function and we just want to wait ten milliseconds and

then clear the input value with e dot target dot value.

And we're just going to set that to nothing.

All right.

So let's create random select down here function, random select.

And for now we'll just console.log 1 to 3.

And if I open up my console and I can type stuff down here and then enter, then you see it fires off

that function.

And it also clears this up here.

Now, in the random select, we're going to go ahead and set a value of times and I'm going to set that

to 30.

And what this represents is the number of times it's going to highlight each one before it stops.

So we'll go one, two, three, four, and it'll go to 30 or whatever you put this to.

And then we're going to have we're going to have to set an interval because this is going to repeat

this highlight of each one, the highlight and the remove of highlight of each one.

So let's create a variable called interval and want to use the set interval function.

So for the for the time here, we want this to happen, let's say every 100 milliseconds.

And what we want to happen is we want to pick a random tag, so let's say random tag and set that to

a function called pick random tag.

And before we move on, we'll create that.

So let's say function pic, random tag, and we want to take all the tags so we can use document, dot,

query, select or all.

And we want to get all the elements with the class of tag, which will be all these, all of these,

all the spans.

And then to get a random one, let's return.

And we're going to return tags.

So tags when we use query select are all it's a node list that we bring in.

So all of these will be put into the node list, which is similar to an array with an index.

So the index is going to be random and we'll use math dot floor to round down math dot random, which

will give us a random decimal.

We just want to multiply that by the length of the tags array or not array, but node list which is

similar to an array.

So that will give us a random tag.

I'm also going to create two more functions down here just to highlight and highlight.

So we'll call this highlight tag and it's going to take in a specific tag element.

And then we're going to take that tag element and we're going to just add a class, add a class with

class list add and we're going to add the highlight class.

And then we want one to remove the highlight.

So we'll call this highlight tag and we're just going to remove instead of ADD.

Like that.

So now back up to here.

So we have this interval that's going to fire off every 100 milliseconds.

It's going to pick a random tag.

And then we want to highlight that random tag.

So highlight tag pass in our random tag and then we want to highlight.

So I'm going to have a set time out here which is going to take in a function and we're just going to

wait 100 milliseconds here to highlight.

So in here we'll say highlight tag and want to pass in our random tag.

So with this, if I were to create my tags and then hit enter, you can see what's happening every 100

milliseconds.

It's highlights picking a random tag to start at and then it's highlighting a random tag and then 100

milliseconds after it's highlighting.

So that's just going to keep going forever right now.

All right.

So I'm just going to reload to stop that.

And now what we can do is go under.

Let's see.

So function.

We still want to be within our random select, but we want to go down here.

And I'm going to have a set timeout.

With a function and I want this to run after whatever the times is.

I want to multiply that by 100 milliseconds.

So the 30 here, multiply that by whatever the time this is, which is 100 milliseconds.

Okay.

We could even put that.

We could put that in a separate variable if we wanted to.

But anyway, we want to clear our interval.

So you have an interval that runs.

There's a function called clear interval to stop it.

So we want to pass in our interval.

Then we want to pick a random tag to stop on.

So let's create let's do a set timeout.

And this is going to be 100 milliseconds and inside this set.

Timeout, I want to get a random tag.

So once again, we'll create a random tag and set that to pick random tag and then we want to highlight

it.

So let's say highlight tag and pass in our random tag.

So this up here is is causing that, you know, shifting it to each one, highlighting and highlighting

after a certain amount of time.

And then this takes care of stopping it and just picking a random tag to land on and highlight.

Hopefully that makes sense.

So let's do one, two, three, four, five.

These can be numbers or strings or whatever you want to put in here.

Let's do up to ten and then I'm going to hit enter.

So it should run 30 times and then it's going to stop on a random tag or in this case number.

But of course it can be anything.

And let's try that again.

Same thing which we did one through ten and hit enter.

So it landed on three last time.

Now it lands on one.

All right.

So you have choice one, choice two, choice three and enter.

And it's just a cool little application to pick a random choice.

All right, so that's it.
