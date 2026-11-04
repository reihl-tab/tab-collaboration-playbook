# Synthetic message templates

Templates are drafts, not permission to send. Replace uppercase placeholders
privately, verify recipient/authority and obtain wording approval where required.
No real addresses, signatures, certificates or account records belong here.

## Introduction (send separately in each direction)

> Purpose: establish the agreed collaboration channel for PROJECT.
> I am ROLE, using the mailbox previously confirmed in our trusted conversation.
> This is a harmless signed introduction. Please verify the signature and mailbox
> binding and acknowledge with CHALLENGE. Do not send secrets or private keys.

Tasking messages are signed and numbered from one shared `td` sequence; see
[tasking messages](en/workflow.md#tasking-messages).

## GO (task)

> MAINTAINER report id: tdNNN
> Answers: MESSAGE_OR_TD_ID_OR_NONE
> GO for ISSUE_REFERENCE. Accountable owner: ROLE
> Outcome: one bounded documentation change.
> Scope: REPOSITORY and ISSUE_REFERENCE only.
> Allowed: research public sources, fork, branch, PR and synthetic tests.
> Excluded: secrets, personal data, direct main writes, settings, live services,
> money, external messages or calls.
> Acceptance: design note first if the issue needs the design gate, exact-head
> independent review and green CI. New work outside this scope needs a new GO.
> Please reply accepted/blocked with output, dependencies and next checkpoint.

## Acknowledgment

> Tab report id: tdNNN
> Answers: MESSAGE_OR_TD_ID
> Scope: ISSUE_REFERENCE (per GO tdNNN)
> Accepted OUTCOME within SCOPE. Next artifact: ARTIFACT.
> Blockers: NONE_OR_SPECIFIC_GAP. Next update: AGREED_TIME_AND_TIMEZONE.
> I will stop rather than widen scope if an excluded effect becomes necessary.

## Completion / blocker

> Tab report id: tdNNN
> Answers: MESSAGE_OR_TD_ID
> Scope: ISSUE_REFERENCE (per GO tdNNN)
> Status: VERIFIED_OR_BLOCKED.
> Evidence: ACTUAL_ISSUE_OR_PR_LINK and REVIEWED_SHA.
> Checks: ACTUALLY_RUN_CHECKS. Not verified: REMAINING_GAPS.
> Next owner/action: ROLE_AND_ONE_SPECIFIC_STEP.

## DONE

> MAINTAINER report id: tdNNN
> Answers: TD_ID_OF_THE_COMPLETION_REPORT
> DONE for ISSUE_REFERENCE (per GO tdNNN). Merged MERGE_COMMIT after
> independent review of REVIEWED_SHA. This closes the scope.

## תבנית קצרה בעברית

> MAINTAINER report id: tdNNN. Answers: MESSAGE_OR_TD_ID_OR_NONE.
> GO עבור ISSUE_REFERENCE. אחראי: ROLE. תוצר: OUTCOME.
> תחום: REPOSITORY ו-ISSUE_REFERENCE בלבד.
> מותר: מחקר במקורות ציבוריים, fork, ענף, PR ובדיקות סינתטיות.
> מוחרג: סודות, מידע אישי, כתיבה ישירה ל-main, הגדרות, שירותים חיים, כסף,
> הודעות חיצוניות או שיחות.
> קבלה: מסמך תכנון קודם אם ה-issue דורש שער תכנון, סקירה עצמאית על SHA
> מדויק ו-CI ירוק. עבודה חדשה מחוץ לתחום דורשת GO חדש.
> נא להשיב בדיווח שמתחיל ב-`Tab report id: tdNNN` ו-`Answers: tdNNN`:
> התקבל או חסום, עם תוצר צפוי, תלות ומועד עדכון.

## Call request (private use only, owner approval required)

> Order ID: UNIQUE_REFERENCE. Owner approval: PRIVATE_APPROVAL_REFERENCE.
> Caller: Tab, identified honestly as the owner's AI assistant.
> Recipient and full number: PRIVATE_VERIFIED_RECIPIENT_AND_NUMBER.
> Purpose: APPROVED_PURPOSE. Language: LANGUAGE.
> Exact approved opening: APPROVED_TEXT.
> Exact approved questions and closing: APPROVED_TEXT.
> Permitted disclosures and response branches: EXPLICIT_SCOPE_OR_NONE.
> Cost/plan terms checked: VERIFIED_CURRENT_TERMS. Approved maximum: LIMIT.
> Dial window: START_TO_END, DATE_AND_IANA_TIMEZONE.
> Attempts: MAXIMUM. Retry interval: INTERVAL. No duplicate live attempts.
> Voicemail/menu handling and DTMF: EXPLICIT_APPROVED_RULE_OR_STOP.
> Silence-start trigger: APPROVED_TRIGGER_OR_WAIT_FOR_HUMAN.
> Recording: OFF unless separately authorized and lawful.
> Stop on cancellation, wrong recipient, refusal, unclear menu, hearing failure,
> unexpected question or exhausted limits. No unapproved transfer, fallback,
> message, disclosure or commitment. Recheck authorized changes before dialing.
> Acknowledge scope before acting. Report after each attempt: actual timestamp,
> connected/not connected, known duration, delivered words, answers, unresolved
> items, deviations and evidence limits. Do not call acknowledgment completion.
> These are instructions, not technical guarantees of speech or keypad behavior.

## תבנית שיחה (פרטי בלבד)

> מזהה: UNIQUE_REFERENCE. אישור בעלים: PRIVATE_APPROVAL_REFERENCE.
> מתקשר: Tab, מזדהה ביושר כעוזר ה-AI של הבעלים.
> נמען ומספר מלא: PRIVATE_RECIPIENT.
> מטרה ושפה: APPROVED_SCOPE. פתיח, שאלות וסיום מדויקים: APPROVED_TEXT.
> מידע ותגובות מותרים: EXPLICIT_SCOPE_OR_NONE. עלות עדכנית שנבדקה ותקרה: LIMIT.
> חלון חיוג, תאריך ואזור זמן: WINDOW. ניסיונות ומרווח: ATTEMPTS_AND_INTERVAL.
> תא קולי, תפריט, מקשים והתחלה אחרי שקט: EXPLICIT_RULE_OR_STOP.
> הקלטה כבויה אלא אם אושרה בנפרד ומותרת. אין ניסיון כפול או חלופה לא מאושרת.
> עוצרים בביטול, נמען שגוי, סירוב, תפריט לא ברור, כשל שמיעה, שאלה לא צפויה
> או מיצוי המגבלות. אין העברה, הודעה, גילוי מידע או התחייבות שלא אושרו.
> לפני חיוג בודקים ביטול ושינויים מורשים. מאשרים קבלה לפני ביצוע ומדווחים
> אחרי כל ניסיון זמן, חיבור, משך ידוע, מה נמסר, תשובות, חסמים וחריגות.
> קבלה אינה השלמה; ההוראות אינן הבטחת אכיפה טכנית של דיבור או מקשים.
