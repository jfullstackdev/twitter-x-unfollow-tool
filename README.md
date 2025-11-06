# Twitter X Unfollower Tool

<img width="992" height="655" alt="twitter-unfollower-tool" src="https://github.com/user-attachments/assets/a44e3ccb-04b5-4f0d-944c-0debc2e08ce3" />

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
2. **Open Chrome where you’re logged into Twitter** *(important!)*
3. **Double-click** `unfollowers.html` or drag it into Chrome
4. Upload both `follower.js` and `following.js`
5. Click **Analyze**
6. Click usernames to open profiles — they’ll open in the same browser session
   (That’s why you must open it in the same Chrome profile where you’re logged in!)

---

### Step 4: View Results

You’ll see a list of accounts you follow who don’t follow you back, displayed as:

* **User IDs** (Twitter no longer includes handles in archives)
* **Clickable profile links**
* **Copy URL** buttons for convenience

> **Note:** Results show `User ID: 1234567890` instead of `@username` because Twitter archives only contain account IDs.
> The links still work perfectly!

> **Important:** Twitter may detect bulk unfollow actions.
  To stay safe, unfollow slowly — around **25 users at a time**, then pause before continuing.

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
* 100% client-side execution

---

## What You’ll See

The tool displays:

* **Total Stats** – Following count, follower count, and mutuals
* **Not Following Back** – List of User IDs for accounts that don’t follow you back
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
