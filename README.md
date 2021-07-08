
# Design system naming conventions in Modularization on Android (Based on my experience)

<img width="1323" alt="Screen Shot 2021-07-08 at 23 36 24" src="https://user-images.githubusercontent.com/5199109/124959842-d83a5980-e045-11eb-960d-ca39a2e36b04.png">


## 1. Project structure

We can implement different architectures in Modularization.
##### The structure of each module :

|Architecture|Reference|
|--|--|
| MVP | [Click to see sample MVP](https://github.com/MindorksOpenSource/android-mvp-architecture) |
| MVVM | [Click to see sample MVVM](https://github.com/MindorksOpenSource/android-mvvm-architecture) |
| RIBs | [Click to see sample RIBs](https://github.com/uber/RIBs) |
| ... | ...|


## 2. Naming convention

 - Name the classes based on the feature name.
 - Class names are written in [UpperCamelCase](https://en.wikipedia.org/wiki/Camel_case). 

### Resources: `<FEATURE>_<BRANCH>_<WHAT>_<DESCRIPTION>_<SIZE>` + Suffix ( xml)

### Files: `<FEATURE>_<BRANCH>_<DESCRIPTION>_<SIZE>_<WHAT> `+ Suffix ( files: .java, .kt )


#`<FEATURE>` the name of the core/big feature 
```
Example <FEATURE>: 
1. Feature Video/Audio Call -> <FEATURE> = Call
2. Feature Chat -> <FEATURE>  = Chat
```

#`<BRANCH>`  the name of the minor-feature when we have many small features in a big feature 
```
Example <FEATURE>_<BRANCH>:
3. Call feature has many small features: video, audio -> <FEATURE>_<BRANCH> = CallVideo and CallAudio
4. Chat feature has many small features: group, secret,direct -> <FEATURE>_<BRANCH> = ChatGroup or ChatDirect or ChatSecret.
```

#`<WHAT>` We should use Android component's name (Activity, Fragment, Dialog, etc )

```
Example <FEATURE>_<BRANCH>_<WHAT>:
1. Screens for Call feature ->  <FEATURE>_<BRANCH>_<WHAT>
	1. Activity: CallVideoActivity, CallAudioActivity.
	2. Fragment: CallVideoFragment, CallAudioFragment.
	3. TextView: CallVideoTextView, CallAudioTextView.
2. Screens for Chat feature -> <FEATURE>_<BRANCH>_<WHAT>
	1. Classes:
	 	1. Activity: ChatGroupActivity, ChatDirectActivity.
		2. Fragment: ChatGroupFragment, ChatDirectFragment.
		3. TextView: ChatGroupTextView, ChatDirectTextView.
	2. XMLs:
		1. activity: chat_group_activity, chat_direct_activity.
		2. fragment: chat_group_fragment, chat_direct_fragment.
		3. textview: chat_group_textview, chat_direct_textview.
```

#`<DESCRIPTION>` (Option)
  1. Resources: ```<FEATURE>_<BRANCH>_<WHAT>_<DESCRIPTION>``` Differentiate multiple elements in one screen. 
  2. Files: `<FEATURE>_<BRANCH>_<DESCRIPTION>_<WHAT>` information clarifies the responsibility of the file.
			

```
Example:
4. Classes ->  <FEATURE>_<BRANCH>_<DESCRIPTION>_<WHAT>
	1. Activity: CallVideoLandscapeActivity, CallAudioPortraitActivity.
	2. Fragment: CallVideoLandscapeFragment, CallAudioPortraitFragment.
	3. TextView: CallVideoFullScreenTextView, CallAudioPortraitTextView.
5. Resources -> <FEATURE>_<BRANCH>_<WHAT>_<DESCRIPTION>
	1. Drawables: chat_group_icon_landscape
	2. XMLs:
		1. chat_group_activity_landscape || chat_group_activity_portrait.
		2. chat_direct_activity_landscape || chat_direct_activity_portrait.
```

#`<Size>` (Option) : size of resources, often used for dimens, drawables
1. Dimension:  chat_group_icon_landscape_large_50dp, chat_group_icon_landscape_50dp
2. Drawables:  chat_group_icon_landscape_24dp

#References:
1. https://jeroenmols.com/blog/2016/03/07/resourcenaming/
2. https://github.com/ribot/android-guidelines/blob/master/project_and_code_guidelines.md

# License

```
MIT License

Copyright (c) [2020] [Henry]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
