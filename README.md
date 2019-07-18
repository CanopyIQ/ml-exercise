# Journal ML Take Home exercise

In this exercise, you'll be creating a REST API service that serves an ML model
that you'll create to solve the following problem:

Based on the contents of a news article, we want to be able to predict if the
article was written in one of the following publications:

- NPR
- CNN
- Washington Post
- Reuters
- Guardian
- New York Times
- Atlantic
- Business Insider
- Vox
- Buzzfeed News
- Talking Points Memo

To assist with training a model to perform this, we are providing gold data in the
`train.csv` file included in this repository. The file has the following columns:

| column      | description                                                                |
|-------------|----------------------------------------------------------------------------|
| title       | The title of the article                                                   |
| publication | The name of the publication                                                |
| date        | The publication date in the following format "YYYY-MM-DD" (eg. 2016-12-06) |
| year        | The publication year                                                       |
| month       | The publication month                                                      |
| content     | The article body text                                                      |

The service you create should respond to the endpoint `/predict_publication`, 
where users can `POST` JSON data in the following form to get a prediction:

```json
{
  "title": "FILL WITH TITLE OF ARTICLE",
  "content": "FILL WITH CONTENT OF ARTICLE"
}
```

and expect a response in the form:

```json
{
  "publication": "FILL WITH PREDICTED PUBLICATION NAME"
}
```

An example request:

```json
{
  "title": "How To Teach A Sea Lion Who’s Fussy About Grammar",
  "content": "When it comes to sentence structure, Rocky, a sea lion, was a stickler. ”It really mattered to her, what’s going to be the direct and indirect object,” says Kathy Streeter, an animal trainer. For Sierra, it isn’t the grammar that interests her. It’s the vocalizations. This California sea lion loves experimenting with her vocal range, and she hates being interrupted. More than 1 million people visit the New England Aquarium in Boston each year. Before walking through the front door, they watch Atlantic harbor seals play. Inside, visitors watch sea lions cruise around the   pool. What these visitors may not know is that the aquarium’s 10 seals and two sea lions go to school each day Streeter is one of their teachers. Rushing between classes, Streeter can rattle off the disposition of each student.   Cayenne, a harbor seal, has a ”hard time totally, totally focusing.”   Sierra is smart and eager. She’s like: ”Come on! Let’s go! Let’s move fast! You’re taking too long.”   Zoe, a    sea lion, isn’t great at transitioning between tasks. With such different personalities, what’s the classroom dynamic like? ”They get along really, really well.” But Streeter rarely works with the whole student body. Instead, most of her lessons are taught   . Or, to put it in language that would sound familiar to just about any   teacher, she has an individualized learning plan for each of her students. With rubber boots and waterproof pants, Streeter starts her lesson with Chucky  —   short for Chacoda  —   by asking slowly and clearly, ”How are you?” In a rush of excitement, the harbor seal answers in a garbled voice, ”How are you. How are you!” ”Good boy! Bubbles?” she asks. Much to the delight of the tourists watching, Chucky dives underwater and starts blowing."
}
```

and the corresponding response:
```json
{
  "publication": "NPR"
}
```

## Expected results

## Model

Feel free to use any language of your choosing to train your model, and feel
to use any external libraries to help you solve this problem. We're more
interested in the following:

- how do you evaluate performance of your model/system
- get a working, baseline model with acceptable performance
- how/why did you choose the components of you prediction system
- what else would you try if you had more time

Please include a written document explaining the above.

### Service

Please package up your service with Docker to make it easier to run. This can
just be a Dockerfile included in your submission that would contain the service
when built. An example submission might include the following files:

```
Dockerfile
app.py: The service implementation
model.pkl: A binary file containing the prediction model
README.md: A document describing the solution
```

### Submission

Please don't spend more than 2-3 hours on this problem. As mentioned previously,
we're more interested in your ability to get a working solution to the problem
and your thought process around what can be tried next to potentially improve it.
