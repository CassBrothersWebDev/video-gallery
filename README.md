# Video Showcase Webpage

## Overview

This webpage is designed to showcase a list of product videos provided by suppliers. The main features include a prominent main video display and a list of videos with thumbnails and titles. The JavaScript functionality allows users to click on a video in the list, which updates the main video display with the selected video.

## HTML Structure

### Main Video Container

The main video container includes an `iframe` element to embed the YouTube video, and an `h3` element to display the video title. The main-video-container class styles this section.

```HTML
<div class="main-video-container">
    <iframe
        src="https://www.youtube.com/embed/7Lrxk2g5TpE"
        allow="autoplay"
        frameborder="0"
        allowfullscreen
        loop
        controls
        class="main-video"
    ></iframe>
    <h3 class="main-vid-title">Are Velux Skylights Hail Proof?</h3>
</div>
```

### Video List Container

The video list container contains a series of video items (`div` elements) with thumbnails, embedded videos, and titles. Each video item is marked with the list class.

### Thumbnail

The thumbnail is represented by an `img` element with the list-thumbnail class.

```HTML
<div class="list-thumbnail">
    <img
        src="http://img.youtube.com/vi/7Lrxk2g5TpE/0.jpg"
        alt="Are Velux Skylights Hail Proof?"
    />
</div>
```

### Embedded Video

The embedded video is represented by an `iframe` element with the list-video class.
Title: The video title is displayed within an `h3` element with the list-title class.

```HTML
<iframe
src="https://www.youtube.com/embed/7Lrxk2g5TpE?autoplay=1"
class="list-video"
frameborder="0"
autoplay="1"
allowfullscreen
></iframe>
<h3 class="list-title">Are Velux Skylights Hail Proof?</h3>
```

## JavaScript Functionality

The JavaScript code enhances user interaction by allowing them to click on a video in the list. When a video is clicked:

```JavaScript
let videoList = document.querySelectorAll(".video-list-container .list");

videoList.forEach((vid) => {
  console.log("vid", vid);
  vid.onclick = () => {
    videoList.forEach((remove) => {
      remove.classList.remove("active");
    });
    vid.classList.add("active");
    let src = vid.querySelector(".list-video").src;
    let title = vid.querySelector(".list-title").innerHTML;
    document.querySelector(".main-video").src = src;
    document.querySelector(".main-vid-title").innerHTML = title;
  };
});
```

The script removes the "active" class from all video list items.
Adds the "active" class to the clicked video list item.
Retrieves the video source and title from the clicked item.
Updates the main video's source and title with the selected video.
This interactive feature provides a seamless way for users to explore different videos in the list.

Feel free to reach out if you have any questions or need further assistance!
