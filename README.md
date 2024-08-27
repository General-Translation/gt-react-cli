# gt-react-cli

A CLI tool for processing React dictionary files and sending translations to General Translation services.

## Installation

### Global Installation

To install the `i18n` CLI tool globally using npm, run:

```bash
npm install -g gt-cli
```

This will make the `i18n` command available globally on your system.

## Usage

### Update Command

The primary command is `update`. This command processes a React dictionary file and sends the translations to General Translation services.

#### Basic Usage

Once installed globally, you can run the command:

```bash
i18n update dictionary.js --apiKey YOUR_GT_API_KEY --projectID YOUR_GT_PROJECT_ID --languages en fr es --override
```

- `dictionary.js`: Path to the dictionary file you want to process.
- `--apiKey`: Your General Translation API key.
- `--projectID`: Your General Translation project ID.
- `--languages`: A list of languages you want to target for translation.
- `--override`: (Optional) Specify this flag to override existing translations.

### Example

```bash
i18n update ./src/dictionary.js --apiKey YOUR_GT_API_KEY --projectID YOUR_GT_PROJECT_ID --languages en fr de --override
```

This command will process the `dictionary.js` file, target English, French, and German for translation, and send the results to the General Translation service.

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
