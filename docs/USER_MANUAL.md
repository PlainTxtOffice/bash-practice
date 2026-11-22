---
last_updated: 2026-11-22
version: 5.10.0
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
categories. You can read about each one, mark it as learned, take quizzes, and
follow your progress.

| Item | Details |
| --- | --- |
| Platform | Android phones and tablets; iPhone and iPad |
| Interface | Four tabs for **Learn**, **Practice**, **Progress**, and **Docs** |
| Version | 1.1.0 on Android. On iOS, 1.0.0 is on the App Store and 1.1.0 is waiting for App Review |

<!-- Verified from: platform/android/app/build.gradle.kts [versionName, minSdk] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [HomeTab, HomeRoute] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/CommandLibrary.kt [CommandLibrary.all] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [CommandCategory] -->

Bash Practice does not run bash commands or connect to a shell or server. It
checks your quiz answers on the device.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_device_body] -->

### iOS

Bash Practice 1.1.0 for iPhone and iPad requires iOS 17 or later. Its
**Learn**, **Practice**, **Progress**, and **Docs** tabs provide the command
library, multiple-choice and typed quizzes, pipeline practice, a practice
terminal, on-device progress tracking, and guides. Install it from the
[App Store](https://apps.apple.com/app/id6837567763). The App Store has
version 1.0.0; version 1.1.0, described here, is waiting for App Review.

On iOS, each example on a command's page shows its **Output**: what the
terminal prints when you run it, or a note that it prints nothing. The output
is a recorded sample; the app never runs commands.

The **Docs** tab holds short guides: **Command Conventions**, **Paths and
Wildcards**, **Quoting and Variables**, **Piping Techniques**, **Redirection**,
and **Exit Status and Chaining**. Each has worked examples with their output.
Its **About** section, at the end, opens **Privacy** and **Send Feedback** and
shows the app version. iOS has no **More options** menu.

To use the practice terminal, open **Practice**, tap **Practice Terminal**, type
an example from a command page or a guide, and press Return. The terminal shows
that example's recorded output. For a command it knows but an example it
doesn't, it lists that command's examples to tap; **Try an Example** fills in a
random one, and `clear` or **Clear Screen** empties the screen. Nothing you type
is run.

<!-- Verified from: platform/ios/bash-practice.xcodeproj/project.pbxproj [MARKETING_VERSION, IPHONEOS_DEPLOYMENT_TARGET, TARGETED_DEVICE_FAMILY] -->
<!-- Verified from: platform/ios/bash-practice/Views/PracticeTabs.swift [PracticeTabs] -->
<!-- Verified from: platform/ios/bash-practice/Views/ExampleRow.swift [ExampleRow, ExampleOutput] -->
<!-- Verified from: platform/ios/bash-practice/Views/DocsView.swift [DocsView, GuideView] -->
<!-- Verified from: platform/ios/bash-practice/guides.json -->
<!-- Verified from: platform/ios/bash-practice/Views/TerminalView.swift [TerminalView] -->
<!-- Verified from: platform/ios/bash-practice/Practice/PracticeTerminal.swift [PracticeTerminal.reply] -->

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
1. The app opens on the **Learn** tab, which lists the commands by category.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [app_name] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [selectedTab = HomeTab.LEARN] -->

### Close Bash Practice

The app has no quit command. Leave it the way you leave any Android app, such
as by going to the Home screen. Learned commands and quiz answers are saved as
you go.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailViewModel.kt [toggleLearned] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizViewModel.kt [submit] -->

## Getting Around

The Android app has four tabs. On a phone they appear in a bar at the bottom of
the screen; on a tablet or other wide window they appear in a rail at the side.

| Tab | What you find there |
| --- | --- |
| **Learn** | The command library, grouped by category, with a search field |
| **Practice** | Command quizzes, pipeline exercises, and the **Practice Terminal** |
| **Progress** | Your learned count, quiz accuracy, progress by category, commands that need review, and **Reset All Progress** |
| **Docs** | Six guides with worked examples, plus privacy information, feedback, and the app version under **About** |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [NavigationSuiteScaffold, HomeTab] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/learn/LearnScreen.kt [LearnScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [PracticeScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/stats/StatsScreen.kt [StatsScreen] -->

Each tab has a **More options** menu (three dots) at the top right with
**Privacy** and **Send feedback**. Tap a command to open its detail screen.
Use the back arrow at the top left, or the system Back gesture, to return.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [HomeMenu] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/Navigation.kt [MainNavigation] -->

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

The app follows your device's light or dark theme. On Android 12 and later it
also takes its colours from your wallpaper.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/ui/theme/Theme.kt [BashPracticeTheme] -->

## Everyday Tasks

### Browse and Search the Command Library

1. Tap the **Learn** tab.
1. Scroll through the categories, or tap the search field, which shows
   **Command, operator, or task**.
1. Type part of a command's name, another way of writing it, or words from its
   description. The list shows only matching entries.
1. Tap a command to open it.

To clear the search, tap **Clear search** (the X) in the field. A check mark
next to a command means you marked it as learned. If nothing matches, the app
shows **No results for** your search, with a suggestion to check the spelling.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/learn/LearnScreen.kt [SearchField, CommandListItem, NoResults] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/learn/LearnViewModel.kt [learnSections] -->

### Study a Command

The detail screen for a command shows:

- Its category and kind, such as **Variables & Scripting · Shell builtin**.
  The kind is **Shell builtin** (part of bash itself), **Program** (a separate
  program on the system), or **Operator** (symbols that join or redirect
  commands, such as `|`).
- Its name and a short summary of what it does.
- **Syntax**, showing its common options.
- **Also written as**, when bash accepts another spelling, such as `.` for
  `source`.
- **Examples**, each with an explanation and its recorded **Output**. A silent
  example displays a note explaining that the command prints nothing on success.
- **Tip**, for some commands.
- **Quiz record: X of Y correct**, after you have answered quiz questions
  about it.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt [CommandDetails] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [CommandKind, Command.alternatives] -->

### Copy a Command

1. Open a command's detail screen.
1. Next to the syntax or an example, tap **Copy**.
1. The text is placed on the clipboard so you can paste it into another app,
   such as a terminal.

Android 13 and later show their own confirmation when text is copied; earlier
versions show a short **Copied** message. You can also press and hold the text
to select part of it. Other apps can read text you paste into them.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/ui/Components.kt [CodeBlock] -->
<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_copy_body] -->

### Mark a Command as Learned

1. Open a command's detail screen.
1. Tap **Mark as Learned** at the bottom of the screen. The button changes to
   **Learned**.
1. To undo it, tap **Learned** again.

Learned commands show a check mark in the **Learn** list and count toward the
**Learned** total on the **Progress** tab. If the change cannot be saved, the
app shows **Couldn't update progress** and leaves your progress unchanged.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt [LearnedButton, SaveFailedDialog] -->

### Take a Quiz

1. Tap the **Practice** tab.
1. Under **Quiz Type**, choose a quiz type:
   - **Multiple Choice**: pick the right command from four choices.
   - **Type the Command**: read the description and type the command.
1. Under **Commands**, tap the button next to **Practice** and choose which
   commands to include.
1. Use the down and up arrow buttons next to **Questions** to choose how many
   questions to ask.
1. Tap **Start Quiz**.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [ModeOption, ScopePicker, QuestionCountStepper] -->

| Option | Default | Accepted values |
| --- | --- | --- |
| Quiz Type | **Multiple Choice** | **Multiple Choice** or **Type the Command** |
| Practice | **All Commands** | **All Commands**, **Not Yet Learned**, **Needs Review**, or one category |
| Questions | 10 | 5 to 30, in steps of 5 |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeViewModel.kt [PracticeSettings, MIN_QUESTIONS, MAX_QUESTIONS, QUESTION_STEP] -->

Each question in a quiz is about a different command. If your selection has
fewer commands than the number of questions, the quiz asks one question per
command. The **Practice** menu shows how many commands each of the first three
choices contains. **Start Quiz** is unavailable when the selection is empty,
and a note below it explains why.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Quiz.kt [QuizBuilder.makeQuestions] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [scopeTitle, canStart] -->

The app keeps these choices while it is open, but not after it closes.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeViewModel.kt [settings] -->

### Answer Quiz Questions

The quiz shows the question number at the top, such as **1 of 10**, and a
progress bar. Each question is one of two kinds:

- **Which command does this?** shows a description of what a command does.
- **Which command would you use to…** shows a task, taken from one of the
  command's examples.

When the answer is an operator, the question says **operator** instead of
**command**. In a **Multiple Choice** quiz, the other three choices come from
the same category when possible. Android task questions use examples led by the
answer or its other spelling. For an operator task, fill the blank in the
displayed command. Choices exclude other commands in that example and known
equivalent answers.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Quiz.kt [QuestionKind, QuizBuilder] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [questionHeading] -->

On iOS, a task question uses only an example that starts with the command or one
of its other spellings, so the command is its answer. For an operator, iOS shows
the example with the operator replaced by a blank and asks
**Which operator completes this command?**, and the other choices are operators.
On iOS, the other choices never include a command that appears in the example,
or `type` when the answer is `which`, or `printf` when the answer is `echo`.

<!-- Verified from: platform/ios/bash-practice/Practice/Quiz.swift [QuizQuestion.tasks, QuizQuestion.wrongChoices, QuizQuestion.blankedCode] -->
<!-- Verified from: platform/ios/bash-practice/Views/QuizView.swift [prompt] -->

In a **Multiple Choice** quiz, tap one of the four choices. The correct choice
is highlighted with a check mark, and a wrong choice you picked is highlighted
with an X.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [Choices] -->

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

After you answer, the app shows **Correct!** or **Not quite. The answer is**
followed by the answer, and then an example of the command with its
explanation. For a task question it also shows the command's summary. Tap
**Next Question** to continue, or **See Results** after the last question.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [Feedback, bottomBar] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Quiz.kt [QuizQuestion.example] -->

Each answer is saved as soon as you give it. If it cannot be saved, the app
shows **Couldn't save your answer**. To leave a quiz early, tap **Close** (the
X) at the top left or use the system Back gesture; answers you already gave
stay saved.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizViewModel.kt [submit] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [QuizRoute, navigationIcon] -->

### Review Your Quiz Results

At the end of a quiz, the **Results** screen shows your score, such as **8 /
10**, with a short message. **Review These** lists each command you missed
with its summary. Tap **Done** to return to the **Practice** tab.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [QuizResults] -->

### Read a Guide on Android

Open **Docs** and choose a guide. The guides cover command conventions, paths
and wildcards, quoting and variables, piping, redirection, and exit status and
chaining. Each section explains a technique and shows worked examples. Tap
**Copy** beside an example to put the command on the clipboard.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/docs/DocsScreen.kt [GuideScreen] -->

### Use the Practice Terminal on Android

1. Open **Practice** and tap **Practice Terminal**.
1. Type an example from **Learn** or **Docs**, such as `pwd`, or tap
   **Try an Example** to fill in a random one.
1. Tap **Run** or press the keyboard’s Go key. For `pwd`, the recorded output is
   `/home/alex/projects/site`.
1. If you enter a known command with different arguments, tap one of its
   suggested examples, then tap **Run**.
1. Tap **Clear Screen** or enter `clear` to clear the transcript.

The terminal looks up examples on the device. It never executes input or changes
files.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/PracticeTerminal.kt [reply] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/terminal/TerminalScreen.kt [TerminalScreen] -->

### Practice Pipelines

A pipeline joins commands with `|` so that each one works on the output of
the one before it. The **Pipelines** section at the bottom of the **Practice**
tab has two ways to practice them. Each round asks 10 questions about
everyday tasks, such as counting the lines of a log file that contain 404.

- **Pick the Pipeline**: choose the pipeline that does the task from four.
  Each wrong choice has one command swapped for a likely mistake.
- **Build the Pipeline**: tap the commands into order. One command is a decoy
  that the pipeline does not need. Tap a command you placed to take it back
  out. Once every stage is in place, tap **Check** on Android or **Check
  Answer** on iPhone.

After each answer, the app shows the right pipeline and explains how it
works. At the end, the results list the pipelines you missed. Pipeline
answers are not added to your accuracy, answer count, or **Needs Review**
list. To leave early, tap **Close** on Android or **End Practice** on iPhone.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Pipeline.kt [PipelineQuizBuilder, PipelineLibrary] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/pipeline/PipelineScreen.kt [PipelineBuilder, PipelineFeedback, PipelineResults] -->
<!-- Verified from: platform/ios/bash-practice/Views/PipelineView.swift [builder, feedback, PipelineSummary] -->

### Check Your Progress

Tap the **Progress** tab to see:

- **Learned**: how many of the 68 commands you marked as learned.
- **Accuracy**: the percentage of all quiz answers that were correct, or a
  dash before your first answer.
- **Answers**: the total number of quiz answers you have given.
- **By Category**: learned commands in each category, with a progress bar.
- **Needs Review**: commands you have missed at least once and answer
  correctly less than 70% of the time, listed with your correct and total
  answers. The lowest accuracy is listed first. Tap one to open its detail
  screen.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/stats/StatsScreen.kt [StatsScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/stats/StatsViewModel.kt [statsUiState] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [needsReview, accuracy] -->

### Reset All Progress

1. Tap the **Progress** tab.
1. Scroll down and tap **Reset All Progress**.
1. In **Reset all progress?**, tap **Reset**. Tap **Cancel** to keep your
   progress.

This clears learned commands and quiz history, and it cannot be undone. The
button is unavailable when there is no progress to clear. If the reset fails,
the app shows **Couldn't reset progress** and leaves your progress unchanged.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/stats/StatsScreen.kt [confirmingReset, AlertDialog] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/stats/StatsViewModel.kt [canReset, reset] -->

### Send Feedback

Use **Send feedback** to report a bug or ask for a feature. On Android:

1. On any tab, tap **More options** (three dots) at the top right.
1. Tap **Send feedback**.
1. Choose **Bug report** or **Feature request**.
1. Describe the problem or idea in **Details**.
1. Tap **Send by email**. Your email app opens with a draft to
   `support@plaintxtoffice.com`.
1. Review the draft and send it from your email app.

The draft includes what you typed plus the app version, Android version, and
device model. It never includes your learned commands or quiz answers. Nothing
is sent unless you send it. **Send by email** is unavailable until you type
some details. If you have no email app, tap **Use the contact page instead**
to open the developer's website.

On iOS, open **Docs** and tap **Send Feedback** in the **About** section.
**Report a Problem** and **Suggest a Feature** open a new email to
`support@plaintxtoffice.com` in your mail app, and **Contact Plain Text
Office** opens the contact page. In version 1.0.0, **Send Feedback** is in
**More options** on each tab.

You can also email
[support@plaintxtoffice.com](mailto:support@plaintxtoffice.com) directly, use
the [contact page](https://plaintxtoffice.com/contact/), or open an issue in
[GitHub Issues](https://github.com/PlainTxtOffice/bash-practice/issues).

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackScreen.kt [FeedbackRoute, FeedbackScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackIntents.kt [FEEDBACK_ADDRESS, openFeedbackEmail, deviceSummary] -->
<!-- Verified from: platform/ios/bash-practice/Views/FeedbackView.swift [FeedbackView] -->

### Read the Privacy Information

1. On any tab, tap **More options** (three dots) at the top right.
1. Tap **Privacy**.
1. Read the privacy information. It is available without a network
   connection.
1. To contact the developer, tap **Contact Plain Text Office**. This opens the
   developer's website.

You can also open **Privacy** from **Docs** under **About**. Use
**Full Privacy Policy** to read the published policy in your browser or
**Send feedback** to open the feedback form.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/privacy/PrivacyScreen.kt [PrivacyScreen] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackIntents.kt [openContactPage] -->

On iOS, open **Docs** and tap **Privacy** in the **About** section. The
privacy information shows the names of buttons in bold. At the end, **Send
Feedback** opens the feedback options, **Contact Plain Text Office** opens the
developer's website, and **Full Privacy Policy** opens the full privacy policy
there.

<!-- Verified from: platform/ios/bash-practice/Views/PrivacyView.swift [PrivacyView] -->
<!-- Verified from: platform/ios/bash-practice/Views/FeedbackView.swift [FeedbackView] -->

## Settings and Preferences

Not Applicable.
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt, platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeViewModel.kt -->

## Importing and Exporting

Not Applicable.
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt, platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/stats/StatsScreen.kt -->

## Commands and Shortcuts

The app has no keyboard shortcuts. These on-screen controls perform its main
actions.

| Control | Where | What it does |
| --- | --- | --- |
| **Learn**, **Practice**, **Progress**, **Docs** | Bottom bar or side rail | Switch between the main screens |
| **More options** (three dots) | Each tab, top right | Opens **Privacy** and **Send feedback** |
| Search field | **Learn** | Filters commands by name, other spelling, or description |
| **Copy** | Command detail | Copies the syntax or an example to the clipboard |
| **Mark as Learned** / **Learned** | Command detail | Marks or unmarks the command as learned |
| **Practice Terminal** | **Practice** | Looks up the recorded output of a command or guide example |
| **Start Quiz** | **Practice** | Starts a quiz with the chosen options |
| **Check** | Quiz, **Type the Command** | Checks your typed answer |
| **Next Question** / **See Results** | Quiz | Moves to the next question or the results |
| **Close** | Quiz, top left | Leaves the quiz |
| **Reset All Progress** | **Progress** | Clears learned commands and quiz history after confirmation |
| **Send by email** | **Send feedback** | Opens a feedback draft in your email app |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/home/HomeScreen.kt [HomeTab, HomeMenu] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/learn/LearnScreen.kt [SearchField] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/ui/Components.kt [CodeBlock] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt [LearnedButton] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [Start Quiz] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [TypedInput, navigationIcon, bottomBar] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/stats/StatsScreen.kt [Reset All Progress] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackScreen.kt [Send by email] -->

## Your Data Files

The app keeps its records inside its own storage on your device. You do not
open or edit these records by hand, and the app does not show their location.

| Data | Where it is stored | Can you edit it? |
| --- | --- | --- |
| Command library | Included with the app | No |
| Learned commands and quiz answers for each command | The app's private storage on your device; exact location Unknown. | No; change it through the app |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/di/AppModule.kt [database] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [CommandProgress] -->

To remove your records, use **Reset All Progress**, clear the app's storage
in Android Settings, or uninstall the app. Device backups may keep earlier
copies. The app has no user-visible log files.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_removing_body] -->
<!-- Verified from: platform/android/app/src/main/AndroidManifest.xml [android:allowBackup] -->

On iOS, the app saves learned commands and quiz answers in `progress.json` in
its Application Support folder, which iCloud and computer backups of the device
include. If that file cannot be read when the app opens, the app renames it
`progress.corrupt.json`, replacing any earlier copy, starts with empty progress,
and shows **Saved progress was reset** once. **Reset All Progress** also
deletes `progress.corrupt.json`, and deleting the app removes both files.

<!-- Verified from: platform/ios/bash-practice/Progress/ProgressFile.swift [load, corruptCopy, fileURL] -->
<!-- Verified from: platform/ios/bash-practice/BashPracticeApp.swift [AppContent] -->

## Troubleshooting

| Symptom | Likely Cause | Resolution |
| --- | --- | --- |
| **Start Quiz** is unavailable. | The chosen **Practice** selection has no commands, such as **Needs Review** before you have missed any questions. | Choose **All Commands**, **Not Yet Learned**, or a category. |
| A quiz has fewer questions than you chose. | The selection has fewer commands than the **Questions** value. | Choose a larger selection to get more questions. |
| A typed answer that looks right is marked wrong. | Typed answers are case-sensitive, or the keyboard changed a character. | Type the command exactly as bash expects it, usually in lowercase. |
| **Couldn't update progress** appears. | The learned status could not be saved. | Tap **OK** and try again. Your progress was not changed. |
| **Couldn't save your answer** appears during a quiz. | The answer could not be recorded. | Tap **OK** and continue. That question's result was not recorded. |
| **Couldn't reset progress** appears. | The reset could not be saved. | Tap **OK** and try again. Your progress was not changed. |
| **Reset All Progress** is unavailable. | There is no progress to clear. | No action is needed. |
| **No email app was found. Use the contact page instead.** | No app on the device can open the feedback email. | Tap **Use the contact page instead**, or install an email app. |
| **No app was found to open the link.** | No browser can open the developer's website. | Install or enable a web browser, then try again. |
| On iOS, **Saved progress was reset** appears when the app opens. | The saved progress file could not be read, so the app kept it as `progress.corrupt.json` and started with empty progress. | Tap **OK**. Learned commands and quiz answers you add from now on are saved as usual. |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/practice/PracticeScreen.kt [canStart, practice_nothing_to_review] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Quiz.kt [QuizBuilder.makeQuestions] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [Command.matches] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/detail/CommandDetailScreen.kt [SaveFailedDialog] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/quiz/QuizScreen.kt [SaveFailedDialog] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/stats/StatsScreen.kt [SaveFailedDialog, canReset] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackScreen.kt [FeedbackError] -->
<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [feedback_no_email_app, open_link_failed] -->
<!-- Verified from: platform/ios/bash-practice/BashPracticeApp.swift [AppContent] -->
<!-- Verified from: platform/ios/bash-practice/Progress/ProgressFile.swift [load] -->

## FAQ

### Does the app run bash commands?

No. The app does not run bash commands or connect to a shell or server. Try
the examples in a terminal on Linux, macOS, or another system with bash.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_device_body] -->

### Do I need an internet connection?

No. The command library is included with the app, and answers are checked on the
device. **Contact Plain Text Office**, **Use the contact page instead**, and
**Full Privacy Policy** open your browser. **Send by email** opens your email
app.

<!-- Verified from: platform/android/app/src/main/AndroidManifest.xml [no INTERNET permission] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/feature/feedback/FeedbackIntents.kt [openContactPage, openFeedbackEmail] -->

### Does capitalization matter in typed answers?

Yes. Bash treats `ls` and `LS` as different names, and so does the quiz.
Spaces before and after your answer are ignored.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [Command.matches] -->

### What is the difference between a builtin, a program, and an operator?

A shell builtin, such as `cd`, is part of bash itself. A program, such as
`grep`, is a separate file that bash finds and runs. An operator, such as `|`
or `>>`, is not a command at all: it tells bash how to connect commands or
where to send their output. The detail screen shows which kind each entry is.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [CommandKind] -->

### How does a command get on the Needs Review list?

A command appears there after you miss it at least once and your correct
answers for it fall below 70%. It leaves the list when your accuracy for it
reaches 70% or more.

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [needsReview] -->

### Does the app collect analytics or require an account?

No. This version contains no developer-run analytics, advertising, or account
service.

<!-- Verified from: platform/android/app/src/main/res/values/strings.xml [privacy_services_body] -->

## Glossary

| Term | Meaning |
| --- | --- |
| Accuracy | The share of your quiz answers that were correct. |
| Also written as | Another spelling bash accepts for the same command, such as `.` for `source`. |
| Learned | A command you marked with **Mark as Learned**. |
| Needs Review | Commands you missed at least once and answer correctly less than 70% of the time. |
| Operator | Symbols such as `\|`, `>`, or `&&` that join commands or redirect their input and output. |
| Program | A command that is a separate file on the system, such as `grep`. |
| Redirection | Sending a command's input or output to or from a file instead of the screen. |
| Shell builtin | A command that is part of bash itself, such as `cd`. |
| Syntax | The pattern for running a command, with its common options. |

<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/Command.kt [CommandKind, Command] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/domain/CommandLibrary.kt [REDIRECTION entries] -->
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/bashpractice/data/CommandProgress.kt [accuracy, needsReview] -->
