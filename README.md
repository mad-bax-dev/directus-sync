# Directus Schema Sync Panel

A beautiful, modern web-based panel for synchronizing Directus schema between instances. This tool allows you to sync your main Directus instance schema to multiple branch instances with an intuitive dark-themed interface.

## Features

- 🎨 **Modern Dark Theme** - Beautiful GitHub-inspired dark mode interface
- 🔄 **Schema Synchronization** - Sync schema from main Directus to multiple branches
- 📊 **Real-time Progress** - Track sync progress with detailed step indicators
- 🔁 **Resume on Error** - Automatically resume from failed steps without restarting
- 📋 **Snapshot Viewer** - View complete schema snapshot in a modal
- ⚡ **Error Handling** - Comprehensive error reporting with detailed messages
- 🎯 **Smart Diff Detection** - Handles 204 No Content responses (no changes detected)

## How It Works

1. **Get Snapshot** - Retrieves the complete schema from your main Directus instance
2. **Calculate Diff** - For each branch, calculates the differences between main and branch schemas
3. **Apply Changes** - Applies the schema changes to each branch instance

## Usage

1. Open `index.html` in your web browser
2. Enter your **Main Directus** URL and Access Token
3. Add **Branch Directus** instances (URL + Access Token for each)
4. Click **Start Sync** to begin the synchronization process
5. Monitor progress in the right panel
6. Use **Retry** button on failed branches to resume from the point of failure

## Requirements

- Modern web browser (Chrome, Firefox, Edge, Safari)
- Access to Directus instances with schema API endpoints
- Valid access tokens with schema read/write permissions

## API Endpoints Used

- `GET /schema/snapshot?export=json&access_token={token}` - Get schema snapshot
- `POST /schema/diff?force=true&access_token={token}` - Calculate differences
- `POST /schema/apply?access_token={token}` - Apply schema changes

## Features in Detail

### Smart Error Recovery
- If a step fails, you can retry that specific branch
- Completed steps are preserved and won't be re-executed
- Handles 204 No Content responses gracefully (no changes detected)

### Progress Tracking
- Visual step indicators (Diff, Apply)
- Color-coded status badges (Success, Error, Processing, Pending)
- Detailed error messages with stack traces
- Click on steps to view detailed information

### Snapshot Viewer
- View the complete schema snapshot in a modal
- Formatted JSON display for easy inspection

## License

MIT License - see [LICENSE](LICENSE) file for details

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Author

Developed by [mad-bax-dev](https://github.com/mad-bax-dev)

---

**Note**: This tool requires direct access to your Directus instances. Make sure your access tokens have the necessary permissions for schema operations.

