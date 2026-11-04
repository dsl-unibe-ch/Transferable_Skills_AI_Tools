# Hands-on: Speech-to-Text and OCR with Text Lab

Text Lab runs on UBELIX, the University of Bern's computing cluster. You don't need any code.
Your files never leave the university, and they are deleted when your session ends.

**Download the sample files first:** [all_sample_files.zip](https://github.com/dsl-unibe-ch/Transferable_Skills_AI_Tools/raw/main/materials/all_sample_files.zip) (unzip it), or individual files from [`audio/`](audio/) and [`documents/`](documents/).

---

## 0. Start Text Lab

1. Open <https://ondemand.hpc.unibe.ch>. You must be on the university network or VPN.
2. Go to **My Interactive Sessions → Data Science Lab Services → Text Lab**.
3. Fill in the form (see the screenshot in the course README), then click **Launch**:

   | Setting | Today | Next time, on your own |
   |---|---|---|
   | Account | `teaching` | `gratis` |
   | Job Time (hours) | `6` | as needed |
   | SLURM Partition | `gpu` | `gpu` |
   | Quality of Service (QoS) | `job_teaching` | `job_gratis` |
   | GPU Type | `rtx4090` | `rtx4090` |
   | Number of GPU(s) requested | `1` | `1` |
   | Reservation | `DSL_AI_TOOLS` | *leave empty* |

4. Wait until the card turns green, then click **Connect to Text Lab**.

> ⚠️ **Using Text Lab after today?** The `teaching` account, the `job_teaching` QoS and the `DSL_AI_TOOLS` reservation **only work during this course**.
> Next time, switch to `gratis` and `job_gratis` and leave the reservation empty. Otherwise your job will not start.

---

## A. Speech-to-Text

### A1: Who said what?
**File:** `audio/interview_en.wav` (1 min 48 s, three people).

1. Open **Transcribe** and choose **Transcribe audio**. Upload the file.
2. Check the detected language. It should be **English**.
3. Tick **Set min speakers** and **Set max speakers**, and set both to **3**.
4. Click **Start Transcription**.
5. Play the result with the synchronized player.

**Look for:**
- Does it find three speakers, and does each keep the same label?
- At about 1:08, two people talk over each other. What happens to the labels there?
- How are **UBELIX** and **PaddleOCR** spelled?
- Download the **.zip** bundle. What would you each file in it for?

You can compare with the real script in `audio/transcripts/interview_en_script.txt`.

### A2: Two languages in one recording
**File:** `audio/mixed_de_en.wav` (1 min 9 s). It starts in English and continues in German.

1. Transcribe it as one file, keeping the detected language.
2. Compare the German part of the transcript with the real script in `audio/transcripts/mixed_de_en_script.txt`.
   Read every sentence: is it all still in German?

**The workaround:** Text Lab uses one language per file, so split the recording by language.
1. Choose **Batch transcribe (ZIP)** and upload `audio/mixed_split.zip`. It contains the same recording, cut into an English part and a German part.
2. Set the language to **Auto-detect**. Each file then gets its own language.
3. Click **Start Batch Transcription** and compare the two results.

> If you have a Swiss German recording, try the **Swiss German** language option. It uses a model fine-tuned for dialect.

---

## B. OCR: from a scan to structured text

**Files:** `documents/sample_paper_born_digital.pdf` and `documents/sample_paper_scan.pdf`. It is the same article twice.

1. Open **OCR**, upload the **born-digital** PDF and click **Parse document**. Note how long it takes.
2. Do the same with the **scan**. Why does it take longer?
   Compare the two results: which one gives you headings, a real table and the formula?
3. In the scan's results:
   - **Layout preview:** which colour marks the title, the table, the figure and the formula?
   - **Tables:** is Table 1 a real table? Download it as CSV and open it in Excel. Check the **header row** carefully.
   - **Figures:** was the chart cropped out?
   - **Document:** how was the formula exported?
4. Download the **Searchable PDF**, open it, and press **Ctrl+F** to search for `Tesseract`.
5. Open **Models used (for citation)**. This is what goes in your methods section.

**Bonus:** tick the option to describe figures and run the scan again. Is the description of Figure 1 *transcribed* from the page or *generated* by a model? Why does that matter when you quote it?

---

## C. Your own file

Try a real file from your work: a scan, a photo of a page, or a short recording (under 3 minutes for today).
Processing happens on UBELIX and the file is deleted when your session ends.
Still, only use material you are allowed to process.

---

## Before you leave

- **Stop your job:** in OnDemand, open **My Interactive Sessions** and click **Delete**. The GPUs are shared.
- Text Lab documentation: <https://text-lab.dsl.unibe.ch>
- Please fill in the Text Lab survey (2 min). The link is in the course README.
