# HTML markup formatter

A simple, single-page HTML formatting tool for turning messy or poorly indented HTML into cleaner, easier-to-read markup.

The tool is designed especially for cases where the original HTML needs to be preserved for testing or review. It formats the source without trying to repair invalid markup, add missing elements, reorder attributes, or otherwise change the underlying structure.

## What it does

Users can either:

- paste raw HTML into the app, or
- upload an `.html` or `.htm` file.

The tool then reformats the source with consistent indentation and sensible line breaks.

HTML structure is preserved as closely as possible, including malformed or unusual markup.

## Features

- Single self-contained HTML file
- No external libraries or dependencies
- Paste HTML directly into the app
- Upload `.html` and `.htm` files
- 2-space, 4-space, or tab indentation
- Preserves attribute order
- Preserves single and double quotes
- Preserves duplicate attributes
- Does not add missing tags or repair invalid markup
- Keeps inline content together where practical
- Formats CSS inside `<style>` elements
- Formats JavaScript inside `<script>` elements
- Preserves significant whitespace inside `<pre>` and `<textarea>`
- Preserves HTML comments and conditional comments
- Copy formatted HTML to the clipboard
- Download the formatted HTML as a file
- Keyboard shortcut: `Cmd/Ctrl + Enter` to format
- Does not render or execute the HTML being formatted

## Why it does not use the DOM

Browser HTML parsers automatically repair some invalid markup. That behaviour is useful when displaying web pages, but not when the purpose of the tool is to inspect or test the original source.

For example, a DOM-based formatter may silently:

- insert missing elements
- correct invalid nesting
- normalise markup
- change the structure being tested

This formatter instead works directly with the source text and tokens. Its goal is to improve readability without intentionally changing the HTML itself.

## How it was built

The app is written entirely in:

- HTML
- CSS
- vanilla JavaScript

All CSS and JavaScript are embedded directly in the HTML file, so the tool can be downloaded and run locally without a build process, server, package manager, or internet connection.

The HTML formatter uses a lightweight source/token-based approach rather than converting the document into a browser DOM. Embedded CSS and JavaScript are formatted conservatively, while content where whitespace can be meaningful is left untouched.

## Running the tool

Download or clone the repository, then open the HTML file directly in a browser.

No installation or setup is required.
