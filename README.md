![](https://github.com/Pawel-Albert/utilities-for-testing-extension/blob/main/%F0%9F%92%BButylis%E2%9A%99%EF%B8%8F.png)

# Google chrome extension with a couple of small functionalities for testers in the form of context menu

## Project Description

The project is a chrome extension in the form of a context menu (available via right mouse button) - mostly niche and company-specific functionalities. The project was written in vanilla Javascript, bundled with Parcel. This project heavily uses already written code from https://github.com/Pawel-Albert/test-data-generators. The purpose of the project is to provide an actual utility tool for personal and team usage while practicing building chrome extensions.

## Installation

### Clone

Clone this repo to your local machine using

```shell
git clone https://github.com/Pawel-Albert/utilities-for-testing-extension.git
```

### Setup

Type in terminal

```shell
$ npm install
$ npm run build
```

A folder "dist" should be created. Go to chrome://extensions/. While in developer mode use "load unpacked" extension option and choose "dist" folder. Extension now is ready to use (remember to allow for use in incognito mode if needed).

## Features

All features are available in the context menu, organized into logical groups. After right-clicking, hover over TesterUtilities to see the following groups:

### Data Generators

- "Generate PESEL (18+)" - Generates valid Polish PESEL number (for adults)
- "Generate IBAN" - Generates valid IBAN number
- "Generate ID number" - Generates valid Polish ID number
- "Generate PASSPORT number" - Generates valid Polish passport number
- "Generate valid PL mobile phone" - Generates valid Polish mobile phone number
- "Generate valid PL NIP" - Generates valid Polish NIP (tax identification number)
- "Generate valid PL REGON" - Generates valid Polish REGON number

### Text Tools

- "Generate Counter String" - Generates a counter string with specified length
- "Generate Lorem Ipsum" - Generates Lorem Ipsum text with specified length
- "Multiply Text in Lines" - Multiplies given text in multiple lines with specified parameters
- "Generate Text Pattern" - Generates various text patterns based on input text

### Form Tools

- "Remove all 'disabled' attributes" - Removes all disabled attributes from form elements
- "Clear all input restrictions" - Removes typical input restrictions
- "Change all inputs type from password to text" - Converts password fields to text fields
- "Highlight elements with same ID" - Highlights elements with duplicate IDs
- "Highlight and show all 'display none' elements" - Shows hidden elements

### Form Fillers

- "Simple form filler - default site" - Auto-fills forms on default site (Alt+2)
- "Simple form filler - custom sites" - Auto-fills forms on custom sites (Alt+3)

To configure form fillers for your sites, you can extend the `siteSelectors` configuration. Here's an example:

```javascript
const mySiteData = {
  // Configuration for specific site
  'mySite1.com': {
    username: {
      selector: 'input[name=username]',
      type: 'input',
      data: myFakeData.username
    },
    password: {
      selector: 'input[name=password]',
      type: 'input',
      data: myFakeData.password
    }
    // Add more fields as needed
  },

  // Configuration for another site
  'mySite2.com': {
    email: {
      selector: 'input[name=email]',
      type: 'input',
      data: myFakeData.email
    },
    password: {
      selector: 'input[name=password]',
      type: 'input',
      data: myFakeData.password
    }
    // Add more fields as needed
  },

  // Default configuration used when no specific site match
  default: {
    username: {
      selector: 'input[name=username]',
      type: 'input',
      data: myFakeData.username
    },
    password: {
      selector: 'input[name=password]',
      type: 'input',
      data: myFakeData.password
    }
    // Add more fields as needed
  }
}
```

Each field configuration requires:

- `selector`: CSS selector to find the element
- `type`: Type of element ('input' for input fields)
- `data`: Data to be inserted (can use predefined fake data or custom values)

### Console Tools

- "JSON prettier via console" - Formats JSON and prints to console
- "Timestamp to date" - Converts timestamp to readable date
- "Base64 decode and print to console" - Decodes Base64 string
- "Base64 encode and print to console" - Encodes string to Base64

### Domain Tools

- "Switch domain" - Switches between domains (Alt+1) - Company-specific feature, currently configured only for internal company domains. To use it for different domains, the configuration needs to be modified in the source code.

## Configuration

The extension now includes configuration options for both form filling and text generators, accessible through the extension's options page:

### Form Filler Settings

- User Prefix - Custom prefix for generated usernames (default: testLendi)
- Email Domain - Custom domain for generated email addresses (default: gmail.com)

### Text Generator Settings

- Lorem Ipsum default length - Default length for Lorem Ipsum text (default: 100)
- Pattern Generator default text - Default text for pattern generation (default: test)
- Pattern Generator default length - Default length for generated patterns (default: 1000)
- Text Multiplier default text - Default text for multiplication (default: sample text)
- Text Multiplier default lines - Default number of lines (default: 3)
- Text Multiplier line length - Default length of each line (default: 50)
- Counter String default length - Default length for counter string (default: 100)

All settings are persistent between browser sessions and can be modified at any time through the extension's options page.

## Recent Updates

### Version 0.2.9

- Added new text generation tools with configurable defaults
- Reorganized context menu into logical groups
- Added persistent settings for all text generators
- Improved project structure with centralized configuration
- Enhanced user experience with customizable default values

## Todo

- [x] Form auto filler with random data
- [x] Fix Generate functions, as currently they are not registered by browser as user actions
- [x] Add basic configuration for form filling (user prefix, email domain)
- [x] Add text generator configuration options
- [x] Organize context menu into logical groups
- [ ] Add more configuration options based on user feedback
- [ ] Implement more "quality of life" improvements based on user requests

## Polityka Prywatności / Privacy Policy

**TesterUtilities - Rozszerzenie dla Testowania**

TesterUtilities nie zbiera ani nie przechowuje żadnych danych osobowych użytkowników. Rozszerzenie służy wyłącznie jako narzędzie pomocnicze do uruchamiania skryptów testerskich. Nie przekazujemy, nie przetwarzamy ani nie przechowujemy żadnych informacji dotyczących użytkowników tego rozszerzenia.

W razie dodatkowych pytań proszę o kontakt.

---

**TesterUtilities - Testing Extension**

TesterUtilities does not collect or store any personal user data. This extension serves solely as a utility tool for running testing scripts. We do not transmit, process, or retain any information about the users of this extension.

For any further questions, please feel free to contact me.
