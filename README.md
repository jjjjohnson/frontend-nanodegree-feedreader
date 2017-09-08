# Project Overview

Testing is an important part of the development process and many organizations practice a standard known as "test-driven development" or TDD. This project utilize Jasmine to do varuous tests. we required to complete the application with an incomplete test suite. 

## Get started
```
git clone https://github.com/jjjjohnson/frontend-nanodegree-arcade-game
cd frontend-nanodegree-arcade-game
```
Double click the index.html.

## Tests implemented

### Tests about RSS feeds definitions
- It tests to make sure that the allFeeds variable has been defined and that it is not empty.(line 24-37, [feedreader.js](jasmine/spec/feedreader.js))
- It tests every object in `allFeeds` and ensures it has a URL definedand that the URL is not empty. (line 34-40, [feedreader.js](jasmine/spec/feedreader.js))
- It tests every object in `allFeeds` and ensures it has a name definedand that the name is not empty. (line 47-55, [feedreader.js](jasmine/spec/feedreader.js))

### Tests about the menu
- It tests that ensures the menu element is hidden by default. which implies the `body` has class `menu-hidden`. (line 66-68, [feedreader.js](jasmine/spec/feedreader.js))
- It test that when `.menu-icon-link` has click event will toggle the class `menu-hidden` in `body`.(line 74-80, [feedreader.js](jasmine/spec/feedreader.js))

### Tests about Initial Entries
- It tests that loadFeed function is called and completes its work, there is at least a single .entry element within the .feed container(line 92-99, [feedreader.js](jasmine/spec/feedreader.js)). Since `loadFeed()` is asynchronous, Jasmine's `beforeEach` and asynchronous `done()` function is used to make sure the function finished.

### Tests about New Feed Selection
- The test ensures when a new feed is loaded by the loadFeed function that the content actually changes.(line 108-131, [feedreader.js](jasmine/spec/feedreader.js)). variable `oldContent, newContent` are introduced to store the old and new content of `feed`. It tests to make sure the texts are not the same at the two functioncalls.

```
beforeEach(function(done) {
            // Get the content for loadFeed(0)
            loadFeed(0, function() {
                oldContent = $('.feed').text();
                // console.log(oldContent);
                // Get the content for loadFeed(1)
                loadFeed(1, function() {
                    newContent = $('.feed').text();
                    // console.log(newContent);
                    // All feeds received, call done() 
                    done();
                });
            });
        });
```