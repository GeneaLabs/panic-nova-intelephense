# Intelephense
[Intelephense](https://intelephense.com) runs any time you open a local PHP
  project, automatically lints all open files, then reports errors and warnings
  in Nova's **Issues** sidebar and the editor gutter.

![](https://nova.app/images/en/dark/tools/sidebars.png)

### Prerequisites
- installation of NPM on your system, for example `brew install npm`.

## Features
Further features, as listed on the Intelephense website (), include:

✅ Currently implemented by Nova natively or through this package.
☑️ Limited functionality.
⛔️ Currently not implemented.

| Implemented | Feature | Description |
| ----------- | ------- | ----------- |
| ✅ | Code Completion | Fast camel/underscore case context aware suggestions _with automatic addition of use declarations_. |
| ✅ | Signature Help | View detailed parameter hints for call expressions. |
| ✅ | Jump to Definition | Quickly navigate to symbol definitions. |
| ✅ | Find in Project | Quickly find symbol references within the workspace. |
| ☑️ | Symbol Search | Fast camel/underscore text search for workspace and document symbol definitions. **In Nova this is included in the "Find in Project" functionality.** |
| ✅ | Linting | Error tolerant parser and powerful static analysis engine report problems as you type. |
| ⛔️ | Formatting | PSR12 compatible full document and range formatting. **This does not appear to be available in Nova at this time.** |
| ✅ | Embedded Language Support | Includes HTML/JS/CSS code intelligence too. |
| ✅ | Hover | Detailed hover information with links to official PHP documentation. |
| ⛔️ | Highlight | Smart highlighting of references and keywords. **I don't believe this is currently supported in Nova, or it may be theme-dependent.** |
| ✅ | Sending configuration to LSP | From the Extension Preferences tab, configure directly the [parameters to pass on to Intelephense](https://github.com/bmewburn/intelephense-docs/blob/master/gettingStarted.md). |

### Premium-Only Features
Currently the premium features of [Intelephense](https://intelephense.com) do
  not appear to be functional in Nova. However, we still encourage you to
  support Ben Mewburn by purchasing a license.

## Configuration

<!--
🎈 If your extension offers global- or workspace-scoped preferences, consider pointing users toward those settings. For example:
-->

To configure global preferences, open **Extensions → Extension Library...** then select intelephense's **Preferences** tab.

You can also configure preferences on a per-project basis in **Project → Project Settings...**

Finally, note that the additional preferences found on the **Preferences** tab relate to Intelephense-specific configurations. See Ben Mewburn's [own explanations](https://github.com/bmewburn/intelephense-docs/blob/master/gettingStarted.md) for further information on what each option does.

## Caveats

During activation, this extension will attempt to deploy on the workspace a fully functional (and independently managed) installation of Intelephense; you will need to have `npm` installed (you can get it with `brew install npm`).

In some circumstances (under investigation!), `npm` may fail to create the directories it needs (notably, `node_modules`) in the place where Nova (and, later, Intelephense) expects them; as a consequence, the LSP will fail with a console error that might not be easy to debug — since it depends quite a lot on how you are currently managing `npm`, both at the global as well as the local level.

This step may require some improvement in the future; alternatively, there might be a choice to use the _global_ installation of `npm` instead, or, if you have one local `npm` installation in your current PHP project, this extension might attempt to use it. Such options will require a few new options on the Preferences panel; stay tuned...

<!--
👋 That's it! Happy developing!

P.S. If you'd like, you can remove these comments before submitting your extension 😉
-->

## Credit
- Primary credit goes to Ben Mewburn, who developed the
  [Intelephense](https://intelephense.com) language server, which this extension
  uses to provide auto-complete and other LSP features in order to bring Nova on
  par with modern PHP development.
- I would like to thank
  [Kristófer Reykjalin](https://extensions.panic.com/extensions/com.thorlaksson/)
  for inspiration and debugging many of the same errors I have run into ahead of
  me in various github issues. He has spent a lot of effort in creating an
  Intelephense extension for Nova, and the only reason I started working on my
  own extension is because I had some trouble getting his extension to work in
  my projects. As I am finding out now, this is probably not a problem on his
  end, but rather upstream from the Intelephense package. I needed to get
  Intelephense working quickly in order for me to be able to use Nova as a
  primary driver.
- Additional thanks to [John Fieber](https://devforum.nova.app/u/jrf/) for his
  extensive explanation on how exactly Nova passes configurations to the LSP
  (and answers its requests).