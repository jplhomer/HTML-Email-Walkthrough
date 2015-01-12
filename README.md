# HTML-Email-Walkthrough
A brief look at HTML email development.

## Explanation of HTML in email

*[tldr](#tldr)*

* Use email marketing services to avoid being treated as spam.
* Don't forget about text based emails. Emails are sent with a Multipart/Alternative MIME format meaning emails are sent as an HTML version and a text version to support email clients that only accept text based emails.
* Emails are rendered inside of an email client where the rendering feature set is none standard at best.

To effectively send large blast emails you'll need to have a properly set up email server. Something that takes into account firewalls, ISPs, sending frequencies, proper MIME types etc. Typically, you should just use an email service provider (ESP) like [MailChimp](http://mailchimp.com/) or [Campaign Monitor](https://www.campaignmonitor.com/). The advantages of using a third party service extends beyond saving time in setting up your own server. Most ESPs can provide analytics, spam filter testing, and may even share statistical data from their clients to help determine engagement patterns for your email lists.

When coding HTML emails it's important to note that you're not coding for the browser. You're coding for a wide array of email platforms that hold their own private set of features. Each email platform is more concerned with spam over rendering beautiful standard complaint HTML web pages. So while there are some consistencies, like using tables over DIVs, each client will have their own quarks and idiosyncrasies making testing an absolute necessity.

##Best Practices

* Create an email marketing plan - here are some references that go into more detail on how to do this: [Mail Chimp](http://mailchimp.com/resources/), [Campaign Monitor](https://www.campaignmonitor.com/guides/).
* Avoid common mistakes / spam filters
  * Get the _recipients permission_ to send them emails first, include an _unsubscribe_ link, include the _sender's physical address_, use a legit _from name_ and _email address_, balance text for images, avoid bad spamy writing (i.e. "FREE! BUY NOW!")
* Build your HTML emails using a frame work

When you're ready you should start with putting together a comprehensive email marketing plan. There are many resources available on how to do this so I won't go into detail here. You can avoid spam filters by including the basic [CAN-SPAM](http://www.ftc.gov/tips-advice/business-center/can-spam-act-compliance-guide-business) requirements. These requirements are actual laws so you should be familiar with them. Also, most ESPs won't let you send emails from their servers without this information. You'll also need to familiarize yourself with how spam filters work. Things like over using explanation marks, or vague subject lines are commonly known email mistakes to be avoided. Lesser known spam triggers are things like including large images in an email with less than a few characters of text. Or generating bad HTML code akin to something Microsoft Word would generate.

<a name="tldr"></a>Basing your HTML off of a framework such as [Zurb's INK](http://zurb.com/ink/), or [MailChimps email design patterns](http://templates.mailchimp.com/resources/email-design-patterns/) helps alleviate most of the HTML rendering issues, and will give

When coding your HTML bear in mind that you must _use tables_, and _inline CSS_. You should *avoid* *JavaScript, video, Flash, and animated GIFs*. Most CSS rules are supported, but you should check specific usage here: [MailChimp CSS Support](http://templates.mailchimp.com/resources/email-client-css-support/). Media queries are usable. However, since they cannot be set inline you should _add `!important`_ to each media query rule.

Once you've built your HTML email run it through a pre-flight check list like [Premailer](http://premailer.dialect.ca/) and test it in as many email platforms as possible. If you find display errors check your email source using your email platforms ability to "show original" or view "raw source."

