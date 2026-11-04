# Hands-on: Text Processing with Text Lab

In this part, you will compare two transcripts, translate the German portion of an interview, and summarize the original bilingual transcript.

**Before you start:** Keep your Text Lab session open and have the results from [Part 1, exercise A2](EXERCISES_part1.md#a2-two-languages-in-one-recording) ready. You will use the transcript generated from the full `mixed_de_en.wav` recording and the separate German transcript from the batch run. If you saved a ZIP of your results, unzip it first.

---

## A. Chat: Find the major transcription issues

**Files:** The plain-text transcript generated from the full bilingual recording and the [reference script](audio/transcripts/mixed_de_en_script.txt).

1. Open **Chat**. Under **Upload Context**, attach both `.txt` files. If needed, rename your generated transcript to `mixed_de_en_generated.txt` so you can distinguish it from the script.
2. Send this prompt, adjusting the generated filename if needed:

   > Compare `mixed_de_en_generated.txt` with `mixed_de_en_script.txt`. Use the script as the reference. Identify the most important discrepancies. For each one, show a short excerpt from both files and explain what changed. Pay particular attention to the switch from English to German and to missing or changed information.

3. Verify two of Chat's findings by opening both files and checking the quoted passages.

**Look for:** Does Chat distinguish a change of language from a change of meaning? Did it miss any issue you noticed in Part 1?

---

## B. Translate: From German to English

**Text:** The German transcript generated from the split recording in the Part 1 batch run.

1. Open **Translate** and select the **Text** tab.
2. Keep the default translation backend. Set the source language to **German** and the target language to **English**.
3. Paste the German transcript into the left panel. Click **Load model**, wait until it is ready, then click **Translate**.
4. Compare the English result with the German transcript and the corresponding passage in the reference script.

**Look for:** Does the translation preserve how many people were interviewed and why students came to the library in the evening? If a detail changed, did the change first appear in the German transcript or in the translation?

---

## C. Meeting Notes Generator: Summarize the bilingual transcript

**Text:** The same unedited bilingual transcript you uploaded to Chat in exercise A.

1. Open **Meeting Notes Generator → From Transcript**.
2. Choose **Upload text file** and select your generated `.txt` file. You can also choose **Paste text** and paste the full transcript, including both language sections.
3. Select **General Summary** and choose a summary language you can review. Click **Generate Summary**.
4. Read the **Summary**, then open **Sources** and check which transcript lines support two of its claims.

**Look for:** Does the summary cover both the interview setup and the research findings? Did it carry over any transcription issue you found in exercise A?

> **Starting from audio or a transcript.** You can upload a recording directly in **From Audio**. Text Lab transcribes it and generates the summary in one run. Here we used **From Transcript** to show how you can reuse the same text for different research questions. You might want to check how accurately an interview was transcribed or summarize what the interviewee said. If you already have a transcript you want to use, **From Transcript** summarizes that text directly. [Meeting Notes Generator guide](https://text-lab.dsl.unibe.ch/meeting_notes/#choosing-what-to-start-from)

---

## Before you leave

- Save any results you want to keep before closing your Text Lab session.
- Text Lab guides for [Chat](https://text-lab.dsl.unibe.ch/chat/), [Translate](https://text-lab.dsl.unibe.ch/translate/) and the [Meeting Notes Generator](https://text-lab.dsl.unibe.ch/meeting_notes/).
