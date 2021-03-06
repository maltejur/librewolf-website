# Frequently Asked Questions

This FAQ documents version 3.0 of the settings. Please always upgrade to the
latest version of the browser available. If your question is not answered here,
you can try to get answers in our
[Gitter](https://gitter.im/librewolf-community/librewolf) /
[Matrix](https://app.element.io/#/room/#librewolf:matrix.org) room, or on
[r/LibreWolf](https://www.reddit.com/r/LibreWolf/) and
[c/LibreWolf](https://lemmy.ml/c/librewolf).

Alternatively you could check the parts in the firefox documentation that could
be relevant:

- [Protect your privacy](https://support.mozilla.org/en-US/products/firefox/protect-your-privacy).
- [Manage preferences and add-ons](https://support.mozilla.org/en-US/products/firefox/manage-preferences-and-add-ons-firefox).
- [Fix slowness, crashing, error messages and other problems](https://support.mozilla.org/en-US/products/firefox/fix-problems).
- <a name="performance"></a>[Tweak the performance](https://support.mozilla.org/en-US/kb/performance-settings?as=u&utm_source=inproduct).
- <a name="prefs-connection-settings"></a>[Network settings](https://support.mozilla.org/en-US/kb/connection-settings-firefox).

## General questions:

- [Can I use LibreWolf with Tor?](#can-i-use-librewolf-with-tor)
- [How often do you update LibreWolf?](#how-often-do-you-update-librewolf)
- [Do you recommend using any extension?](#do-you-recommend-using-any-extension)
- [Does LibreWolf make any outgoing connection?](#does-librewolf-make-any-outgoing-connection)

## Settings and _librewolf.override.cfg_:

- [Where do I find my _librewolf.overrides.cfg_?](#where-do-i-find-my-librewolfoverridescfg)
- The ~/.librewolf directory does not exist, so
  [where should I put my overrides?](#the-librewolf-directory-does-not-exist-so-where-should-i-put-my-overrides)
- [Why do I see "Your browser is being managed by your organization" in the settings?](#why-do-i-see-your-browser-is-being-managed-by-your-organization-in-the-settings)
- [What are some tips on a more hardened setup?](#what-are-some-tips-on-a-more-hardened-setup)
- My cookies are gone.
  [How do I stay logged into specific websites?](#how-do-i-stay-logged-into-specific-websites)
- [How do I keep my first-party cookies?](#how-do-i-keep-my-first-party-cookies)
- [How do I enable DRM?](#how-do-i-enable-drm)
- [How do I enable WebGL?](#how-do-i-enable-webgl)
- [Why am I seeing striped images?](#why-am-i-seeing-striped-images)
- [How do I allow canvas access?](#how-do-i-allow-canvas-access)
- [What are the most common downsides of RFP (resist fingerprinting)?](#what-are-the-most-common-downsides-of-rfp-resist-fingerprinting)
- [Why is LibreWolf forcing light theme?](#why-is-librewolf-forcing-light-theme)
- [What settings are used to enable video conferencing?](#what-settings-are-used-to-enable-video-conferencing)
- [How do I enable IPv6?](#how-do-i-enable-ipv6)
- [How do I enable extensions auto-updating?](#how-do-i-enable-extensions-auto-updating)
- [How do I enable location aware browsing?](#how-do-i-enable-location-aware-browsing)
- [How do I disable bookmarks opening in a new tab?](#how-do-i-disable-bookmarks-opening-in-a-new-tab)
- [How do I enable search suggestions?](#how-do-i-enable-search-suggestions)
- [How do I add a search engine?](#how-do-i-add-a-search-engine)
- [How do I allow autoplay of media?](#how-do-i-allow-autoplay-of-media)
- [How do I enable Google Safe Browing?](#how-do-i-enable-google-safe-browing)
- [How do I enable OCSP certificate revocation?](#how-do-i-enable-ocsp-certificate-revocation)
- [How do I enable the extension firewall?](#how-do-i-enable-the-extension-firewall)
- [How do I enable push notifications?](#how-do-i-enable-push-notifications)
- [How do I disable Mozilla Tracking Protection?](#how-do-i-disable-mozilla-tracking-protection)
- [How do I change language in the browser?](#how-do-i-change-language-in-the-browser)
- [Why is the built-in password manager disabled?](#why-is-the-built-in-password-manager-disabled)
- [Why isn't First Party Isolate enabled by default?](#why-isnt-first-party-isolate-enabled-by-default)
- [Does LibreWolf use HTTPS-Only mode?](#does-librewolf-use-https-only-mode)

## Linux specific questions:

- [Can't open links with Librewolf when using Wayland](#cant-open-links-with-librewolf-when-using-wayland)

## macOS specific questons:

- [How do I install LibreWolf on macOS?](#how-do-i-install-librewolf-on-macos)
- [How do I build LibreWolf on macOS?](#how-do-i-build-librewolf-on-macos)
- [How do I update LibreWolf on macOS?](#how-do-i-update-librewolf-on-macos)
- [Is LibreWolf available via Homebrew?](#is-librewolf-available-via-homebrew)
- [Does LibreWolf work on M1 machines?](#does-librewolf-work-on-m1-machines)
- [Why is LibreWolf marked as broken?](#why-is-librewolf-marked-as-broken)

## Windows specific questions:

# Answers

## General questions:

### [Can I use LibreWolf with Tor?](#general-questions)

Please **don't**.

Tor Browser is specifically designed to reduce fingerprintability. Using
LibreWolf or any other browser would make you stand out. From a personal
security perspective it's also a good idea to have a seperate browser for .onion
sites and general Tor browsing.

### [How often do you update LibreWolf?](#general-questions)

LibreWolf is always based on the latest version of Firefox. Updates usually come
within three days from each upstream stable release, at times even the same day.
Unless problems arise, we always try to release often and in a timely manner.

It should however be noted that LibreWolf does not have auto-update
capabilities, and therefore it relies on package managers or users to apply
them.

<a name="addons-help"></a>

### [Do you recommend using any extension?](#general-questions)

Yes, in fact we include uBlockOrigin in the browser. As a general rule you
shouldn't install too many add-ons, but we have a few
[suggestions](/docs/addons/) that you can look at.

### [Does LibreWolf make any outgoing connection?](#general-questions)

Yes, but they aren't in any way privacy invading. Specifically they are needed
to fetch and update the blocking lists for
[uBO](https://github.com/gorhill/uBlock/wiki/Can-you-trust-uBlock-Origin%3F) and
[Tracking Protection](#how-do-i-disable-mozilla-tracking-protection), which we
considered more important than disabling all outgoing connections, especially
ones that are harmless.

In the near future we will probably also allow outgoing connections required for
[CRL](https://en.wikipedia.org/wiki/Certificate_revocation_list), in order to
increase the security of the browser without compromising privacy (like
alternatives such as OCSP would require).

With that being said, LibreWolf is still commited to removing all privacy
invading connections, and to keep all connections to the bare minimum required
to maximize and balance privacy and security.

## Settings and _librewolf.override.cfg_:

### [Where do I find my _librewolf.overrides.cfg_?](#settings-and-librewolfoverridecfg)

Using overiddes is a great way to change your default settings across multiple
profiles and installations, which means that it also allows you to easily backup
and port your preferences.

On most Linux (not Flatpak), in the home directory:

```
$HOME/.librewolf/librewolf.overrides.cfg
```

On Linux with Flatpak:

```
$HOME/.var/app/io.gitlab.librewolf-community/.librewolf/librewolf.overrides.cfg
```

On macOS, in your home directory:

```
$HOME/.librewolf/librewolf.overrides.cfg
```

On Windows, in your profile directory:

```
%USERPROFILE%\.librewolf\librewolf.overrides.cfg
```

### [The ~/.librewolf directory does not exist, so where should I put my overrides?](#settings-and-librewolfoverridecfg)

You can simply create that directory by going to your home/profile directory and
entering `mkdir .librewolf`.

### [Why do I see "Your browser is being managed by your organization" in the settings?](#settings-and-librewolfoverridecfg)

That message is displayed when a `policies.json` file is used to enforce some
settings inside the browser. We specifically
[use it](https://gitlab.com/librewolf-community/settings/-/blob/master/distribution/policies.json)
to include uBlockOrigin and the privacy respecting search engines, but also to
disable some features like telemetry, studies and pocket.

In some releases this message is patched, and you should not see it anymore.

### [What are some tips on a more hardened setup?](#settings-and-librewolfoverridecfg)

You can disable asm.js and WebAssembly to enhance your security. Please keep in
mind that having them disabled could increase your fingerprint, as well as
reduce performance.

```
defaultPref("javascript.options.asmjs", false);
defaultPref("javascript.options.wasm", false);
```

To improve your privacy we suggest enabling letterboxing, in order to prevent
your real window size from being fingerprinted. This can be especially useful if
you resize your window.

```
defaultPref("privacy.resistFingerprinting.letterboxing", true);
```

<a name="storage-permissions"></a>

### [How do I stay logged into specific websites?](#settings-and-librewolfoverridecfg)

Add an exception at Settings > Privacy & Security > Cookies and Site Data >
Manage Exceptions. Make sure you add a website to the exceptions **before** you
login, both _http_ and _https_ versions of the domain. If you want to stay
logged into `www.example.com` enter `example.com` and click on "Allow": you
should then see the two versions listed, and you can go ahead and save the
changes.

Please notice that these exceptions are bypassed by the settings at Privacy &
Security > History > Clear history when LibreWolf closes > Settings.

### [How do I keep my first-party cookies?](#settings-and-librewolfoverridecfg)

This setup was designed for users that want to keep **all** cookies across
multiple browsing sessions, in order to give them a somewhat decent amount of
protection.

While with the following prefs you are blocking third party cookies and
isolating them with FPI, using this configuration will still leave you exposed
to first party tracking across multiple sessions, and you should be aware that
in general cookies and website data should be cleared with frequency. For this
reason we suggest to use the default setup, and if you really want to use this
one consider **clearing your cookies and website data manually with frequency**.

```
pref("browser.contentblocking.category", "custom"); // strict would force dFPI
defaultPref("privacy.firstparty.isolate", true); // enable FPI
defaultPref("network.cookie.cookieBehavior", 1); // block 3rd party cookies
defaultPref("network.cookie.lifetimePolicy", 0); // keep cookies untill they expire
```

<a name="drm-content"></a>

### [How do I enable DRM?](#settings-and-librewolfoverridecfg)

We disable DRM by default, as we consider it a limitation to user freedom. Take
a moment to [read about it](https://www.eff.org/issues/drm) before you go ahead
and enable it.

DRM support can be enabled from Settings > General > Digital Right Management
(DRM) Content. Additionally, a pop-up and an icon in your URL bar will show up
when a website is trying to use DRM.

### [How do I enable WebGL?](#settings-and-librewolfoverridecfg)

Put this in your _librewolf.overrides.cfg_:

```
defaultPref("webgl.disabled", false);
```

If you enable WebGL please consider using an extension like
[CanvasBlocker](https://addons.mozilla.org/en-US/firefox/addon/canvasblocker/).

### [Why am I seeing striped images?](#settings-and-librewolfoverridecfg)

If you see striped images in your browser, that's most like caused by the fact
that the website needs canvas access to display properly. Check out
[how to allow it](#how-do-i-allow-canvas-access).

### [How do I allow canvas access?](#settings-and-librewolfoverridecfg)

Canvas can be handled on a per-site basis thank to RFP. You will be prompted for
access next to the URL bar, so look for the icon there. Please be mindful when
allowing canvas access as it is a very strong fingerprinting vector, however it
is required by websites more and more often.

Generally speaking, if you are already logged into a website you shouldn't
stress too much about giving it canvas access because they already know who you
are.

### [What are the most common downsides of RFP (resist fingerprinting)?](#settings-and-librewolfoverridecfg)

It is possible that users will experience breakage because of RFP: usually this
is caused by canvas access, which can be relaxed on a per-site basis, as
[described previously](#how-do-i-allow-canvas-access). There's currently no
workaround for keyboard alt-keys.

Other common problems brought by RFP include: spoofed **timezone**, forced light
**theme**, fixed **user agent**, smaller and fixed **window size** on startup.
There's no real workaround for these annoyances as they are intended to protect
your privacy, and tweaking them using extensions or preferences significantly
impacts the effectiveness of RFP, both for the user himself/herself, and the
rest of the userbase: in fact modifications create a subset of users who stand
out, and they reduce the number of RFP users who look the same, making it worse
for everyone.

For this very reason we suggest **against** modifying any metric involved in
RFP, as even a single change could make it useless. We also suggest users to get
used to RFP and stick with it as much as possible: it is a very powerful tool
that gets improvements as the result of the
[Tor Uplift Project](https://wiki.mozilla.org/Security/Tor_Uplift), and it will
surely benefit your privacy in a **major** way.

Still, if you don't like the downsides of resist fingerprinting, you can disable
it by adding to your overrides:

```
defaultPref("privacy.resistFingerprinting", false);
```

In that case consider using an extension like
[CanvasBlocker](https://addons.mozilla.org/en-US/firefox/addon/canvasblocker/)
to retain at least a minimum amount of fingerprinting protection.

### [Why is LibreWolf forcing light theme?](#settings-and-librewolfoverridecfg)

This is a privacy to reduce your fingerprint, which is part of RFP. Please red
[this](#what-are-the-most-common-downsides-of-rfp-resist-fingerprinting) before
you go on: as stated there, our stance is that you should **never** alter RFP
behavior in any way if you want to protect your privacy.

If you want dark theme, first of all check wether your favourite websites allow
to se it manually. Another possible solution is represented by using an
[extension that enforces a dark theme](/docs/addons#other-useful-addons), but be
careful as it could make you stand out. Alternatively, LibreWolf has a
preference which allows to stop `privacy.resistFingerprinting` from forcing the
light time: the preference is intentionally locked and users should be aware
that enabling it will cause them to increase their fingerprint, so use extra
caution, and if you can avoid it.

To bring back dark theme add to your overrides:

```
lockPref("privacy.override_rfp_for_color_scheme", true);
```

### [What settings are used to enable video conferencing?](#settings-and-librewolfoverridecfg)

The following two prefs enable WebRTC and are required by basically all video
conferencing services:

```
defaultPref("media.peerconnection.enabled", true);
defaultPref("media.peerconnection.ice.no_host", false);
```

Please be careful as WebRTC could leak your real IP address while using a VPN.

Other video conferencing services also require to
[enable WebGL](#how-do-i-enable-webgl) and to allow autoplay, which can be set
on a per-site basis from the URL bar.

### [How do I enable IPv6?](#settings-and-librewolfoverridecfg)

Before enabling IPv6 make sure you are using **IPv6 privacy extension** at the
OS level: while macOS and Windows users are already covered, some Linux distros
do not enable it by default. You can then add the following pref to your
overrides:

```
defaultPref("network.dns.disableIPv6", false);
```

### [How do I enable extensions auto-updating?](#settings-and-librewolfoverridecfg)

To enable extensions auto-update go to Settings > Extensions and Themes, then
click on the settings icon and tap 'Update Add-ons automatically'. If you do not
plan to review the code of your extensions before you install updates, please go
ahead and enable this.

### [How do I enable location aware browsing?](#settings-and-librewolfoverridecfg)

To enable location aware browsing you need the following preferences:

```
defaultPref("geo.enabled", true);
defaultPref("permissions.default.geo", 0);
```

The permission will still be behind a prompt, and handled on a per-site basis.

### [How do I disable bookmarks opening in a new tab?](#settings-and-librewolfoverridecfg)

Add to your overrides:

```
defaultPref("browser.tabs.loadBookmarksInTabs", true);
```

### [How do I enable search suggestions?](#settings-and-librewolfoverridecfg)

If you use a privacy respecting search engine go to Settings > Search > Search
Suggestions, and enable search suggestions.

### [How do I add a search engine?](#settings-and-librewolfoverridecfg)

LibreWolf provides a selection of privacy respecting search engines, but you can
add more by following
[this guide](https://support.mozilla.org/en-US/kb/add-or-remove-search-engine-firefox).

### [How do I allow autoplay of media?](#settings-and-librewolfoverridecfg)

Autoplay can be controlled on a per-site basis from your urlbar.

<a name="phishing-malware"></a>

### [How do I enable Google Safe Browing?](#settings-and-librewolfoverridecfg)

We disable Safe Browsing as we consider it a censorship concern, and we would
rather not let Google control another aspect of the internet.

If you want to re-enable Google Safe Browsing insert the following prefs in your
overrides:

```
defaultPref("browser.safebrowsing.malware.enabled", true);
defaultPref("browser.safebrowsing.phishing.enabled", true);
defaultPref("browser.safebrowsing.blockedURIs.enabled", true);
defaultPref("browser.safebrowsing.provider.google4.gethashURL", "https://safebrowsing.googleapis.com/v4/fullHashes:find?$ct=application/x-protobuf&key=%GOOGLE_SAFEBROWSING_API_KEY%&$httpMethod=POST");
defaultPref("browser.safebrowsing.provider.google4.updateURL", "https://safebrowsing.googleapis.com/v4/threatListUpdates:fetch?$ct=application/x-protobuf&key=%GOOGLE_SAFEBROWSING_API_KEY%&$httpMethod=POST");
defaultPref("browser.safebrowsing.provider.google.gethashURL", "https://safebrowsing.google.com/safebrowsing/gethash?client=SAFEBROWSING_ID&appver=%MAJOR_VERSION%&pver=2.2");
defaultPref("browser.safebrowsing.provider.google.updateURL", "https://safebrowsing.google.com/safebrowsing/downloads?client=SAFEBROWSING_ID&appver=%MAJOR_VERSION%&pver=2.2&key=%GOOGLE_SAFEBROWSING_API_KEY%");
```

If you also want Safe Browsing to locally check your downloads add:

```
defaultPref("browser.safebrowsing.downloads.enabled", true);
```

### [How do I enable OCSP certificate revocation?](#settings-and-librewolfoverridecfg)

To enable OCSP certificate revocation add to your overrides:

```
defaultPref("security.OCSP.enabled", 1);
defaultPref("security.OCSP.require", true);
```

### [How do I enable the extension firewall?](#settings-and-librewolfoverridecfg)

To enable the extension firewall and prevent internet access to the extensions,
add to your overrides:

```
defaultPref("extensions.webextensions.base-content-security-policy", "default-src 'none'; script-src 'none'; object-src 'none';");
defaultPref("extensions.webextensions.base-content-security-policy.v3", "default-src 'none'; script-src 'none'; object-src 'none';");
```

<a name="push"></a>

### [How do I enable push notifications?](#settings-and-librewolfoverridecfg)

To enable push notifications add the following prefs - which include the push
server and service workers, required for push notifications - to your overrides:

```
defaultPref("dom.push.enabled", true);
defaultPref("dom.push.serverURL", "wss://push.services.mozilla.com/");
defaultPref("dom.serviceWorkers.enabled", true);
```

<a name="enhanced-tracking-protection"></a> <a name="turn-off-etp-desktop"></a>

### [How do I disable Mozilla Tracking Protection?](#settings-and-librewolfoverridecfg)

In LibreWolf we decided to keep Tracking Protection, as it plays nicely with uBO
and it can block some extra scripts. Additionaly, when set to strict it includes
dFPI, shims that reduce breakage, better cookie cleaning and stricter referrer
policies. For this reason, we always suggest the default **strict** mode, and
when using it please
[do not enable FPI](/docs/faq#why-isnt-first-party-isolate-enabled-by-default),
as it interferes with the more recent dFPI.

Tracking Protection requires some occasional outgoing connections, in order to
fetch its blocking lists: these connections are harmless for privacy, and TP has
a flawless track record in this regard. A particular important connection is the
one that TP makes on first launch, as without it the feature cannot effectively
work.

If you want, you can block these outgoing connections by using:

```
defaultPref("browser.safebrowsing.provider.mozilla.updateURL", "");
defaultPref("browser.safebrowsing.provider.mozilla.gethashURL", "");
```

As stated above, and despite what you see in the Settings UI, blocking these
connections will cause TP to **stop working**, as it won't be able to use the
lists that allow it to block known tracking, cryptomining and fingerprinting
scripts.

### [How do I change language in the browser?](#settings-and-librewolfoverridecfg)

At the moment LibreWolf spoofs everything as en-US in order to reduce every
possible leaking point that fingerprinting techniques could use, regardless of
the user's locale. If you want to learn more read
[this issue](https://gitlab.com/librewolf-community/browser/windows/-/issues/64),
which also contains a solution for those who want to change language.

<a name="lockwise-alerts"></a> <a name="primary-password-stored-logins"></a>

### [Why is the built-in password manager disabled?](#settings-and-librewolfoverridecfg)

We believe you should use a password manager that is better for your security
and comfort, please consider some of the options in our
[recommended addons](/docs/addons#recommended-addons).

<a name="containers"></a>

### [Why isn't First Party Isolate enabled by default?](#settings-and-librewolfoverridecfg)

FPI is not enabled by default as we use dFPI, and the two do not work well
togheter. dFPI is a newer implementation and it causes less breakage, plus it is
included by default when using Tracking Protection in strict mode.

Please also notice that dFPI makes containers and
[containers extensions](/docs/addons#container-addons) redudant, unless you want
to protect your privacy when visiting the same website multiple times, during
the same browsing sessions.

<a name="https-only-prefs"></a>

### [Does LibreWolf use HTTPS-Only mode?](#settings-and-librewolfoverridecfg)

Yes, and you won't need any extension for that. HTTP can still be
[allowed for certain sites](https://support.mozilla.org/en-US/kb/https-only-prefs#w_turn-off-https-only-mode-for-certain-sites).

## Linux specific questions:

### [Can't open links with Librewolf when using Wayland](#linux-specific-questions)

The solution is also described in
[this issue](https://github.com/flathub/io.gitlab.librewolf-community/issues/2).

When setting LibreWolf as a handler to open links with, in some circumstances,
environment variables parsed during "regular" launch are not parsed / applied
when opening LibreWolf as a handler (XDG MIME handling) when using Wayland.
Librewolf then either gets launched without opening the link or by giving an
error ('Librewolf is already running').

This can be fixed by placing a modified `.desktop` file in
`~/.local/share/applications/`.

It's easiest to just copy the existing `.desktop` file (for native packages
`/usr/share/applications/librewolf.desktop`, for Flatpak
`~/.local/share/flatpak/exports/share/applications/io.gitlab.librewolf-community.desktop`)
to `~/.local/share/applications/` and edit the `Exec` lines:

##### Flatpak

```
# io.gitlab.librewolf-community.desktop
Exec=/usr/bin/flatpak run --env=GDK_BACKEND=wayland --branch=stable --arch=x86_64 --command=librewolf --file-forwarding io.gitlab.librewolf-community @@u %u @@
Exec=/usr/bin/flatpak run --env=GDK_BACKEND=wayland --branch=stable --arch=x86_64 --command=librewolf --file-forwarding io.gitlab.librewolf-community @@u %u @@
Exec=/usr/bin/flatpak run --env=GDK_BACKEND=wayland --branch=stable --arch=x86_64 --command=librewolf --file-forwarding io.gitlab.librewolf-community --private-window @@u %u @@
Exec=/usr/bin/flatpak run --env=GDK_BACKEND=wayland --branch=stable --arch=x86_64 --command=librewolf --file-forwarding io.gitlab.librewolf-community --ProfileManager @@u %u @@
```

For Flatpak, this might also be possible by using
`flatpak override --user --env=GDK_BACKEND=wayland io.gitlab.librewolf-community`,
but this is not yet tested.

##### Native Linux Package

```
# librewolf.desktop

Exec=env GDK_BACKEND=wayland MOZ_ENABLE_WAYLAND=1 /usr/lib/librewolf/librewolf %u
Exec=env GDK_BACKEND=wayland MOZ_ENABLE_WAYLAND=1 /usr/lib/librewolf/librewolf --new-window %u
Exec=env GDK_BACKEND=wayland MOZ_ENABLE_WAYLAND=1 /usr/lib/librewolf/librewolf --private-window %u
```

## macOS specific questons:

### [How do I install LibreWolf on macOS?](#macos-specific-questons)

As explained in the
[install section](https://librewolf-community.gitlab.io/install/) you can either
build from source following the
[build guide](https://gitlab.com/librewolf-community/browser/macos/-/blob/master/build_guide.md),
install using a disk image from the
[releases](https://gitlab.com/librewolf-community/browser/macos/-/releases) or
install using HomeBrew.

### [How do I build LibreWolf on macOS?](#macos-specific-questons)

You can build from source following the
[build guide](https://gitlab.com/librewolf-community/browser/macos/-/blob/master/build_guide.md).

### [How do I update LibreWolf on macOS?](#macos-specific-questons)

To update the browser on macOS you need to grab the latest .app and drag it into
your `Applications` directory, or if you installed using HomeBrew you can do it
as you would for every other cask.

### [Is LibreWolf available via Homebrew?](#macos-specific-questons)

LibreWolf is available as a cask, so you can install entering
`brew install --cask librewolf`.

### [Does LibreWolf work on M1 machines?](#macos-specific-questons)

Yes, we provide native builds for both Intel and ARM based machines. If you own
a M1 powered MacBook the relative builds are refered to as `aarch64`, and they
are also marked as `experimental`, as they are cross-compiled on Intel machines
and we did not test them before release. Please consider that the build time on
M1 is relatively low, so building from source is probably worth it in any case.

### [Why is LibreWolf marked as broken?](#macos-specific-questons)

It is possible that M1 users see their recently downloaded LibreWolf flagged as
broken or unsafe by the OS.

This happens because we do not notarize the macOS version of the browser: we
don't have a paid Apple Developer license and we don't want to suppose this
signing mechanism that is put behind a paywall without providing significant
gains.

[Here](https://gitlab.com/librewolf-community/browser/macos/-/issues/19#note_597640488)
you can find a proposed fix, and the relative discussion.

## Windows specific questions:
