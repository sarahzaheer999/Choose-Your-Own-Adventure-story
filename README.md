# Choose-Your-Own-Adventure-story

## https://codesandbox.io/s/sparkling-star-vvn45?file=/src/App.js


```
import React, { Component } from "react";

import "./styles.css";

var pages = {
  start: {
    text: "Welcome, this is your reminder app. Sarah's bday is in London, how would you like to go there?",
    leftLabel: "Train",
    rightLabel: "Ship",
    leftPage: "onthetrain",
    rightPage: "Ontheship",
    url:
      "https://s3-eu-west-1.amazonaws.com/work.ninjapixel.io/meetup-may-2017/london.jpg"
  },

  onthetrain: {
    text:
      "Welcome. It is going to take about 8 hours for you to reach your destination",
    leftLabel: "cool",
    rightLabel: "97C",
    leftPage: "Ontheship",
    rightPage: "life"
  },
  Ontheship: {
    text:
      "You are here! Yay, now let's select a dress for you. What'd you like to wear?",
    leftLabel: "dress",
    rightLabel: "97C",
    leftPage: "whattowear",
    rightPage: "life"
  },

  whattowear: {
    text:
      "this looks great, now what would you like to eat?",
    leftLabel: "pizza",
    rightLabel: "97C",
    leftPage: "eat",
    rightPage: "life"
  },

  eat: {
    text:
      "this looks great, where do you wanna go now?",
    leftLabel: "londoneye",
    rightLabel: "97C",
    leftPage: "londoneye",
    rightPage: "life"
  },


  londoneye: {
    text:
      "this looks great, where do you wanna go now?",
    leftLabel: "bday",
    rightLabel: "97C",
    leftPage: "bday",
    rightPage: "life"
  },

  bday: {
    text:
      "It is 8 pm. time for you to go to Sarah's bday. Are you ready?",
    leftLabel: "Hell yes",
    rightLabel: "97C",
    leftPage: "party",
    rightPage: "life"
  },

  party: {
    text:
      "Oh wait..... where is everyone?",
    leftLabel: "I don't know eh",
    rightLabel: "97C",
    leftPage: "wrongdate",
    rightPage: "life"
  },

  wrongdate: {
    text:
      "Seems like the party was 2 weeks back... oh no you forgot to update me",
    leftLabel: "oh no... Let's go back",
    rightLabel: "97C",
    leftPage: "letsgoback",
    rightPage: "life"
  },

  letsgoback: {
    text:
      "How would you like to go back?",
    leftLabel: "Train",
    rightLabel: "97C",
    leftPage: "Goingback",
    rightPage: "life"
  },

  Goingback: {
    text:
      "The train booked for 8 am shall take you back.",
    leftLabel: "oh okay...",
    rightLabel: "97C",
    leftPage: "start",
    rightPage: "life"
  },





};

class App extends Component {
  constructor(props) {
    super(props);

    this.state = {
      page: "start"
    };
  }

  goToPage(pageName) {
    this.setState({
      page: pageName
    });
  }

  render() {
    var pageData = pages[this.state.page];

    return (
      <div className="App">
        <p>{pageData.text}</p>
        <img src={pageData.url} width="200"  height="150"/>

        <button onClick={() => this.goToPage(pageData.leftPage)}>
          {pageData.leftLabel}
        </button>
      </div>
    );
  }
}

export default App;
```
