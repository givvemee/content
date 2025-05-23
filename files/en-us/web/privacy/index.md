---
title: Privacy on the web
slug: Web/Privacy
page-type: landing-page
sidebar: privacy
---

People use websites for several important tasks such as banking, shopping, entertainment, and paying their taxes. In doing so, they are required to share personal information with those sites. Users place a certain level of trust in the sites they share their data with. If that information fell into the wrong hands, it could be used to exploit users, for example by profiling them, targeting them with unwanted ads, or even stealing their identity or money.

Modern browsers already have a wealth of features to protect users' privacy on the web, but that's not enough. To create a trustworthy and privacy-respecting experience, developers need to educate their site users in good practices (and enforce them). Developers should also create sites that collect as little data from users as possible, use the data responsibly, and transport and store it securely.

In this article, we:

- Define privacy and important related terms.
- Examine browser features that automatically protect user privacy.
- Look at what developers can do to create privacy-respecting web content that minimizes the risk of users' personal information/data being obtained unexpectedly by third parties.

## Defining privacy terms and concepts

Before we look at the various privacy and security features available to use on the web, let's define some important terms.

### Privacy and its relationship with security

It is hard to talk about privacy without also talking about security — they are closely related, and you can't really create privacy-respecting websites without good security. Therefore, we shall define both.

