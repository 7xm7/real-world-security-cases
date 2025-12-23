# A Real World Logic Flaw

**Category:** Business Logic  
**Context:** Mobile application  
**Disclosure:** Responsible  
**Application:** Company XYZ

---

## 1. Context

I was using an application from **Company XYZ** to book a paid service.

Nothing unusual. I paid, used the service, and everything seemed to work as expected.

But later that day, something caught my attention.

---

## 2. The small detail that raised a question

Out of curiosity, I went back into the app to check my booking.

At that moment, I wondered:  
**“How does the app know that this service has already been used?”**

That question stayed in my head.

- I didn’t try to hack anything.  
- I didn’t use any tools.  
- I didn’t intercept traffic.

I just observed.

---

## 3. What I tried

I changed the **time on my iPhone** to a moment *before* the service was scheduled.

When I reopened the app:
- the service appeared editable again
- I could reschedule it
- the app behaved as if the service had not yet happened

At that point, it became clear that something was wrong.

---

## 4. What was happening behind the scenes

The application was trusting **client-side time** to decide whether a service was still valid.

Because of that:
- changing the device time altered the application state
- the server accepted those changes
- a single purchase could be reused multiple times

No technical exploitation was needed.  
Just a broken assumption.

---

## 5. Why this is a real problem

This isn’t a “security bug” in the traditional sense.

It’s a **logic flaw**.

If one user can:
- reuse a paid service
- without paying again
- by changing a local setting

then the business logic is fragile.

On a larger scale, this can result in significant financial loss.

---

## 6. What I did next

I reported the issue responsibly to **Company XYZ**.

Some time later, I tested the same behavior again and the issue was no longer present, which suggests it was fixed.

---

## 7. What this taught me

This experience reinforced something important:

Many real world vulnerabilities are not found by:
- running scanners
- using advanced exploits
- brute forcing systems

They are found by:
- understanding how applications *think*
- questioning assumptions
- and paying attention to edge cases

---

## Final thoughts

This report intentionally:
- avoids naming the real application's name
- avoids step by step exploitation
- focuses on understanding, not abusing

The goal was to learn and show how logic flaws appear in real systems.

---

## Responsible disclosure

This behavior was observed through minimal testing only.

I did not exploit the issue beyond confirming it existed, and the goal was understanding, not abuse.

The issue was reported responsibly and appears to have been fixed.
