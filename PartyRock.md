# Build Generative AI Applications with Amazon PartyRock

---
## Overview

PartyRock is a shareable Generative AI app building playground, that allows you to experiment with prompt engineering in a hands-on and fun way. In just a few clicks, you can build, share, and remix apps, to get inspired while playing with Generative AI. Here are a few examples:

- DormChef (jlooper): With just a few ingredients that happen to be in your dorm fridge, create a recipe so you don't go hungry tonight. With tofu, a pack of ketchup, and a can of diet coke, you can cook "Tofu and Ketchup Stir-Fry" for example.
- Resume Optimizer (graffot): Input the description of the job you're seeking, and this tool gives you suggestions to tweak your LinkedIn profile in a way to demonstrate your fit for the role.
- Prompt Engineering - Content Creation (js2222): learn how to write prompts for different Foundation Models (FMs) in Bedrock to generate content.

![0-partyrock.png](images%2F0-partyrock.png)

By building and playing with PartyRock apps, you learn about the fundamental techniques and capabilities needed to get started with Generative AI, including understanding how a foundation model responds to a given prompt, experimenting with different text-based prompts, and chaining prompts together.

## Create A PartyRock Account
Any builder  experiment with PartyRock needs to a profile using a social login from Amazon.com, Apple, or Google. **PartyRock is separate from the AWS console and does not require an AWS account to get started.**

1. To begin head over to the [PartyRock website](https://partyrock.aws/).
2. Login/register with a social login from Amazon.com, Apple, or Google

## Exercise 1: Build A Mood Mixer For Your Favorite Music

3. Click on `Build your own app` and enter the following prompt and click `Generate App`.

> Develop an app that curates personalized music playlists based on user moods, activities, or genres. Users can input preferences, and the AI generates customized playlists tailored to their tastes, enhancing music discovery and enjoyment within the media and entertainment space.

PartyRock was able to create the widgets needed to take `user moods`, `activities`, and `preferred genre` as inputs, and generate `Playlist` and other as outputs. populate the inputs will trigger the outputs to generate.

![1-app-bare.png](images%2F1-app-bare.png)

> **_NOTE:_** The widgets generate may not be the same every time.


4. You can resize each widget by click and drag the bottom right corner. You can also move the widgets on the canvas by click and drag the widget title.

## Modify widgets

There are 5 types of widgets, last 3 are AI-powered:

- User Input
- Static Text
- Text Generation - AI-powered
- Image Generation - AI-powered
- Chatbot - AI-powered


Everywhere you see this icon means it is editable.

![2-edit-icon.png](images%2F2-edit-icon.png)

5. for the 3 inputs, lets set the default values:

- Mood -> Cheerful
- Genre -> Hip pop
- Activities -> Gym

6. Edit the  AI-powered widgets. You can change the Widget title, Foundation Models (FMs), and the prompt.

> **_NOTE:_** Input widgets: Mood, Genre, Activities are referenced in the prompt to establish dependency relationship.
> You can expand the Advanced setting to adjust configuration parameters for FMs.

![3-edit-AI-widget.png](images%2F3-edit-AI-widget.png)

**Example**: we can change the prompt for Playlist widget above to display the songs in bullet list.

> Generate a personalized playlist of 10 songs ... Display in a bullet list.

![4-playlist-bullets.png](images%2F4-playlist-bullets.png)

## Add New Widget

If it is not already created, let's add a new widget that generate an introduction for our playlist.
7. Click on `+ Add widget`.
8. Choose `Text Generation` and input `Playlist introduction` as Title
9. Edit the widget with following info.

![5-Playlist-introduction.png](images%2F5-Playlist-introduction.png)

Next are going to create a new widget that generates a cover image for our playlist
7. Click on `+ Add widget`.
8. Choose `Image Generation` and input `Playlist Cover` as Title
9. Edit the widget with following info.

![6-Playlist-cover.png](images%2F6-Playlist-cover.png)

## Finishing Touch
Please take one more path to refine your titles, wording, and layout. In the end, you should have something like this.

![7-final-app.png](images%2F7-final-app.png)

Click `Share` at top-right to publish your application.

![8-publish.png](images%2F8-publish.png)

## Exercise 2: Playtime
You can now update the prompts, play with the settings, or just create your own app. Be creative and let's see what you can come up with!

## Final Thought
With PartyRock, you can quickly experiment with different ideas leverage the power of Generative AI. When you are ready for production, you can implement the ideas using Amazon Bedrock.



