# Alien Swarm: Reactive Drop Translation Files

This document explains how Alien Swarm: Reactive Drop is translated. If you would like to contribute to the translation process, visit [reactivedrop_translations on GitHub](https://github.com/ReactiveDrop/reactivedrop_translations).

Most of Alien Swarm: Reactive Drop's translations are stored in files read by ILocalize, such as `closecaption_english.txt` or `reactivedrop_schinese.txt`. The game loads the English translation first, then whatever language is selected in Steam, for all of these files from all enabled addons. A list of supported languages can be found in [the Steamworks Partner documentation](https://partner.steamgames.com/doc/store/localization#supported_languages).

However, Alien Swarm: Reactive Drop loads these files differently than other Source Engine games. We use a full [KeyValues](https://developer.valvesoftware.com/wiki/KeyValues) parser, rather than the simplified one in localize.dll, and our file reader can handle UTF-8 (with or without BOM) as well as the standard UTF-16LE.

There is only one pool of translation tokens—that is, tokens in `closecaption_german.txt` cannot overlap with tokens in `reactivedrop_german.txt` or `basemodui_german.txt` without overriding each other.

The `#` character is removed from the start of tokens, and tokens that start with `[english]` are ignored by the game (they are used by the translation synchronization tool to know if a string's original value has changed).

The `statsweb` files use formatting syntax from [Go's `fmt` package](https://pkg.go.dev/fmt#hdr-Printing), but most files use Source Engine's string formatter, which uses `%s1` for the first placeholder, `%s2` for the second, and so on.

## Mail, News, and Credits

Text shipped with Alien Swarm: Reactive Drop that is not stored in one of the token files described above is generally stored with one language per file. For example, `scripts/asw_credits.txt` is loaded by default, but can be overridden by `scripts/asw_credits_russian.txt` if the game's language is set to Russian. Mail and news files use the `_english` version of the file as a fallback. All three of these file formats are VDF-based (KeyValues).

```
"Credits"
{
	// All keys are optional, but MUST be in this order.

	// This is the default; if you wish to hide the logo, set this value to 0.
	"show_credits_logo"		"1"

	// This is the default. Other than Jacob's Rest, all content should use its own logo.
	// Whether that is a campaign-specific logo or a developer's logo is up to that developer.
	// Path is relative to materials/vgui.
	"custom_logo"		"../console/valve_logo"

	// Each line of the credits is listed as follows. The key name isn't actually checked,
	// but it should be consistent in case it is ever checked in the future.
	"asw_credits_"		"Line 1"
	"asw_credits_"		"Line 2"
	// ...
}
```

Both mail and news items are limited to 4 paragraphs. If you need more space, you can insert line breaks into your strings, but splitting a long message into multiple emails or news items or editing it down is preferred.

```
"News"
{
	// The headline of the news article.
	"Headline"		"Example News Article"

	// The date of the news article is in MM/DD/YY format for English.
	// Check existing translations for other languages for their format.
	"HeadlineDate"		"12/15/52"

	// There can be up to 4 paragraphs in a news article.
	"Paragraph1"		"First line of text."
	"Paragraph2"		"Second line of text."
}
```

```
"Mail"
{
	// PDA belongs to Example Person

	// inbox

	"MailFrom1"	"From: Coworker Name"
	"MailDate1"	"Date: 12/19/52"
	"MailSubject1"	"Subject: First inbox message subject line"
	"MailBody1A"	"First line of text."
	"MailBody1B"	"Second line of text."
	"MailBody1C"	"Third line of text."

	// sent mail

	"MailFrom3"	"To: Coworker Name"
	"MailDate3"	"Date: 12/19/52"
	"MailSubject3"	"Subject: First sent message subject line"
	"MailBody3A"	"First line of text."
	"MailBody3B"	"Second line of text."
	"MailBody3C"	"Third line of text."
	"MailBody3D"	"Fourth line of text."

	// Mails 1 and 2 are in the inbox, 3 and 4 are in sent mail.
	// Dates use MM/DD/YY format in English.
	// There can be up to 4 paragraphs in each email.
}
```

## External Translations

Some translated text is not part of the game. These files are manually uploaded or copied by project admins, and generally consist of a template file that gets copied and translated to each langauge.
