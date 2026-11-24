---
last_updated: 2026-11-23
version: 6.0.0
product_versions:
  android: "1.1.0"
  ios: "1.1.0"
generated_from: "dev-docs/specs/USER_MANUAL_SPEC.instructions.md"
---

# User Manual

## Overview

Bash Practice is an app for learning common bash commands and testing yourself
on them. It is for people who are new to the Linux or macOS command line, or
who want to refresh their memory of everyday commands, their options, and the
operators that join and redirect them.

The app includes a built-in library of 68 commands and operators in ten
categories. You can read about each one, mark it as learned, take quizzes,
practice pipelines, and try examples in an emulator that shows their recorded
output.

| Item | Details |
| --- | --- |
| Platform | Android phones and tablets; iPhone and iPad |
| Interface | Four tabs for **Home**, **Practice**, **Emulator**, and **Docs** (in development; see below) |
| Version | 1.1.0 on Android. On iOS, 1.0.0 is on the App Store and 1.1.0 is waiting for App Review |

<!-- Verified from: platform/android/app/build.gradle.kts [versionName, minSdk] -->
<!-- Verified from: platform/ios/bash-practice.xcodeproj/project.pbxproj [MARKETING_VERSION, TARGETED_DEVICE_FAMILY] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeTab.kt [HomeTab] -->
<!-- Verified from: platform/ios/bash-practice/Views/AppTabs.swift [AppTab, AppTabs] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/CommandLibrary.kt [CommandLibrary.all] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [CommandCategory] -->

Bash Practice does not run bash commands or connect to a shell or server. It
checks your quiz answers on the device.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_device_body] -->
<!-- Verified from: platform/ios/bash-practice/Views/PrivacyView.swift [PrivacyView] -->

### Interface in Development

This manual describes the interface that is in development for the next
Android and iOS versions: the **Home**, **Practice**, **Emulator**, and
**Docs** tabs. It is not in Google Play or the App Store yet.

The versions available now (1.1.0 on Android; 1.0.0 on iOS, with 1.1.0
waiting for App Review) have the same command library, quizzes, and pipeline
practice, arranged differently:

| In this manual | In the versions available now |
| --- | --- |
| **Home** tab | Not present; the app opens on the **Learn** tab |
| **Commands** in the **Docs** tab | The **Learn** tab |
| **Guides** in the **Docs** tab | The **Docs** tab (Android 1.1.0 and iOS 1.1.0) |
| **Emulator** tab | **Practice Terminal** in the **Practice** tab (Android 1.1.0 and iOS 1.1.0) |
| **Send Feedback** on **Home** and under **About** | **More options** (three dots) on each tab on Android and in iOS 1.0.0; under **About** in **Docs** in Android 1.1.0 and iOS 1.1.0 |

Those versions also have a **Progress** tab, which shows learned and quiz
totals and holds **Reset All Progress**. The interface described here does not
have that tab; **Reset All Progress** is under **About** in **Docs** >
**Guides**. Commands you marked as learned and your quiz answers are kept. In
those versions a pipeline round has 5 to 14 questions, and the length you
choose is not kept after you close the app.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [TabHost] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [guideItems, ResetRow] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [GuideList] -->
<!-- Verified from: platform/ios/bash-practice/Views/AppTabs.swift [AppTabs] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [CommandProgress] -->
<!-- Verified from: platform/ios/bash-practice/Progress/ProgressFile.swift [load] -->

## Installation and Setup

### Check the System Requirements

| Requirement | Details |
| --- | --- |
| Device | Android phone or tablet, or iPhone or iPad |
| Operating system | Android 8.0 or later, or iOS 17 or later |
| Account or sign-in | None required |
| Internet connection | Not required to learn or practice |

<!-- Verified from: platform/android/app/build.gradle.kts [minSdk = 26] -->
<!-- Verified from: platform/android/app/src/main/AndroidManifest.xml [no permissions declared] -->
<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_device_body, privacy_services_body] -->
<!-- Verified from: platform/ios/bash-practice.xcodeproj/project.pbxproj [IPHONEOS_DEPLOYMENT_TARGET] -->

### Install on Android

