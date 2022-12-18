# About animations
### LoveHue supports animations using `.lhad` files. Here you will learn more about them, and how to create them yourself.

## What is a `.lhad` file?
A `.lhad` file is a file with the `lhad` file extension, and it stands for LoveHue Animation Dictionary. It's written like a JSON file, but we chose for a different file extension so LoveHue knows exactly what animations there are in a directory only by looking at a file's name.

## How do you make an animation?
You can make one pretty easily, and it has a bunch of different features. Let's make a simple, short one to demonstrate this.

### Example I: The Traffic Light

First, we need to know what we want the animation to look like. Let's say we want to simulate a simple traffic light, so we will need three different colors, and just because we can, we are going to have three different brightnesses.

Our `.lhad` file requires a name first, so let's give it one!
```json
{
	"name": "Traffic Light"
}
```
You can give this any name, but some characters might not look as good as others.

Let's add our first color, red. We will use `#FF0000` for this tutorial. We can add our color by first adding a list named `colors` that will contain various dictionaries. Our first dictionary will contain three values, and **none of them are required**. We will use all three this time, a HEX value, a brightness and how long until the next color is set.

The hashtag in front of the color value is optional. The value for `time_until_next` is in seconds.

```json
{
	"name": "Traffic Light",
	"colors": [
		{
			"color": "#FF0000",
			"brightness": 75,
			"time_until_next": 5
		}
	]
}
```

Great! Now we have the most boring animation ever! All it does right now is set the color of the lamp(s) to red with 75% brightness. Then, it waits 5 seconds and then the animation is over. But, this does show how it works. Let's add our other two colors!

```json
{
	"name": "Traffic Light",
	"colors": [
		{
			"color": "#FF0000",
			"brightness": 75,
			"time_until_next": 5
		},
		{
			"color": "#FFFF00",
			"brightness": 50,
			"time_until_next": 3
		},
		{
			"color": "#00FF00",
			"brightness": 100,
			"time_until_next": 8
		}
	]
}
```

Now our traffic light will actually be like a traffic light! But let's discuss a few other examples first where LoveHue will have to fill in the blanks a bit more.

### Example II: The Bright Dance

This example demonstrates the use of leaving things out, and what would happen if you enter things incorrectly. This is the code:
```json
{
	"name": "The Bright Dance",
	"colors": [
		{
			"color": "63ADF2",
			"brightness": 100
		},
		{
			"brightness": 25
		},
		{
			"color": "##04D6D",
			"brightness": 75
		},
		{
			"brightness": 25
		}
	]
}
```

Maybe you can already see what would is going to happen here, but let's analyze it all, line by line.

```json
{
	"name": "The Bright Dance",
	"colors": [
		// ...
	]
}
```
First, we begin by giving it a name and by opening our `colors` list. This is all normal, and if this isn't included, LoveHue won't even bother running the animation.

Let's analyze it all some more:

```json
{
	// ...
	"colors": [
		{
			"color": "63ADF2",
			"brightness": 100
		},
		// ...
	]
}
```
So, we've added our first color! But, unlike all the previous examples, the `color` value does not include a hashtag! Luckily, that doesn't matter to LoveHue! Then, we set the `brightness` value, but this is still like normal.
What is unusual, is that it does not set a value for `time_until_next`. That's because we don't need to change it per se, as it defaults to five seconds.

Let's go to our second color!
```json
{
	// ...
	"colors": [
		// ...
		{
			"brightness": 25
		},
		// ...
	]
}
```

As you can see, it does not specify a color value. Which is totally fine, as it tells LoveHue, "hey, continue with the last value you know". This could either be user set, or in this case, set by the animation just before that. Let's continue to our third value!

```json
{
	// ..
	"colors": [
		// ...
		{
			"color": "##04D6D",
			"brightness": 75
		},
		// ...
	]
}
```

This time we are once again trying to set a color, but what's that? A typo? Oh no! Well, luckily LoveHue doesn't care. LoveHue isgnores all hashtags for the `color` values, so it does not matter if there are zero, one, or 10 000, it will not error out because of a hashtag!

Let's proceed to the last color value.

```json
{
	// ...
	"colors": [
		// ...
		{
			"brightness": 25
		}
	]
}
```

As set previously, if no color is specified, it will continue with the last known value. And in this case, it was specified in the last step.

This marks the end of the tutorial. We've covered how to do some simple things by specifiying every value, and how we can just simply remove values and it will still work!

If you'd like to look at some other `.lhad` files, you can find some more in the `Animations` directory!
