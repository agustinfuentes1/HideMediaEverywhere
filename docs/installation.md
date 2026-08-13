# Installation and updates

HideMediaEverywhere runs as a Vencord userplugin and requires a Vencord source build.

## Before you start

Install Vencord from source by following the [official source installation guide](https://docs.vencord.dev/installing/). The Vencord folder should contain `package.json`, `pnpm-lock.yaml`, and a `src` folder.

Place this plugin in `src/userplugins`, the folder Vencord uses for custom plugins. Do not place it in `src/plugins`.

## Install the plugin

Open a terminal in the root of your Vencord source folder and run:

```sh
git clone https://github.com/t6rtar/HideMediaEverywhere.git src/userplugins/hideMediaEverywhere
pnpm build
```

Then apply the custom build to your client:

### Discord desktop

Run `pnpm inject`, select the Discord installation you use, and finish the installer. Quit Discord from its tray icon, then reopen it.

### Vesktop

Open **Vesktop Settings**, find **Vencord Location**, and select the `dist` folder inside your Vencord source folder. Quit Vesktop from its taskbar or tray icon, then reopen it.

### Browser build

Run `pnpm buildWeb` instead of `pnpm build`, then install the generated browser extension or userscript using the instructions in Vencord's source installation guide.

After restarting, open **Settings > Vencord > Plugins**, search for **HideMediaEverywhere**, and enable it.

## Update

From the root of your Vencord source folder:

```sh
git -C src/userplugins/hideMediaEverywhere pull --ff-only
pnpm install --frozen-lockfile
pnpm build
```

Use `pnpm buildWeb` for a browser build. Reapply or reselect the build if your client requires it, then quit and reopen the client.

## Remove

Disable **HideMediaEverywhere** in Vencord first. Delete `src/userplugins/hideMediaEverywhere`, rebuild Vencord, then quit and reopen the client.

Removing the plugin does not modify Discord messages. Its saved settings may remain in Vencord's local settings until you clear them.

## Troubleshooting

### The plugin does not appear

- Confirm the file is at `src/userplugins/hideMediaEverywhere/index.tsx`.
- Confirm you rebuilt the same Vencord checkout that your client loads.
- Quit the client from its tray or taskbar icon instead of closing its window.
- Check the build output for a TypeScript or dependency error.

### A build fails after updating Vencord

Run `pnpm install --frozen-lockfile`, then rebuild. If the error points to `hideMediaEverywhere/index.tsx`, copy the full error into a GitHub issue.

### Media appears in one Discord view after you hide it

Include the media type and location in the bug report: regular chat, search results, image preview, GIF picker, or another view. Discord uses a separate renderer for each view.

### The plugin misses a renamed or reposted file

Image matching requires access to the file content. Video matching may use the Discord attachment filename when Discord re-encodes the file. Include whether someone uploaded the file again, renamed it, or posted it in another channel.

### Filename tooltips do not appear

Keep Vencord's `ImageFilename` plugin enabled. After rebuilding, quit and reopen the client so Vencord reloads both plugins.

## Getting help

Open an issue in this repository. Remove private server names, usernames, message text, and personal media from screenshots or logs.