Install Bash Practice from
[Google Play](https://play.google.com/store/apps/details?id=com.plaintxtoffice.bashpractice).
It needs no account.

<!-- Verified from: platform/android/app/build.gradle.kts [applicationId] -->

### Install on iOS

Install Bash Practice on your iPhone or iPad from the
[App Store](https://apps.apple.com/app/id6837567763). It needs no account.

<!-- Verified from: platform/ios/bash-practice.xcodeproj/project.pbxproj [PRODUCT_BUNDLE_IDENTIFIER, IPHONEOS_DEPLOYMENT_TARGET] -->

### Set Up the App

No setup is needed. The command library is included with the app, and your
progress starts empty the first time you open it.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/CommandLibrary.kt [CommandLibrary] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/ProgressRepository.kt [ProgressRepository] -->

## Starting the Program

### Open Bash Practice

1. On your Home screen or in your app list, tap **Bash Practice**.
1. The app opens on the **Home** tab, which has a card for each of the other
   tabs.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [app_name] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [selectedTab = HomeTab.HOME] -->
<!-- Verified from: platform/ios/bash-practice/Views/AppTabs.swift [tab = AppTab.home] -->

### Close Bash Practice

The app has no quit command. Leave it the way you leave any app on your
device, such as by going to the Home screen. Learned commands and quiz answers
are saved as you go.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailViewModel.kt [toggleLearned] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizViewModel.kt [submit] -->
<!-- Verified from: platform/ios/bash-practice/Views/QuizView.swift [submit] -->

## Getting Around

The app has four tabs.

| Tab | What you find there |
| --- | --- |
| **Home** | A card that opens each of the other tabs, and **Send Feedback** |
| **Practice** | Command quizzes and pipeline exercises |
| **Emulator** | A prompt where you type examples to see their recorded output |
| **Docs** | **Commands**, the searchable command library, and **Guides**, six guides with worked examples plus privacy information, feedback, **Reset All Progress**, and the app version under **About** |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeTab.kt [HomeTab, homeDestinations] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [PracticeScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/terminal/TerminalScreen.kt [TerminalRoute] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [DocsSegment, DocsScreen] -->
<!-- Verified from: platform/ios/bash-practice/Views/AppTabs.swift [AppTabs] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [DocsSegment, DocsView] -->

On an Android phone the tabs appear in a bar at the bottom of the screen; on
a tablet or other wide window they appear in a rail at the side. On iPhone
and iPad they appear in the tab bar.

A screen you open from a tab, such as a command page or a guide, opens inside
that tab, and the tabs stay in view. On Android this also applies to quizzes
and pipeline rounds; on iPhone and iPad those fill the screen until you finish
or end them. Each tab keeps its place while you use another one.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [FloatingTabBar, TabRail, RailMinWidth, PushedScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/Navigation.kt [MainNavigation, tabEntryProvider] -->
<!-- Verified from: platform/ios/bash-practice/Views/PracticeView.swift [fullScreenCover] -->
<!-- Verified from: platform/ios/bash-practice/Views/AppTabs.swift [TabView] -->

The **Home** tab shows the app's name and three cards: **Practice**,
**Emulator**, and **Docs**. Tap a card to open that tab. Below the cards,
**Send Feedback** opens the feedback screen.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [HomeScreen, DestinationCard, FeedbackPill] -->
<!-- Verified from: platform/ios/bash-practice/Views/HomeView.swift [HomeView] -->

In **Docs**, tap **Commands** or **Guides** at the top to switch between the
command library and the guides. Tap a command or a guide to open it. Use the
back button at the top left to return. On Android you can also use the system
Back gesture, which returns to **Home** from the other tabs.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [SegmentedControl] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeTab.kt [afterBack] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/Navigation.kt [MainNavigation] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [Picker] -->

The library uses these categories:

| Category | Examples |
| --- | --- |
| Getting Help | `man`, `help`, `type`, `history` |
| Files & Folders | `ls`, `cd`, `cp`, `rm`, `find` |
| Viewing Files | `cat`, `less`, `head`, `tail` |
| Text Processing | `grep`, `sed`, `awk`, `sort` |
| Pipes & Redirection | `\|`, `>`, `>>`, `2>`, `&&` |
| Permissions & Users | `chmod`, `chown`, `sudo` |
| Processes & Jobs | `ps`, `kill`, `jobs`, `fg` |
| Variables & Scripting | `echo`, `export`, `source`, `test` |
| System & Archives | `df`, `du`, `tar`, `gzip` |
| Networking | `curl`, `ping`, `ssh`, `scp` |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/CommandLibrary.kt [CommandLibrary.all] -->
<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [category_*] -->

The app follows your device's light or dark appearance.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/ui/theme/Theme.kt [BashPracticeTheme] -->
<!-- Verified from: platform/ios/bash-practice/Theme/Theme.swift [Theme] -->

## Everyday Tasks

### Browse and Search the Command Library

1. Tap the **Docs** tab. It opens on **Commands**; if **Guides** is showing,
   tap **Commands**.
1. Scroll through the categories, or tap the search field. The empty field
   shows **Command, operator, or task** on Android and **Commands, aliases, or
   tasks** on iOS.
1. Type part of a command's name, another way of writing it, or words from its
   description. The list shows only matching entries.
1. Tap a command to open it.

To clear the search, tap **Clear search** (the X) in the field. A check mark
next to a command means you marked it as learned. If nothing matches, the app
says there are no results for your search.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [commandItems, SearchField, CommandListItem, NoResults] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/CommandListViewModel.kt [commandSections] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [CommandList, CommandRow] -->
<!-- Verified from: platform/ios/bash-practice/Theme/Components.swift [SearchField] -->

### Study a Command

The page for a command shows:

- Its category and kind. The kind is **Shell builtin** (part of bash itself),
  **Program** (a separate program on the system), or **Operator** (symbols
  that join or redirect commands, such as `|`).
- Its name and a short summary of what it does.
- **Syntax**, showing its common options.
- **Also written as**, when bash accepts another spelling, such as `.` for
  `source`.
- **Examples**, each with an explanation and its recorded **Output**: what
  the terminal prints when you run it, or a note that the command prints
  nothing when it succeeds. The app never runs commands.
- **Tip**, for some commands.
- On Android, **Quiz record: X of Y correct**, after you have answered quiz
  questions about it.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt [CommandDetails] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [CommandKind, Command.alternatives] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/ui/WorkedExample.kt [WorkedExample, RecordedOutput] -->
<!-- Verified from: platform/ios/bash-practice/Views/CommandDetailView.swift [CommandDetailView] -->
<!-- Verified from: platform/ios/bash-practice/Views/ExampleRow.swift [ExampleRow] -->

### Copy a Command

1. Open a command's page.
1. Next to the syntax or an example, tap the copy button.
1. The text is placed on the clipboard so you can paste it into another app,
   such as a terminal.

Android 13 and later show their own confirmation when text is copied; earlier
versions show a short **Copied** message. Other apps can read text you paste
into them. Examples in the guides and in quiz feedback have the same copy
button.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/ui/Components.kt [CodeBlock] -->
<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_copy_body] -->
<!-- Verified from: platform/ios/bash-practice/Theme/Components.swift [CodeBlock] -->

### Mark a Command as Learned

1. Open a command's page.
1. Tap **Mark as Learned** at the bottom of the screen. The button changes to
   **Learned** on Android and **Mark as Not Learned** on iOS.
1. To undo it, tap the button again.

Learned commands show a check mark in the **Commands** list in **Docs**, and
you can leave them out of a quiz by choosing **Not Yet Learned**. If the
change cannot be saved, the app shows **Couldn't update progress** on Android
or **Couldn't save progress** on iOS and leaves your progress unchanged.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt [LearnedButton, SaveFailedDialog] -->
<!-- Verified from: platform/ios/bash-practice/Views/CommandDetailView.swift [toggleLearned] -->
<!-- Verified from: platform/ios/bash-practice/BashPracticeApp.swift [AppContent] -->

### Take a Quiz

1. Tap the **Practice** tab.
1. Under **Quiz Type**, choose a quiz type:
   - **Multiple Choice**: pick the right command from four choices.
   - **Type the Command**: read the description and type the command.
1. Under **Commands**, tap the **Practice** row and choose which commands to
   include.
1. Use the minus and plus buttons next to **Questions** to choose how many
   questions to ask.
1. Tap **Start Quiz**.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [QuizTypeOption, ScopePicker, CountStepperRow] -->
<!-- Verified from: platform/ios/bash-practice/Views/PracticeView.swift [PracticeView, scopeRow] -->

| Option | Default | Accepted values |
| --- | --- | --- |
| Quiz Type | **Multiple Choice** | **Multiple Choice** or **Type the Command** |
| Practice | **All Commands** | **All Commands**, **Not Yet Learned**, **Needs Review**, or one category |
| Questions | 10 | 5 to 30, in steps of 5 |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeViewModel.kt [PracticeSettings, MIN_QUESTIONS, MAX_QUESTIONS, QUESTION_STEP] -->
<!-- Verified from: platform/ios/bash-practice/Views/PracticeView.swift [count, countRange, countStep] -->

**Needs Review** holds commands you have missed at least once and answer
correctly less than 70% of the time.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [needsReview] -->

Each question in a quiz is about a different command. If your selection has
fewer commands than the number of questions, the quiz asks one question per
command. On Android, the **Practice** menu shows how many commands each of the
first three choices contains. **Start Quiz** is unavailable when the selection
is empty, and a note below it explains why.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Quiz.kt [QuizBuilder.makeQuestions] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [scopeTitle, canStart] -->
<!-- Verified from: platform/ios/bash-practice/Views/PracticeView.swift [CardFooter] -->

The app keeps these choices while it is open, but not after it closes.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeViewModel.kt [settings] -->

### Answer Quiz Questions

The quiz shows the question number at the top, such as **1 of 10**, and a
progress bar. A caption above each question names its kind:

- **Command** or **Operator**: the question is a description of what a command
  or an operator does.
- **Task**: the question is a task, taken from one of the command's examples.

When the answer to a task question is an operator, the quiz shows the example
command with the operator replaced by a blank; iOS captions that question
**Operator**. In a **Multiple Choice** quiz, the other three choices come from
the same category when possible. Android task questions use examples led by
the answer or its other spelling. Choices exclude other commands in that
example and known equivalent answers.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Quiz.kt [QuestionKind, QuizBuilder] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [QuestionContent, questionKindLabel] -->

On iOS, a task question uses only an example that starts with the command or one
of its other spellings, so the command is its answer. For an operator, the
other choices are operators. On iOS, the other choices never include a command
that appears in the example, or `type` when the answer is `which`, or `printf`
when the answer is `echo`.

<!-- Verified from: platform/ios/bash-practice/Practice/Quiz.swift [QuizQuestion.tasks, QuizQuestion.wrongChoices, QuizQuestion.blankedCode] -->
<!-- Verified from: platform/ios/bash-practice/Views/QuizView.swift [prompt] -->

In a **Multiple Choice** quiz, tap one of the four choices. The correct choice
is highlighted with a check mark, and a wrong choice you picked is highlighted
with an X.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [Choices] -->
<!-- Verified from: platform/ios/bash-practice/Views/QuizView.swift [mark] -->

In a **Type the Command** quiz:

1. Read the description or task.
1. Type the command after the **$** prompt.
1. Tap **Check**, or tap the done key on the keyboard.

Typed answers are case-sensitive, just as bash is: `ls` is correct but `LS` is
not. Spaces before and after the answer are ignored. Other spellings shown
under **Also written as** are accepted too, such as `.` for `source` and `[`
for `test`.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [TypedInput] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [Command.matches] -->
<!-- Verified from: platform/ios/bash-practice/Views/QuizView.swift [typedAnswer] -->

After you answer, the app shows **Correct!** or tells you the answer:
**Not quite. The answer is** followed by the answer on Android, and **Not
quite** with the **Answer** on iOS. It then shows an example of the command
with its explanation. For a task question it also shows the command's summary.
Tap **Next Question** to continue, or **See Results** after the last question.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [Feedback, bottomBar] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Quiz.kt [QuizQuestion.example] -->
<!-- Verified from: platform/ios/bash-practice/Views/QuizView.swift [feedback] -->

Each answer is saved as soon as you give it. If it cannot be saved, the app
shows **Couldn't save your answer**. To leave a quiz early, tap **Close** (the
X) at the top left; answers you already gave stay saved. The app asks **End
this quiz?**; tap **End Quiz** to leave. On Android, the system Back gesture
asks the same question.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizViewModel.kt [submit] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [QuizScreen, ConfirmDialog] -->
<!-- Verified from: platform/ios/bash-practice/Views/QuizView.swift [confirmationDialog] -->

### Review Your Quiz Results

At the end of a quiz, the **Results** screen shows your score, such as **8 /
10**, with a short message. **Review These** lists each command you missed
with its summary. Tap **Done** to return to the **Practice** tab.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [QuizResults] -->
<!-- Verified from: platform/ios/bash-practice/Views/QuizSummary.swift [QuizSummary] -->

### Read a Guide

1. Tap the **Docs** tab, then tap **Guides**.
1. Tap a guide: **Command Conventions**, **Paths and Wildcards**, **Quoting
   and Variables**, **Piping Techniques**, **Redirection**, or **Exit Status
   and Chaining**.

Each section explains a technique and shows worked examples with their
recorded output. Tap the copy button beside an example to put the command on
the clipboard.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [guideItems, GuideScreen] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [GuideList, GuideView] -->
<!-- Verified from: platform/ios/bash-practice/guides.json -->

### Use the Emulator

1. Tap the **Emulator** tab.
1. After the **$** prompt, type an example from **Docs**, such as `pwd`, or
   tap **Try an Example** (the dice) at the top right to fill in a random one.
1. Tap **Run**, or press the Go key on the keyboard. For `pwd`, the recorded
   output is `/home/alex/projects/site`.
1. If you enter a known command with different arguments, the emulator lists
   that command's examples. Tap one to fill it in, then tap **Run**.
1. Tap **Clear Screen** (the eraser) at the top right, or enter `clear`, to
   empty the screen.

The emulator looks up examples on the device. It never runs what you type and
never changes files. If you enter something that is not in the command
library, it tells you to find an example in **Docs**.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/PracticeTerminal.kt [reply] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/terminal/TerminalScreen.kt [TerminalScreen, TerminalTools, TerminalHistory] -->
<!-- Verified from: platform/ios/bash-practice/Views/EmulatorView.swift [EmulatorView, EntryView] -->
<!-- Verified from: platform/ios/bash-practice/Practice/PracticeTerminal.swift [PracticeTerminal.reply] -->

### Practice Pipelines

A pipeline joins commands with `|` so that each one works on the output of
the one before it. Each question gives an everyday task, such as counting the
lines of a log file that contain 404.

1. Tap the **Practice** tab and scroll to **Pipelines**.
1. Choose how to answer:
   - **Pick the Pipeline**: choose the pipeline that does the task from four.
     Each wrong choice has one command swapped for a likely mistake.
   - **Build the Pipeline**: tap the commands into order. One command is a
     decoy that the pipeline does not need.
1. Use the minus and plus buttons next to **Questions** to choose from 1
   question up to all 14 pipeline exercises. The first round has 10; after
   that, the app remembers your choice, even after you close it.
1. Tap **Start Pipeline Quiz**.
1. For each question, tap a pipeline under **Answer Choices**, or tap
   commands under **Commands** to place them in **Your Pipeline**. Tap a
   command you placed to take it back out.
1. Tap **Check Answer**.

After each answer, the app shows the right pipeline and explains how it
works. Tap **Next Question** to continue, or **See Results** after the last
question. **Pipeline Results** shows your score and lists the pipelines you
missed under **Pipelines to Review**; tap **Done** to return to **Practice**.
Pipeline answers are not added to your quiz record or to **Needs Review**.

To leave early, tap **End Practice** at the top left. The app asks **End this
practice?**; tap **End Practice** again to leave. On Android, the system Back
gesture asks the same question.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Pipeline.kt [PipelineQuizBuilder, PipelineLibrary, MIN_PIPELINE_QUESTIONS, MAX_PIPELINE_QUESTIONS, DEFAULT_PIPELINE_QUESTIONS, restoredPipelineQuestionCount] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/PracticePreferences.kt [PipelineQuestionCountSetting] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [PipelineModeOption] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/pipeline/PipelineScreen.kt [PipelineChoices, PipelineBuilder, PipelineFeedback, PipelineResults] -->
<!-- Verified from: platform/ios/bash-practice/Practice/Pipeline.swift [PipelineSession.questionCountRange, defaultQuestionCount, questionCount] -->
<!-- Verified from: platform/ios/bash-practice/Views/PracticeView.swift [savedPipelineCount] -->
<!-- Verified from: platform/ios/bash-practice/Views/PipelineView.swift [questionScreen, builder, feedback, PipelineSummary] -->

### Read the Privacy Information

1. Tap the **Docs** tab, then tap **Guides**.
1. Under **About**, at the end of the list, tap **Privacy**.
1. Read the privacy information. It is available without a network
   connection.

At the end of the privacy information, **Send Feedback** opens the feedback
screen, **Contact Plain Text Office** opens the developer's website, and
**Full Privacy Policy** opens the published policy in your browser.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [guideItems] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/privacy/PrivacyScreen.kt [PrivacyScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackIntents.kt [openContactPage] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [GuideList] -->
<!-- Verified from: platform/ios/bash-practice/Views/PrivacyView.swift [PrivacyView] -->

### Reset Your Progress

**Reset All Progress** clears every command you marked as learned and all your
quiz answers, so you can start over. It cannot be undone.

1. Tap the **Docs** tab, then tap **Guides**.
1. Under **About**, tap **Reset All Progress**.
1. When the app asks **Reset all progress?**, tap **Reset All Progress** to
   confirm. To keep your progress, tap **Cancel** on Android. On iPhone and
   iPad, tap **Cancel** if the prompt shows it, or tap outside the prompt.

**Reset All Progress** is dimmed when there is nothing to clear. If the reset
fails, the app says so and your progress is unchanged.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [ResetRow, ConfirmDialog, DocsRoute] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/CommandListViewModel.kt [reset] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [GuideList.resetRow, confirmationDialog] -->
<!-- Verified from: platform/ios/bash-practice/Progress/ProgressStore.swift [reset] -->

## Settings and Preferences

The app has no settings screen. It remembers the number of pipeline questions
you last chose in **Practice** and uses it the next time you open the app.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeViewModel.kt [PracticeViewModel, stepPipelineQuestionCount] -->
<!-- Verified from: platform/ios/bash-practice/Views/PracticeView.swift [savedPipelineCount] -->

## Importing and Exporting

Not Applicable.
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt, platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt, platform/ios/bash-practice/Views/DocsView.swift -->

## Commands and Shortcuts

The app has no keyboard shortcuts. These on-screen controls perform its main
actions.

| Control | Where | What it does |
| --- | --- | --- |
| **Home**, **Practice**, **Emulator**, **Docs** | Tab bar, or side rail on a wide Android window | Switch between the main screens |
| **Practice**, **Emulator**, **Docs** cards | **Home** | Open that tab |
| **Send Feedback** | **Home**; **About** under **Guides** in **Docs** | Opens the feedback screen |
| **Commands** / **Guides** | **Docs**, at the top | Switches between the command library and the guides |
| Search field | **Commands** in **Docs** | Filters commands by name, other spelling, or description |
| Copy button | Command page, guides, quiz feedback | Copies the syntax or an example to the clipboard |
| **Mark as Learned** | Command page | Marks or unmarks the command as learned |
| **Start Quiz** | **Practice** | Starts a quiz with the chosen options |
| **Start Pipeline Quiz** | **Practice** | Starts a round of pipeline questions |
| **Check** | Quiz, **Type the Command** | Checks your typed answer |
| **Check Answer** | Pipeline question | Checks the pipeline you picked or built |
| **Next Question** / **See Results** | Quiz and pipeline questions | Moves to the next question or the results |
| **Close** | Quiz, top left | Leaves the quiz, after asking you to confirm |
| **End Practice** | Pipeline question, top left | Leaves the pipeline round, after asking you to confirm |
| **Run** | **Emulator** | Shows the recorded output of the example you typed |
| **Try an Example** | **Emulator**, top right | Fills in a random example |
| **Clear Screen** | **Emulator**, top right | Empties the emulator screen |
| **Privacy** | **About** under **Guides** in **Docs** | Opens the privacy information |
| **Reset All Progress** | **About** under **Guides** in **Docs** | Clears learned commands and quiz answers, after asking you to confirm |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [FloatingTabBar, TabRail, HomeScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [SegmentedControl, SearchField, guideItems] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/ui/Components.kt [CodeBlock] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt [LearnedButton] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [practice_start, practice_pipelines_start] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [TypedInput, NavRow, bottomBar] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/pipeline/PipelineScreen.kt [PipelineScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/terminal/TerminalScreen.kt [TerminalScreen, TerminalTools] -->
<!-- Verified from: platform/ios/bash-practice/Views/HomeView.swift [HomeView] -->
<!-- Verified from: platform/ios/bash-practice/Views/EmulatorView.swift [EmulatorView] -->
<!-- Verified from: platform/ios/bash-practice/Views/PipelineView.swift [PipelineView] -->

## Your Data Files

The app keeps its records inside its own storage on your device. You do not
open or edit these records by hand, and the app does not show their location.

| Data | Where it is stored | Can you edit it? |
| --- | --- | --- |
| Command library | Included with the app | No |
| Learned commands and quiz answers for each command | The app's private storage on your device: the `progress.db` database on Android and `progress.json` on iPhone and iPad (see below) | No; change it through the app |
| The number of pipeline questions you last chose | The app's settings on your device | No; change it in **Practice** |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/di/AppModule.kt [database, Room.databaseBuilder "progress.db"] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [CommandProgress] -->
<!-- Verified from: platform/ios/bash-practice/Progress/ProgressFile.swift [fileURL] -->

To remove your learned commands and quiz answers, use **Reset All Progress**
(see [Reset Your Progress](#reset-your-progress)). On Android, clearing the
app's storage in Android Settings or uninstalling the app also removes them.
Device backups may keep earlier copies. The app has no user-visible log files.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_removing_body] -->
<!-- Verified from: platform/android/app/src/main/AndroidManifest.xml [android:allowBackup] -->

On iOS, the app saves learned commands and quiz answers in `progress.json` in
its Application Support folder, which iCloud and computer backups of the device
include. If that file cannot be read when the app opens, the app renames it
`progress.corrupt.json`, replacing any earlier copy, starts with empty progress,
and shows **Saved progress was reset** once. Deleting the app removes both
files from the device; earlier backups may still hold older copies.

<!-- Verified from: platform/ios/bash-practice/Progress/ProgressFile.swift [load, corruptCopy, fileURL] -->
<!-- Verified from: platform/ios/bash-practice/BashPracticeApp.swift [AppContent] -->
<!-- Verified from: platform/ios/bash-practice/Views/PrivacyView.swift [PrivacyView] -->

## Troubleshooting

| Symptom | Likely Cause | Resolution |
| --- | --- | --- |
| **Start Quiz** is unavailable. | The chosen **Practice** selection has no commands, such as **Needs Review** before you have missed any questions. | Choose **All Commands**, **Not Yet Learned**, or a category. |
| A quiz has fewer questions than you chose. | The selection has fewer commands than the **Questions** value. | Choose a larger selection to get more questions. |
| A typed answer that looks right is marked wrong. | Typed answers are case-sensitive, or the keyboard changed a character. | Type the command exactly as bash expects it, usually in lowercase. |
| The emulator lists examples instead of showing output. | It knows the command but has no recorded output for those arguments. | Tap one of the listed examples, then tap **Run**. |
| The emulator says what you typed is not in the command library. | The first word is not one of the app's commands. | Look up a command in **Docs** and type one of its examples. |
| **Couldn't update progress** appears on Android, or **Couldn't save progress** on iOS. | The learned status could not be saved. | Tap **OK** and try again. Your progress was not changed. |
| **Couldn't save your answer** appears during a quiz. | The answer could not be recorded. | Tap **OK** and continue. That question's result was not recorded. |
| **No email app was found. Use the contact page instead.** | No app on the Android device can open the feedback email. | Tap **Use the contact page instead**, or install an email app. |
| **No app was found to open the link.** | No browser on the Android device can open the developer's website. | Install or enable a web browser, then try again. |
| On iOS, **Saved progress was reset** appears when the app opens. | The saved progress file could not be read, so the app kept it as `progress.corrupt.json` and started with empty progress. | Tap **OK**. Learned commands and quiz answers you add from now on are saved as usual. |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [canStart, practice_nothing_to_review] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Quiz.kt [QuizBuilder.makeQuestions] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [Command.matches] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/terminal/TerminalScreen.kt [TerminalHistory] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt [SaveFailedDialog] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [SaveFailedDialog] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackScreen.kt [FeedbackError] -->
<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [feedback_no_email_app, open_link_failed] -->
<!-- Verified from: platform/ios/bash-practice/Views/EmulatorView.swift [EntryView] -->
<!-- Verified from: platform/ios/bash-practice/BashPracticeApp.swift [AppContent] -->
<!-- Verified from: platform/ios/bash-practice/Progress/ProgressFile.swift [load] -->

## FAQ

### Does the app run bash commands?

No. The app does not run bash commands or connect to a shell or server. The
**Emulator** shows recorded output for the examples in the app. Try commands
for real in a terminal on Linux, macOS, or another system with bash.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_device_body] -->

### Do I need an internet connection?

No. The command library is included with the app, and answers are checked on the
device. **Contact Plain Text Office**, **Use the contact page instead**, and
**Full Privacy Policy** open your browser. **Send by email** on Android, and
**Report a Problem** and **Suggest a Feature** on iOS, open your email app.

<!-- Verified from: platform/android/app/src/main/AndroidManifest.xml [no INTERNET permission] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackIntents.kt [openContactPage, openFeedbackEmail] -->
<!-- Verified from: platform/ios/bash-practice/Views/FeedbackView.swift [FeedbackView] -->

### Does capitalization matter in typed answers?

Yes. Bash treats `ls` and `LS` as different names, and so does the quiz.
Spaces before and after your answer are ignored.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [Command.matches] -->

### What is the difference between a builtin, a program, and an operator?

A shell builtin, such as `cd`, is part of bash itself. A program, such as
`grep`, is a separate file that bash finds and runs. An operator, such as `|`
or `>>`, is not a command at all: it tells bash how to connect commands or
where to send their output. The command's page shows which kind each entry is.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [CommandKind] -->

### How does a command get into Needs Review?

A command joins the **Needs Review** choice on the **Practice** tab after you
miss it at least once and your correct answers for it fall below 70%. It
leaves when your accuracy for it reaches 70% or more.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [needsReview] -->

### Does the app collect analytics or require an account?

No. This version contains no developer-run analytics, advertising, or account
service.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_services_body] -->
<!-- Verified from: platform/ios/bash-practice/Views/PrivacyView.swift [PrivacyView] -->

## Feedback

To report a bug or request a feature, email
[feedback@plaintxtoffice.com](mailto:feedback@plaintxtoffice.com), use the
contact page at <https://plaintxtoffice.com/contact/>, or use the feedback
screen in the app:

| Platform | How to open feedback |
| --- | --- |
| Android | On the **Home** tab, tap **Send Feedback**. Or open **Docs**, tap **Guides**, and tap **Send Feedback** under **About**. In version 1.1.0, tap **More options** (three dots) at the top right of any tab, then **Send feedback**. |
| iOS | On the **Home** tab, tap **Send Feedback**. Or open **Docs**, tap **Guides**, and tap **Send Feedback** under **About**. In version 1.0.0, tap **More options** on any tab, then **Send Feedback**. |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [FeedbackPill] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [guideItems] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackIntents.kt [FEEDBACK_ADDRESS, openContactPage] -->
<!-- Verified from: platform/ios/bash-practice/Views/HomeView.swift [Send Feedback] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [Send Feedback] -->

### Send Feedback from the App

On Android:

1. On the **Home** tab, tap **Send Feedback**.
1. Choose **Bug report** or **Feature request**.
1. Describe the problem or idea in **Details**.
1. Tap **Send by email**. Your email app opens with a draft to
   `feedback@plaintxtoffice.com`.
1. Review the draft and send it from your email app.

The draft includes what you typed plus the app version, Android version, and
device model. It never includes your learned commands or quiz answers. Nothing
is sent unless you send it. **Send by email** is unavailable until you type
some details. If you have no email app, tap **Use the contact page instead**
to open the developer's website.

On iOS, tap **Send Feedback** on the **Home** tab. **Report a Problem** and
**Suggest a Feature** open a new email to `feedback@plaintxtoffice.com` in
your mail app, and **Contact Plain Text Office** opens the contact page.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackScreen.kt [FeedbackRoute, FeedbackScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackIntents.kt [FEEDBACK_ADDRESS, openFeedbackEmail, deviceSummary] -->
<!-- Verified from: platform/ios/bash-practice/Views/FeedbackView.swift [FeedbackView] -->

## Glossary

| Term | Meaning |
| --- | --- |
| Also written as | Another spelling bash accepts for the same command, such as `.` for `source`. |
| Emulator | The tab where you type an example from the app and see its recorded output. Nothing you type is run. |
| Learned | A command you marked with **Mark as Learned**. |
| Needs Review | Commands you missed at least once and answer correctly less than 70% of the time. |
| Operator | Symbols such as `\|`, `>`, or `&&` that join commands or redirect their input and output. |
| Pipeline | Commands joined with `\|` so that each one works on the output of the one before it. |
| Program | A command that is a separate file on the system, such as `grep`. |
| Redirection | Sending a command's input or output to or from a file instead of the screen. |
| Shell builtin | A command that is part of bash itself, such as `cd`. |
| Syntax | The pattern for running a command, with its common options. |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [CommandKind, Command] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/CommandLibrary.kt [REDIRECTION entries] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [needsReview] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/terminal/TerminalScreen.kt [TerminalRoute] -->