- **Privacy** refers to the act of giving users the right to control how their data is collected, stored, and used, and not using it irresponsibly. For example, you should clearly communicate to your users what data you are collecting, who it will be shared with, and how it will be used. Users must be given a chance to consent to your terms of data usage, have access to all of their data that you are storing, and delete it if they no longer wish you to have it. You must also comply with your own terms: nothing erodes user trust like having their data used and shared in ways they never consented to. And this isn't just ethically wrong; it could be against the law. Many parts of the world now have legislation that protects consumer privacy rights (for example the EU's [GDPR](https://gdpr.eu/)).

- **Security** is the act of keeping private data and systems protected against unauthorized access. This includes both company (internal) data, and user and partner (external) data. It is no use having a robust privacy policy that makes your users trust you if your security is weak and malicious parties can steal their data anyway.

### Personal and private information

**Personal information** is any information that describes a user. Examples include:

- Postal address, email address, phone number, or other contact information
- Passport number, bank account, credit card, social security number, or other official identifiers
- Physical attributes such as height, gender expression, weight, hair color, or age
- Health information such as medical history, allergies, or ongoing conditions
- Usernames, when they can be linked to an individual
- Hobbies, interests, or other personal preferences
- Biometric data such as fingerprints or facial recognition data

**Private information** is any information that users do not want shared publicly and must be kept private (i.e., information that is accessible only by a certain group of authorized users). Some private data is private by law (for example medical data), and some is private more by personal preference.

### Personally identifiable information

Following on from the above section, **personally identifiable information** (PII) is information that can be used, in whole or in part, to track down and/or identify a specific person. For example, if a site leaks a list of users' names and zip codes online, a bad actor could almost certainly use this information to find their full addresses. Even if a full-scale leak does not happen, it is still possible to identify users through less obvious means, such as the browsers they are using, the devices they are using, specific fonts they have installed, and so on.

### Tracking

**Tracking** refers to the process of recording a user's activity across many different websites. This can be done in various ways, for example:

- Looking at multiple [third-party cookies](/en-US/docs/Web/Privacy/Guides/Third-party_cookies) set across different sites where third-party content is embedded to find out various information points about the user.
- Looking at the {{httpheader("Referer")}} header to see where a user has navigated from.
- Including parameters on the URLs of inbound links (for example in embedded ads linking to product pages, or marketing emails) that can reveal to the linked site where the link originated from, what marketing campaign it is part of, the email address or other identifier of the user that clicked on it, etc. This process is referred to as **link decorating**, and results in link URLs that look like this: `https://example.com/article/?id=62yhgt1a&campaign=902`.
- Redirect tracking, which involves trackers momentarily (and imperceptibly) redirecting a user to their website to use first-party storage to track that user across websites. This allows trackers to get around third-party cookies being blocked. For example, if you have read a product review and want to click through to buy it, you might unwittingly navigate to the redirect tracker first, _then_ to the retailer. This means the tracker is loaded as a first party, and can associate tracking data with the identifiers they have stored in their first-party cookies before forwarding you to the retailer.

Tracking data can be used to build a profile of a user and their interests and preferences, which is usually bad and can be annoying to various degrees. For example:

- **Targeted ads**: Everyone has had the unnerving experience of researching some items to buy on one device and then suddenly being bombarded by adverts for the same products on all their other devices.
- **Selling or sharing data**: Some third parties have been known to compile tracking data and then sell it to/share it with others to use for various purposes, like targeted ads. This is obviously highly unethical and may also be illegal, depending on where in the world it happens.
- **Prejudice via data**: In the worst cases, sharing data could result in the user being unfairly disadvantaged. For example, imagine an insurance company finding out data points about a potential customer that they didn't consent to share, and using them as a justification for increasing insurance premiums.

### Fingerprinting

A process very closely related to tracking is **fingerprinting**: this specifically refers to _identifying_ users by building up a store of data points about them that differentiate them from other users. This could be anything from cookie contents to what browser they are using and what fonts they have installed locally.

Modern browsers take steps to help prevent fingerprinting-based attacks by either not allowing information to be accessed or, where the information must be made available, by introducing variations or "noise" that prevent it from being used for identification purposes.

For example, if a website queries a user's browser for the elapsed time, a comparison of that time to the time reported by the server might be useful as a factor in fingerprinting. Because of this, browsers typically introduce a small amount of variability to timers to make them less useful for identifying the user's system.

> [!NOTE]
> See [Fingerprinting](https://web.dev/learn/privacy/fingerprinting/) on web.dev for additional useful information.

## Privacy features provided by browsers

Browser vendors are aware of the need to protect user privacy and the negative effects of tracking, fingerprinting, etc., on user experience. To this end, they have implemented various features that enhance privacy protection and/or mitigate threats. In this section, we look at different categories of privacy protection that browsers apply automatically.

### HTTPS by default

[Transport Layer Security (TLS)](/en-US/docs/Web/Security/Transport_Layer_Security) provides security and privacy by encrypting data during transport over the network and is the technology behind the [HTTPS](/en-US/docs/Glossary/HTTPS) protocol. TLS is good for privacy because it stops third parties from being able to intercept transmitted data and use it maliciously, for example for tracking.

All browsers are moving towards requiring HTTPS by default; this is practically the case already because you can't do much on the web without this protocol.

Related topics are as follows:

- [Certificate Transparency](/en-US/docs/Web/Security/Certificate_Transparency)
  - : An open standard for monitoring and auditing certificates, creating a database of public logs that can be used to help identify incorrect or malicious certificates.
- [HTTP Strict Transport Security (HSTS)](/en-US/docs/Web/HTTP/Reference/Headers/Strict-Transport-Security)
  - : HSTS is used by servers to let them protect themselves from protocol downgrade and cookie hijack attacks by letting sites tell clients that they can only use HTTPS to communicate with the server.
- [HTTP/2](/en-US/docs/Glossary/HTTP_2)
  - : While HTTP/2 technically does not <em>have</em> to use encryption, most browser developers support it only when used with HTTPS; so in that regard, it can be thought of as a feature to enhance security/privacy.

### Opt-in for "powerful features"

So-called "powerful" web API features that provide access to potentially sensitive data and operations are available only in [secure contexts](/en-US/docs/Web/Security/Secure_Contexts), which basically means HTTPS-only. Not only that, but these web features are gated behind a system of user permissions. Users have to explicitly opt in to features like allowing notifications, accessing geolocation data, making the browser go into fullscreen mode, accessing media streams from webcams, using web payments, etc.

### Anti-tracking technology

Browsers have implemented several anti-tracking features that automatically enhance their users' privacy protection. Many of these block or limit the ability of third-party sites embedded in {{htmlelement("iframe")}}s to access cookies set on the top-level domain, run tracking scripts, etc.

- The {{httpheader("Set-Cookie")}} header [`SameSite`](/en-US/docs/Web/HTTP/Reference/Headers/Set-Cookie#samesitesamesite-value) attribute's default value has been updated to `Lax`, to provide better protection against tracking and {{glossary("CSRF")}} attacks. See [Controlling third-party cookies with `SameSite`](/en-US/docs/Web/HTTP/Guides/Cookies#controlling_third-party_cookies_with_samesite) for more information.
- Browsers have all started to block third-party cookies by default. See [How do browsers handle third-party cookies?](/en-US/docs/Web/Privacy/Guides/Third-party_cookies#how_do_browsers_handle_third-party_cookies) for more details.
- Browsers are implementing technologies to allow third-party cookies only in certain circumstances that do not damage privacy, or to implement common use cases that currently require third-party cookies in alternative ways. See [Transitioning from third-party cookies](/en-US/docs/Web/Privacy/Guides/Third-party_cookies#transitioning_from_third-party_cookies) and [Replacing third-party cookies](/en-US/docs/Web/Privacy/Guides/Third-party_cookies#replacing_third-party_cookies).
- Several browsers strip out known tracking parameters from URLs — this includes Firefox, Safari, and Brave. Browser extensions also help to do this, for example [ClearURLs](https://addons.mozilla.org/en-GB/firefox/addon/clearurls/).
- Browsers have implemented [redirect tracking protection](/en-US/docs/Web/Privacy/Guides/Redirect_tracking_protection).

## Privacy considerations for client-side developers

There are several actions web developers can and should take to improve privacy for their users. The below sections discuss the most important ones. Some of the categories are not purely technical tasks as such and will involve collaboration with other team members.

## Collect data ethically

Companies collect lots of different data from their users for a variety of different reasons:

- Usernames, passwords, emails, etc. for authentication purposes.
- Emails, postal addresses, and phone numbers for communication.
- Age, gender, geographical location, favorite pastimes, and a host of other PII for anything from site personalization to customer satisfaction surveys.
- Browsing habits on their sites and other sites, to measure page and feature success metrics.
- And so much more.

When collecting data from your customers, you have an opportunity to behave with integrity, show them that you are trustworthy, and build a great relationship with them, in turn, improving your brand and your chance of success.

The ethics of data collection can be broken down into three simple principles:

- Don't collect more data than you need
- Communicate clearly how you are going to use the data you collect
- Delete the data once you have finished with it

> [!NOTE]
> The tips provided below make for a better, more privacy-aware user experience, but many of them are required by law to comply with regulations, for example the [GDPR](https://gdpr.eu/) in the EU. You should make sure to find out what regulations apply to you in your locale, and what you need to do to comply with them.

### Don't collect more data than you need

It is tempting to ask for a lot of data from your users because you think it might be useful in the future. However, every bit of extra data you collect adds risk to your users' privacy and increases the chance that they will abandon the step they are performing (whether it is filling out a survey or signing up for a service).

It is good to anonymize data. You should also consider whether you can get what you need by making your data request less granular. As an example, instead of asking a user their favorite products, you could ask them to select between more general categories.

The best way to protect user privacy though, is to minimize the data you collect. Referring to the previous example, you could infer the same data by looking at user purchase history. As another example, users appreciate being able to buy products anonymously. You shouldn't force them to sign up for an account; if it's not necessary for the service to operate, it should be their choice.

### Communicate clearly how you are going to use the data you collect

Once you have decided what data you are going to collect, you should publish a privacy policy on your site that clearly states:

- Data that you collect
- Ways in which you use the data
- Parties with whom you tend to share the data, if at all, and a declaration that you will ask for user consent before sharing
- The duration for which you keep the data before it is deleted
- Ways in which users can view the data you have collected from them and delete it if they want to

When providing you with data, your users should be given an opportunity to read your privacy policy, and consent to it. They should be able to control if they are happy with this and agree to your terms. And as indicated above, they should also get to see what data of theirs you have collected, and delete it if they want to.

When you've published your privacy policy, you need to make sure that you comply with it — doing what you say you are going to do is very important in building user trust. You should only collect the data you say you'll collect, and only use it for the purpose you say you'll use it for. If someone from your company comes up with a clever new way to use existing data, that still isn't OK under the terms of your policy if it doesn't specify that you'll use it for that purpose. If users consented to the use of their data for a specific purpose and that purpose expands, you may have to consider obtaining new consent.

### Delete the data once you have finished with it

Earlier on, we mentioned giving users a way to see what data of theirs you have collected, and delete it if they want to. You could possibly do this as part of the same experience they can use to delete their account (their data goes with it), or make them two separate options. Either way, the options should be easy to find.

Allowing the user to choose when significant portions of data get deleted is very empowering, and builds trust, but there may be some bits of data that you will want to handle deletion of yourself. For example, some data might only be used for a few hours or minutes and then deleted, like data that is used during the administration of a user's session while they are logged in.

> [!NOTE]
> The {{httpheader("Clear-Site-Data")}} HTTP response header is very useful for clearing short-lived user data — it instructs the browser to clear out its cache and/or cookies and/or storage (e.g., [Web Storage](/en-US/docs/Web/API/Web_Storage_API) or [IndexedDB](/en-US/docs/Web/API/IndexedDB_API) data). For example, you might get your server to send it along with a "logged out confirmation" page so that once the user is logged out, their data is safely removed.

## Cut down on tracking

Earlier on we discussed tracking, and some of the unethical purposes it is used for. We shouldn't have to spell out how such uses can erode user trust; wherever possible, you should only use potential tracking mechanisms like [third-party cookies](/en-US/docs/Web/Privacy/Guides/Third-party_cookies) for ethical uses, such as transferring sign-in or other personalization status across sites.

Also recall from earlier that browsers are all starting to block third-party cookies by default, while implementing alternative technologies to achieve common use case. It is a good idea to prepare for this, by limiting the amount of tracking activities you rely on, and/or implementing desired information persistence in other ways. See [Transitioning from third-party cookies](/en-US/docs/Web/Privacy/Guides/Third-party_cookies#transitioning_from_third-party_cookies) for more information.

## Carefully manage third-party resources

Of course, it would be easy to manage privacy if you were only worried about resources you have created (code, cookies, sites, etc.). The real challenge comes from the fact that your site will likely use third-party resources. This can include third-party content embedded in `<iframe>`s, libraries, frameworks, APIs, externally-hosted resources such as images and videos, etc.

Third-party resources are an essential part of modern web development, they provide a lot of power. However, any third-party resource you allow onto your site potentially has the same permissions as your own resources; it all depends on how it is included on your site:

- JavaScript running inside third-party content embedded in your site via an `<iframe>` is separated by [same-origin policy](/en-US/docs/Web/Security/Same-origin_policy), meaning that it wouldn't have access to other scripts and data included in the top-level browsing context.
- However, a third-party script included directly in your page via a {{htmlelement("script")}} element _would_ have access to your other scripts and data, whether it was hosted on your site or another site. It would effectively be first-party code. A malicious script included in this way could secretly steal your users' data, for example sending it off to a third-party server.

It is important to audit all of the third-party resources you use on your site. Make sure you know what data they collect, what requests they make and to whom, and what their privacy policies are. Your carefully designed privacy policy is useless if you use a third-party script that violates it.

> [!NOTE]
> There are various tools out there that can help you build up a picture of what requests a site is making, for example the [Request Map Generator](https://requestmap.webperf.tools/).

Once you have audited your third-party resources and understand what they are doing, you should then consider their negatives as a trade-off for the value they bring. If a third-party script is free and really useful but collects quite a lot of user data, you could:

1. Accept that trade-off, update your privacy policy to include details of it, and hope that it doesn't impact your users' trust too much.
2. Look for an alternative, less data-hungry third-party tool.
3. Build your own tool.

The following list provides some tips on how to mitigate privacy risks inherent with using third-party resources:

- When embedding third-party resources, consider if there is a way to achieve the same or a similar effect with less privacy impact. For example, it might be fun to have a social media post viewer embedded on your site, but is it really necessary? Wouldn't a link to your social media page be sufficient? Also, some third-party services have privacy-enhancing options. See, for example, YouTube's [Embed videos & playlists > Turn on privacy-enhanced mode](https://support.google.com/youtube/answer/171780).
- Where possible, you should block third parties from receiving a {{httpheader("Referer")}} header when you make requests to them. This can be done in a pretty granular way, for example by including [rel="noreferrer"](/en-US/docs/Web/HTML/Reference/Attributes/rel/noreferrer) on external links. Or, you could set this more globally for the page or site, for example by using the {{httpheader("Referrer-Policy")}} header.

  > [!NOTE]
  > See also [Referer header: privacy and security concerns](/en-US/docs/Web/Security/Referer_header:_privacy_and_security_concerns).

- Use the {{httpheader("Permissions-Policy")}} HTTP header to control access to API "powerful features" (such as notifications, geolocation data, accessing media streams from webcams, etc.). This can be useful for privacy because it stops third-party sites from doing unexpected things with these features, and users don't want to be unnecessarily bombarded by permission prompts that they may not understand. You can also control usage of "powerful features" inside third-party sites embedded inside {{htmlelement("iframe")}} elements by specifying permissions policies inside an `allow` attribute on the `<iframe>` itself.

  > [!NOTE]
  > See also our [Permissions-Policy guide](/en-US/docs/Web/HTTP/Guides/Permissions_Policy) for more information and examples, and [permissionspolicy.com](https://www.permissionspolicy.com/) for useful tools including a policy generator.

- Use the {{htmlelement("iframe")}} `sandbox` attribute to allow or disallow usage of certain features inside the content embedded in the `<iframe>` — this includes things like downloads, form submissions, modals, and scripting.

> [!NOTE]
> See [Third parties](https://web.dev/learn/privacy/third-parties/) over on web.dev for additional useful information on auditing and more.

## Protect user data

You need to make sure that user data is transmitted and stored securely once you've collected it. This is more of a [security](/en-US/docs/Web/Security) topic, but it is worth mentioning here — a good privacy policy is useless if your security is lax and attackers can steal the data from you.

The below tips offer some guidance on protecting your user's data:

- Security is hard to get right. When implementing a secure solution that involves data collection — particularly if it is sensitive data such as sign-in credentials — it makes sense to use a reputable solution from a well-respected provider. For example, any respectable server-side framework will have built-in features to protect against common vulnerabilities. You could also consider using a specialized product for your purpose — for example an identity provider solution, or a secure online survey provider.
- If you want to roll out your own solution for collecting user data, make sure you understand what you are doing. Hire an experienced server-side developer and/or security engineer to implement the system, and ensure it is tested thoroughly. Use multifactor authentication (MFA) to provide better protection. Consider using a dedicated API such as [Web Authentication](/en-US/docs/Web/API/Web_Authentication_API) or [Federated Credential Management](/en-US/docs/Web/API/FedCM_API) to streamline the client-side of the app.
- When collecting user sign-up information, enforce strong passwords so your user's account details cannot be easily guessed. Weak passwords are one of the main causes of security breaches. Encourage your users to use a password manager to generate and store complex passwords; this way they won't worry about remembering them, or create a security risk by writing them down.
- Don't include sensitive data in URLs — if a third party intercepts the URL (for example via the {{httpheader("Referer")}} header), they could steal that information. Use `POST` requests rather than `GET` requests to avoid this.
- Consider using tools like [Content Security Policy](/en-US/docs/Web/HTTP/Guides/CSP) and [Permissions Policy](/en-US/docs/Web/HTTP/Guides/Permissions_Policy) to enforce a set of feature usage on your site that makes it harder to introduce vulnerabilities. Be careful when doing this — if you block usage of a feature that a third-party script relies on to work, you may end up breaking your site's functionality. This is something you can look into when auditing your third-party resources (see [Carefully manage third-party resources](#carefully_manage_third-party_resources)).

## See also

- [Web security](/en-US/docs/Web/Security)
- [Learn Privacy](https://web.dev/learn/privacy/) on web.dev
- [The Privacy Sandbox](https://privacysandbox.google.com/) on privacysandbox.google.com
- [Lean Data Practices](https://www.mozilla.org/en-US/about/policy/lean-data/) on mozilla.org
