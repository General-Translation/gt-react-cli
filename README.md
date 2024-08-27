# gt-react-cli

A CLI tool for processing React dictionary files and sending translations to General Translation.

## Installation

### Global Installation

To install the `i18n` CLI tool globally using npm, run:

```bash
npm install -g gt-react-cli
```

This will make the `i18n` command available globally on your system.

## Usage

#### Basic Usage

Once installed globally, you can run the command:

```bash
i18n dictionary.js
```

- `dictionary.js` (Optional): Path to the dictionary file you want to process. If not provided, the tool will look for a `dictionary.js` file in the root and `src` directories.
- `--languages` (Optional): A list of languages you want to target for translation. If not specified, the tool will process all existing languages in the dictionary file (but no additional languages will be added).
- `--override` (Optional): Specify this flag to override existing translations.

### Example

```bash
i18n update ./src/dictionary.js --languages fr es de
```

This command will process the `dictionary.js` file, target French, Spanish, and German for translation, and send the results to the General Translation service.

### Default Paths

If you do not provide a dictionary file path, the tool will look for a dictionary file in the following default locations:

- `./dictionary.js`
- `./dictionary.jsx`
- `./dictionary.ts`
- `./dictionary.tsx`
- `./src/dictionary.js`
- `./src/dictionary.jsx`
- `./src/dictionary.ts`
- `./src/dictionary.tsx`

If no file is found, the command will throw an error.

## Environment Variables

This tool also supports environment variables for the API key and project ID. You can define them in `.env` or `.env.local` files:

```env
GT_API_KEY=your_api_key
GT_PROJECT_ID=your_project_id
```

If these environment variables are set, you do not need to provide the `--apiKey` and `--projectID` flags in the command.

## License

ISC