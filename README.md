# Stardew Valley Mod Template

.NET CLI command for creating Stardew Valley mods.

## Description

This is a `dotnet new` template for quickly setting up a new Stardew Valley ([SMAPI](https://smapi.io)/C#) mod using the most common configuration and structure:

- Solution root folder containing:
  - README file for the mod, pre-populated with a basic outline
  - Open-source license (MIT)
  - Changelog in the [Keep A Changelog](https://keepachangelog.com/en/1.1.0/) format
  - Git metadata to keep your repository clean
- Project directory for the actual mod:
  - Manifest JSON, pre-filled with your author and mod name info (see [Usage](#usage)), and an optional dependency on [Generic Mod Config Menu](https://www.nexusmods.com/stardewvalley/mods/5098) since most mods use it;
  - Mod project and `ModEntry` class;
  - Empty `ModConfig` type that is automatically loaded in `ModEntry`;
  - Localization support provided by `ModTranslationClassBuilder`, with example `default.json`;
  - A handful of global usings/aliases for the most common ambiguous types (`System.Object` vs. `StardewValley.Object`, XNA's `Rectangle` and `Vector2` types);
  - Ready to build using `ModBuildConfig.`

Does not include any editor configs, stylecop settings, IDE settings or other choices that are largely personal preference. Feel free to fork this repository and customize further for your own workflow!

## Installation

- Download the `.nupkg` file from the [latest release](https://github.com/focustense/StardewModdingTemplates/releases).
- Install it with the command: `dotnet new install <path_to_downloaded_file>.nupkg`

## Usage

Run the following command:

```cmd
dotnet new stardewmod -n <ModName> -au <AuthorName>
```

Explanation of parameters:

- `ModName`: The name of the mod; this value will be used as the solution and project names, assembly (DLL) name, manifest name, readme title, sample links in changelog, etc.
- `AuthorName`: Your username, e.g. on GitHub, Nexus Mods, etc. This will be referenced in the mod manifest and some documentation files such as the license.

The unique ID of the mod will be `<AuthorName>.<ModName>`, e.g. `focustense.TestMod`.

Don't put spaces or special characters in either of these names; they aren't compatible with the mod build system.
