# Twitter X Unfollow Tool

<img width="992" height="655" alt="twitter-unfollower-tool" src="https://github.com/user-attachments/assets/2671c935-df7d-4baa-9b89-d2efcb069337" />


A **completely offline** tool to find who doesn’t follow you back on Twitter X.

When you reach around 5K followers and following, it becomes quite difficult
to manually revisit and unfollow those who don’t follow back.
It’s time-consuming and error-prone, hence the need for this tool.

But unlike GitHub, Twitter X is strict about API usage, hence the need for this workaround.
The only downside is that changes are not reflected instantly, the actual
count of users not following back is based on the **archive** you’re using.
Requesting a new archive isn’t instant either, as Twitter X takes time to generate it.

---

## Features

* ✅ **100% Offline** – Runs entirely in your browser
* ✅ **Privacy First** – No uploads, no servers, no tracking
* ✅ **No Login Required** – Uses your Twitter archive data
* ✅ **Clickable Links** – Direct links to profiles
* ✅ **Copy URLs** – One-click copy
* ✅ **Paginated Results** – Browse large lists in pages of 250
* ✅ **Batch Opening** – Open visible results in 25-profile batches
* ✅ **Opened Batch Markers** – Locally remembers which batches you opened
* ✅ **Fast** – Handles up to 50K followers smoothly *(expected but not yet tested)*

---

## How to Use

### Step 1: Request Your Twitter Archive

1. Go to **Twitter → Settings**
2. Navigate to: **Your Account → Download an archive of your data**
3. Wait for Twitter to prepare it (typically 12–48 hours)
4. Download the ZIP file once it’s ready

---

### Step 2: Extract the Archive

Unzip the downloaded file and locate the following files:

```
data/follower.js
data/following.js
```

---

### Step 3: Run the Tool

#### **Option A: Local Use (Recommended)**

1. Download `unfollowers.html` from this repository
2. **Open Chrome where you’re logged into Twitter/X** *(important!)*
3. **Double-click** `unfollowers.html` or drag it into Chrome
4. Upload both `follower.js` and `following.js`
5. Click **Analyze**
6. Click usernames to open profiles in a new tab from the same browser session
   (That’s why you must open the tool in the same Chrome profile where you’re logged in!)

---

### Step 4: View Results

You’ll see a list of accounts you follow who don’t follow you back, displayed as:

* **User IDs** (Twitter no longer includes handles in archives)
* **Clickable profile links**
* **Copy URL** buttons for convenience
* **Pagination** with 250 results per page for smoother browsing

> **Note:** Results show `User ID: 1234567890` instead of `@username` because Twitter archives only contain account IDs.
> The links still work perfectly!

---

## Batch Workflow

The main workflow is to open profiles in manageable batches of 25.

Each results page shows up to 250 accounts and is split into batch buttons:

```text
1-25, 26-50, 51-75, ... 226-250
```

Click a batch button to open those profiles in new tabs, in the same order shown in the table.

### Opened Batch Markers

After a batch is opened, its button is marked with a checkmark.

Opened batch markers are stored locally in your browser using the account IDs
in that exact batch. Nothing is uploaded, synced, or shared.

### Row-Level Visited Markers

When a batch opens, Chrome may automatically mark the matching profile links as visited.

That means individual rows can change color using the browser’s native visited-link behavior.
This is useful for checking which profiles were already opened.

### Manual Fallback

The table is still available for one-by-one review.

You can manually click an individual profile link or use **Copy URL** if a batch did not
open fully, if Chrome blocked tabs, or if you only want to inspect one account.

### Recommended Pacing

Do not abuse batch opening.

My recommendation is to open up to **8 batches** across a 24-hour period, staggered with
breaks between sessions. Since each batch contains 25 profiles, 8 batches is 200 unfollows
per day within X rules.

A good rhythm is to open **2 batches** at a time, manually unfollow from the opened X tabs,
then wait a large gap in minutes before repeating.

### Browser Pop-Up Permission

The first time you use **Open batch** in Chrome, Chrome may block the 25 profile tabs
and show a pop-up warning near the address bar.

Allow pop-ups for the local `unfollowers.html` file so batch opening can work. Other
browsers may show a similar pop-up/tab permission prompt, but Chrome is the recommended
browser for this workflow.

> **Important:**
>
> * Twitter detects bulk unfollow actions. To stay safe,
>   unfollow slowly, around **25 users at a time**, then pause before continuing.
> * Opening **too many profile tabs** at once also counts as activity.
>   If pages stop loading or only show the **X icon**, it means you've
>   hit a temporary rate limit, wait a bit before continuing.
>   I noticed after opening the first 25 to unfollow, I will have this limit,
>   so I'll wait several minutes then just reload them, but I'm not closing the
>   entire Chrome.
> * We can also use the mobile app: simply load the tabs on Web, say, still per 25,
>   then once we have the handle of each profile, search it in the mobile app.
>   This way, we do the actual unfollow in the mobile app, and we simply close
>   the 25 tabs and start a new batch, and we don't hit the Web page limit.
> * Since this tool uses **static archive data**, you might sometimes open
>   a profile that now follows you back. That's perfectly normal,
>   it just means the user started following you **after your archive was generated**.

---

## 🧑‍💻 Developer Mode

If you’d like to modify or contribute to the project, no setup is required —
not even Node.js. Just edit the **HTML**, **CSS**, and **JavaScript**, then reload the file to see your changes!

---

## 📊 Performance

| Followers | Processing Time | Status     |
| --------- | --------------- | ---------- |
| < 10K     | < 2 seconds     | ✅ Instant  |
| 10K–50K   | 5–15 seconds    | ✅ Fast     |
| 50K–75K   | 15–30 seconds   | ⚠️ Slower  |
| 75K+      | 30+ seconds     | ⚠️ May lag |

*Tested up to ~8K followers/following on personal data.*

---

## 🔒 Privacy & Security

* **Completely Offline** – Works without an internet connection
* **No Data Sharing** – Everything stays in your browser
* **No Analytics or Tracking**
* **Open Source** – You can inspect or modify the code freely

---

## 🛠️ Technical Details

* Pure **HTML**, **CSS**, and **JavaScript**
* No dependencies or frameworks
* Uses the **FileReader API** for local file processing
* Renders large result sets in pages of 250 rows
* 100% client-side execution

---

## What You’ll See

The tool displays:

* **Total Stats** – Following count, follower count, and mutuals
* **Not Following Back** – List of User IDs for accounts that don’t follow you back
* **Pagination** – Previous/Next controls with a visible result range
* Each entry includes:

  * User ID (e.g., `User ID: 1234567890`)
  * A clickable profile link
  * A **Copy URL** button

---

## Contributing

Contributions are welcome!
Open an issue or submit a pull request to improve the project.

---

## 📄 License

**MIT License** – Use freely and modify as you wish.

---

## TODOs

* improve link-click tracking to better identify which users
  have already been unfollowed
