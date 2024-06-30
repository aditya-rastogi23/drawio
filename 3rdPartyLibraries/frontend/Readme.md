# Importing a third party library

## General guidelines for picking a library

* See recent commits
* See stars and companies using the same
* look at open issues and try to find out a resolution time for the same

## Implementation details

Any library you are trying to implement should be having 3 layers of abstraction
1. Library import code: this is an abstraction that the library itself provides by being a module easy to import
1. Library handler class: this allows you to expose only certain functions(which are imported as per necessity) to ensure that all your library functions are clearly visible in one place and easier to debug
1. Utility files: these will call the library handler directly and add a layer of abstraction that allows you to write your business logic/general functional manipulation that is required to ensure your end components are completely abstracted from any code that the library produces

## Reasons for each layer of abstraction

1. Makes the library easier to import and share
1. Makes it so that in case the library is needed to be replaced all logic can be found in one place to easily detach said library
1. This allows business logic to be away from both the library code and the end view component. Which means in case we have a specific change requested it can be made without affecting the library used or adding code in any unreachable place