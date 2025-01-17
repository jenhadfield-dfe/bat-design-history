---
title: Sending users a weekly summary of notifications
description: We created a weekly summary email and a way for users to choose whether to receive it.
date: 2022-02-11
screenshots:
  items:
    - text: Email notification settings
tags:
  - notifications
---

{% from "email/macro.njk" import appEmail %}

Users can choose to receive individual email notifications, which are sent when:

- applications are received
- applications are received from other organisations
- there are 20 working days left before applications are automatically rejected
- applications are automatically rejected
- applications are withdrawn by the candidate
- applications are transferred to other organisations
- offers are accepted
- offers are declined

Research shows that some users will find it useful to receive a weekly summary of notifications.

This will be particularly helpful for users who do not process applications every day, but need an overview of the applications being processed.

## What we changed

We added a new option to the notification settings page, which lets users choose to receive a weekly summary of email notifications.

The email includes the date and time of the start and end of the period covered, plus a section for each type of notification which can be sent individually.

<!-- markdownlint-disable MD001 MD025 -->

{{ appEmail({
  subject: "Summary of notifications from 31 January 2022 to 7 February 2022 - manage teacher training applications",
  content: "

This is a summary of notifications from Monday 31 January 2022 at 9am to Monday 7 February 2022 at 9am.

# Received

- [Stacey Fluhler - German and Italian (0HZB)](https://manage-applications-beta.herokuapp.com/)
- [Eloise Blackwell - Mathematics (RMGE)](https://manage-applications-beta.herokuapp.com/)
- [Alex Roberts - Physical education (4TGG)](https://manage-applications-beta.herokuapp.com/)
- [Carol Stark - Drama and English (62NA)](https://manage-applications-beta.herokuapp.com/)
- [Janet Romanoff - Biology and Physics (PJCS)](https://manage-applications-beta.herokuapp.com/)
- [Janet Romanoff - Biology and Chemistry (JFID)](https://manage-applications-beta.herokuapp.com/)
- [Ayesha Leti-I’iga - Physical education (S1KK)](https://manage-applications-beta.herokuapp.com/)
- [Monica Octavius - Primary (5 to 11)](https://manage-applications-beta.herokuapp.com/)

# Received from another organisation

- [Barbara Rambeau - English (X1HT)](https://manage-applications-beta.herokuapp.com/)

# Less than 20 working days before automatic rejection

- [Frédéric Morel - French (F4RS) - 11 February 2022](https://manage-applications-beta.herokuapp.com/)
- [Faith Violetta - Primary (FG23) - 13 February 2022](https://manage-applications-beta.herokuapp.com/)
- [Renee Holmes - Design and Technology (NGU9) - 16 February 2022](https://manage-applications-beta.herokuapp.com/)
- [Umar Smith - German and Spanish (1GCX) - 16 February 2022](https://manage-applications-beta.herokuapp.com/)
- [Morgane Peyronnet - Art and design (1NBJ) - 21 February 2022](https://manage-applications-beta.herokuapp.com/)
- [Renee Wickliffe - Biology and Chemistry (JFID) - 22 February 2022](https://manage-applications-beta.herokuapp.com/)
- [Kara Lynn Hogan - Humanities (Geography and History) (XYL3) - 28 February 2022](https://manage-applications-beta.herokuapp.com/)
- [Chitprem Sra - Biology and Chemistry (E0JO) - 2 March 2022](https://manage-applications-beta.herokuapp.com/)
- [Gaelle Hermet - Art and design (1NBJ) - 2 March 2022](https://manage-applications-beta.herokuapp.com/)

# Automatically rejected

- [Julia Stark - Mathematics (RMGE)](https://manage-applications-beta.herokuapp.com/)
- [Jennifer Maximoff - Biology and Chemistry (OKVX)](https://manage-applications-beta.herokuapp.com/)
- [Wanda Charles - Art and design (VAGD)](https://manage-applications-beta.herokuapp.com/)

# Withdrawn by candidate

- [Natasha Danvers - Primary (5 to 11) (D3QX)](https://manage-applications-beta.herokuapp.com/)
- [Monica Juárez - Physical education (4TGG)](https://manage-applications-beta.herokuapp.com/)

# Transferred to another organisation

- [Hela Morse - French and Spanish (ZCXG)](https://manage-applications-beta.herokuapp.com/)

# Offer accepted

- [Heather Morse - Primary with mathematics (4JTE)](https://manage-applications-beta.herokuapp.com/)
- [Wanda van Dyne - English (PP85)](https://manage-applications-beta.herokuapp.com/)
- [Heather Richards - Music (D59Q)](https://manage-applications-beta.herokuapp.com/)

# Offer declined

- [Kara Lynn Quill - French and German (132H)](https://manage-applications-beta.herokuapp.com/)

# Get help

Get help, report a problem or give feedback at [becomingateacher@digital.education.gov.uk](mailto:becomingateacher@digital.education.gov.uk).

You can change your email notification settings:

https://manage-applications-beta.herokuapp.com/account/notifications
  "
}) }}

## How it works

Like all other email notifications, the option to receive the weekly summary is turned on by default.

Users can choose to receive both the weekly summary and individual notifications.

Notifications do not appear if they’ve been superseded by a further change. For example, if an application was received and withdrawn within the week covered by the email then only the withdrawal is included.

All applications with less than 20 working days are listed, even if they’ve been mentioned in a previous email.

The heading for each category of notifications only appears if there’s at least one application in that category. The weekly summary is only sent if it contains at least one notification.

## Further considerations

We could consider:

- avoiding hiding URLs within the email
- adding more notifications
- reminding users to make decisions about applications 5 working days before they’re automatically rejected

### Avoiding hiding URLs within the email

The [GOV.UK guidance on sending emails](https://www.gov.uk/service-manual/design/sending-emails-and-text-messages) says that we should “spell out any web addresses (URLs) in full to show the user where links are going”. This is intended to help protect users from phishing.

If we spell out URLs in the current design then it will be impossible to tell the links apart, other than by referring to the text alongside them. This could be a particular problem for screen reader users.

We could test that design with users or try other designs which would let us avoid hiding URLs in emails. For example we could create a new page within the service which summarises the previous week’s email notifications.

We could explore this alongside the [notifications feature](/manage-teacher-training-applications/notifications/) which was designed but is not used in the live service.

### Adding more notifications to the weekly summary

We could also consider including notifications in the email which are not available individually.

For example, we could include applications where an offer has been made and the provider is waiting for the candidate’s decision.

### Reminding users to make decisions about applications 5 working days before they’re automatically rejected

Users currently get an email reminder that there are 20 working days before an application will be automatically rejected. But the application list instead highlights applications when there are 5 working days left.

We want to consider sending an email 5 working days before an application will be automatically rejected. This could be instead of the email 20 working days before, or in addition to it.
