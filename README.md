# blazor-test

A simple Blazor Web App (.NET 8, Interactive Server) that counts the words and characters in a text field.

## Run

```bash
cd WordCountApp
dotnet run
```

Then open the URL printed in the console.

## Reviewing the running app from a mobile session

The Claude mobile app doesn't offer a preview pane or a way to open ports from the
cloud container, so you can't browse the running app directly. Instead, ask Claude to
record the app with a headless browser (Playwright is pre-installed in the cloud
container) and send you the results. This worked well for reviewing this app:

- **Screen recording (`.webm`)**: a video of the whole flow (typing, live count updates,
  Clear). Best for seeing how the app behaves.
- **Screenshots (`.png`)**: individual states, e.g. empty, typing, with text, cleared.

Example prompt: *"Run the app, then send me a screen recording and screenshots showing it
working."*

Under the hood, Claude starts the app (`dotnet run --urls http://0.0.0.0:5080`) and
drives it with Playwright, using `recordVideo` for the video and `page.screenshot()` for
the images. The files are sent to the session rather than committed to the repo.
If a `.webm` doesn't play in your viewer, ask for a GIF or MP4 instead, or use the
screenshots.
