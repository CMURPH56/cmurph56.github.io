# One Month With Sublime

This year, I decided to switch from Visual Studio Code to Sublime Text Editor, partially inspired by this [blog post](https://ohdoylerules.com/workflows/why-i-still-like-sublime-text-in-2025/).


### Packages I Installed

One of the first things I realized is the out of the box experience with Sublime is pretty bare bones. I had to install some plugins just to get to a regular Visual Studio Code experience.

#### [Terminus](https://packagecontrol.io/packages/Terminus)

This was the first package I installed. One of the features I really liked about Visual Studio Code was the integrated terminal. As a single-monitor user, it was nice not to have to switch back and forth between windows.

#### [LSP](https://lsp.sublimetext.io/language_servers/)

This package comes highly recommended for all new Sublime users, and through it, I learned what the [Language Server Protocol](https://en.wikipedia.org/wiki/Language_Server_Protocol) is. It essentially creates an open standard for languages to have syntax highlighting and code completion in any text editor that implements it. Thanks to Visual Studio Code and Microsoft for creating and opening that up. For Rust specifically, I installed [LSP-Rust-Analyzer](https://github.com/sublimelsp/LSP-rust-analyzer).

#### [LSP-Copilot](https://github.com/TerminalFi/LSP-copilot)

I didn’t want to miss out on the free-tier GitHub Copilot that was being offered. This package provides that functionality. However, it is not a drop-in replacement. I will elaborate more on this in the **Struggles** section.

#### [Rust Enhanced](https://github.com/rust-lang/rust-enhanced)

I worked with this one for a bit, but it was just too noisy. I didn’t like how it shifted around all my code on save. I ended up uninstalling it and relying on LSP-Rust-Analyzer for my linting and syntax highlighting needs.

### Struggles

It does not "just work."

##### Conflicting Packages

An example of this clash is the LSP-Copilot plugin and the Terminus package. In Sublime, Terminus pins the terminal to the bottom of the editor. The Copilot Chat window is also at the bottom of the editor. When Copilot Chat is open, the terminal disappears, and vice-versa. 

This contrasts with Visual Studio Code, where the in-editor terminal is a default feature pinned to the bottom, and Copilot Chat is neatly placed on the right side of the editor. Additionally, GitHub Copilot generally works better in Visual Studio Code.


### Takeaways

Learning a similar tool helped me understand both tools better. Using Sublime requires frequent use of the Command Palette, triggered by `Ctrl+Shift+P`, which is something I didn’t use as often in Visual Studio Code because it wasn’t necessary. However, this experience gave me a better appreciation of how powerful that tool is in Visual Studio Code.

### Conclusion

Will I stick with Sublime?
I waffled on this, but I think I am going back to using Visual Studio Code. I know that I could spend more time with Sublime and tailor it more to my workflow. However, I would rather keep the complexity focused on my work.