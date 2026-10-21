# CP Bridge

Turn an Android phone into a **wireless‑CarPlay "car"** so it can show **Android Auto** on your car's
built‑in screen — Maps, media, the Assistant, with car touch, audio, microphone and the voice button.
(It can also mirror the phone's screen instead.) No root required.

*(The app installs on your phone as "CarPlay Bridge".)*

> **Supported cars — read this first.** This is confirmed working only on the **BMW i8 (NBT Evo head unit)**
> over wireless CarPlay. Other BMW head units and other brands are **unverified** — they may or may not
> work. There are no refunds for an unsupported car, so use the free trial to test it in *your* car before
> buying a license.

---

## What you need

- An Android phone running **Android 12 or newer**.
- A car with **wireless Apple CarPlay**.
- The **Google Android Auto** app installed on the phone (from Play) — for Android Auto mode.
- A per‑car **license** to unlock **Android Auto** (see *Get a license* below). The license also carries the
  head‑unit certificate Android Auto needs, so it's installed for you on Activate.
- **Mirroring is free for the first 7 days** — enough to confirm the app works in your car before you buy.

---

## Install

1. Download the latest **`.apk`** from the [Releases](../../releases) page.
2. Open it on the phone and allow installing from unknown sources when prompted.
3. Install and open the app. Grant **Bluetooth** (and, on Android 13+, **notifications**) when asked.

The app is signed with the developer's own key, so Android will note it's from an "unknown source" — that's
normal for a sideloaded app. There are **no automatic updates**; check the Releases page for newer builds.

You may see a second launcher icon called **"Test Player"** — that's a diagnostic tool, ignore it.

---

## One‑time phone setup

### 1. Turn on Android Auto's "head unit server"

Android Auto only streams to a head unit after you enable its developer server:

1. Open **Android Auto settings** (the app's *Get Android Auto ready* card can open it for you).
2. Scroll to the bottom to **Version** and tap it **10 times** until it says *Developer mode enabled*.
3. Open the **⋮ menu** (top‑right) → **Start head unit server**.

You must repeat step 3 **after every phone restart** — the server does not survive a reboot or an Android
Auto update.

### 2. (Only some phones) Bluetooth address

The app normally detects your phone's Bluetooth address automatically. A few phones (some Honor/Samsung)
hide it — if the **Bluetooth address** card asks you to enter it, find it under
**Settings › About phone › Status › Bluetooth address**, type it in, and tap **Save**.

---

## Pair with your car (first time only)

**Start the pairing from the car, not from the phone's Bluetooth list.** If the phone initiates it, the car
treats it as an ordinary phone (music/calls only) and CarPlay never starts.

1. **On the phone:** press **Start**. Tap **Allow** on the two Bluetooth pop‑ups (the app briefly turns
   Bluetooth off and back on so CarPlay is offered correctly). The phone becomes visible for ~60 seconds.
2. **On the car:** add a new device / phone and choose **Apple CarPlay**. The car finds your phone.
3. **On the phone:** confirm the pairing and that the passkey matches on both screens.
4. When the car hands over its Wi‑Fi, a **"Connect to …?"** dialog appears on the phone — tap **Connect**
   within ~25 seconds.

After this, the car reconnects by itself next time — you just press **Start**.

---

## Free trial (mirroring)

When you first install, **mirroring works free for 7 days** with no license. That's the best way to check
compatibility: mirroring uses the exact same connection as Android Auto, so if mirroring comes up on your
car, the paid Android Auto will work too. **Try the free part first** — there are no refunds for a car that
turns out not to be supported.

After 7 days, mirroring also needs a license. **Android Auto always needs a license** (it is not part of
the trial).

## Get a license

A license unlocks **Android Auto** (and keeps mirroring after the trial). It is tied to **this phone and
your car's serial** — it won't work on another phone or another car.

1. **Connect to your car once** (steps above) so the app learns your car's serial.
2. In the **License** card, tap **Request license by email**. Your email app opens, already addressed to
   **carplaybridge@proton.me** with your enrollment code (`CPBE1-…`) in the message — just send it.
   *(No email app? Tap **Copy enrollment code** and send the code to carplaybridge@proton.me yourself.)*
3. You'll receive payment details and then your license — a longer code starting with `CPB2-…`.
4. In the app's **License** card, paste it in and tap **Activate**. If the card already says *Licensed*,
   tap **Apply a different license** first, then paste and Activate.

The Android Auto head‑unit certificate is carried in the license and installs automatically on Activate —
it's stored only on your phone (its private key in the phone's secure hardware, never exported).

---

## Drive: start a session

1. Make sure **Wi‑Fi is on** (CarPlay carries the screen and sound over the car's Wi‑Fi).
2. At the top, pick the mode: **Mirror phone** (free for the trial) or **Android Auto** (needs a license).
   Mirror is the default.
3. Press **Start**. The header shows progress: **Bluetooth → Car Wi‑Fi → CarPlay → Playing**. Tap
   **Connect** on the Wi‑Fi dialog when it appears.
4. Your phone's screen — or Android Auto — comes up on the car screen.
5. To stop, **long‑press Stop** (a quick tap only shows "Hold to stop", so you can't end a drive by accident).

---

## Auto‑start in the car (optional)

If you'd rather not press **Start** every time, turn on **Auto‑start in the car** (Android 13+). The app
will then start a session by itself when your car connects over Bluetooth.

- **One‑time setup:** pair and connect to your car once, then switch **Auto‑start in the car** on and
  confirm your car in the system dialog that appears.
- It's a **best‑effort, no‑fuss attempt**: on many phones it just comes up. If nothing appears on the car
  screen, simply press **Start** — the manual way always works and is still there as a fallback.
- On some phones (often Honor and similar) the car doesn't always recognise CarPlay on the first try; there
  the manual **Start** remains the reliable path.
- **Battery settings (important on Honor/Huawei/Xiaomi):** when you turn Auto‑start on, the app asks to be
  exempt from battery optimisation — tap **Allow**. These phones also have an extra "protected apps" /
  "app launch" manager that can freeze the app in the background (symptom: you have to open the app for the
  car to finish connecting). Set the app to **Allow background activity / Launch manually / no restrictions**
  (Honor/Huawei: *Settings › Battery › App launch › CarPlay Bridge › Manage manually*, enable all three;
  Xiaomi: *Autostart* + *No restrictions*).

## Options

- **Phone panel** (Android Auto mode): show your phone's own screen in a side strip next to Android Auto
  (e.g. a navigation app beside Maps). Off by default; needs screen‑capture permission and the touch service.
- **Mirror mode**: show the phone's screen on the car instead of Android Auto. Needs the accessibility
  **"CarPlay Bridge car touch"** service (enable it in Android Settings; the app's button opens the page).

---

## Troubleshooting

- **Car says "Waiting for Android Auto…"** — the head‑unit server isn't running. Android Auto → ⋮ →
  *Start head unit server*, then press Start.
- **Nothing happens after pairing** — Wi‑Fi may be off, or you missed the **Connect** dialog. Press Start
  again and tap **Connect** when it appears.
- **"Not licensed for this car"** — activate a license for this car. A license is tied to this phone + car.
- **CarPlay connects but Android Auto doesn't appear** — re‑activate your license (the head‑unit certificate
  comes with it). If you cleared app data or reinstalled, request a fresh license for the new enrollment code.
- **Screen stutters** — leave Bluetooth discoverability off during a drive (the app already does this once
  paired).

---

## Privacy & security

- Your license and the head‑unit key live **only on your phone** (the key in secure hardware, never on
  disk, never exported).
- No account, no sign‑in, no tracking. The app talks to your car and — for Android Auto — to the Android
  Auto app over the phone's own internal network.
- **Root is not required.**
