# Cameron's Exceptional Emacs

### ORG

Only plugins I have right now for org mode, are org bullets, and some smaller
things

### IDO

IDO is always enabled, and it will create a new buffer when called

IDO is vertically shown, which is nice, you can scroll through with C-n and C-p

Smex allowed you to launch smaller commands with an IDO mode like interface, its quite nice

For some reason I have switch buffers set to C-x b, this pulls up ido switch buffer

### EXWM

I don't use EXWM and I don't think I will but it's still a nice and cool package to have installed for the future

### Special Keybinds

Here are just some of the various special keybindings and things not large enough for their own section

##### open terminal
s-return opens up *vterm* a terminal replacement inside emacs that's quite good

##### subword
i forget what this does

##### electric
This sets up which items I want to be paired, right now I have `(),[],{},""
,''` paired up


### Special Files

##### set default shell to bash
why is this in here? who knows

##### remove backup file creations
These are ugly and clutter up my filesystem. I do not need them as I use git for version control (sometimes)

### Making Nice Lookings

You may be asking yourself, why is it called this? I do not know

#### Window system
Here we enable hl-line-mode (idk)
Here we enable prettify symbols mode, I might remove it

#### yes-or-no
makes the alias yes-or-no-p to y-or-n-p, because typing 'yes' and 'no' every single time you want to confirm something is annoying

#### Most basic of changes

Because it's so basic, i'll just leave it here like this, the source

#+BEGIN_SRC emacs-lisp
(tool-bar-mode -1)
;; I leave the menubar and disable the scrollbar
(menu-bar-mode 1)
(scroll-bar-mode 0)
(setq inhibit-startup-message t)
;; Turns off the bell
(setq ring-bell-function 'ignore)
(show-paren-mode 1)
;; This extends how much is stored in the kill ring
(setq kill-ring-max 100)
#+END_SRC

#### show lines and columns on modeline
I like the emacs modeline. A lot. So now I can see what line, and column i'm in right there? Sounds pretty good to me. I also use `linum-relative` for my programming mode buffers which helps aswell.

#### show clock
I show the time in 24 hour format in the modeline, this isn't really necessary since I have it (down to the second) in my statusbar

#### pretty symbols
I should disable this, it confuses me in programming modes becauase in and def are changed to symbols which confuses my small brain

### Small Packages

#### beacon
Highlights cursor when you open the buffer

#### which-key
This gives a prompt in the minibar to see what each key does when you are typing, ie what possible commands C-c .... could give you

#### sudo-edit
This is great, and my biggest issue with VIM. I would try and edit files not owned by me, and after a solid 15 minutes when I tried to save, I was unable to. Super-e to edit the file as sudo

#### symon
This is cool, shows system resources in minibuffer when enabled with Super-h

#### popup-kill-ring
This opens the kill ring with M-y

#### linum-relative
This shows the line number of current line, and other lines branching out from the main line. A bit heavy, and only enabled in prog mode for speed.

#### async
This supposedly allows multiple processes with emacs, so now core 0 doesn't get obliterated

#### expand-region
I don't remember what this does

#### indent-guide
This is supposed to make indents nice and easier to see when programming, maybe this will make lisp easier for people? who knows

## vterm

for me this replaces ansiterm, and my great colourscheme is used here aswell! I have a nice terminal all within emacs! I never have to leave. Ever.

## dashboard

This replaces the default startup for Emacs, and a great banner title to boot

## modeline

This makes the modeline nicer, it's already nice, but now it's nicer :)

#### spaceline
This is spacemacs modeline, spacemacs is extremely heavy, but this package is just fine for me to eat up

#### diminish
This hides rubbish modes from my modeline that I have on, but don't need to see all the time.
So far, they are

* beacon-mode
* subword-mode
* rainbow-mode
* which-key-mode
* org-indent-mode

## buffers

#### kill all buffers
I have a keybinding to kill all buffers open from my emacs session. I usually have anywhere from 5 to 30 buffers, and its a pain to kill all of those buffers with C-x k, the selection I have is `C-M-s-k`

#### ibuffer
this is a seperate buffer selection screen, `C-x C-b`

## avy

I have `M-s` bound to get avy to goto char, and `C-;` to goto line, I can't think of a good way to explain avy, other than "WOAH" it really helps me jump around lines even faster than VIM let me, and its easier than spamming a massive ammount of `C-u (x) C-f`

## dmenu

Yes, you can use dmenu in emacs. why? because.
`s-SPC` activates the dmenu to popup and you can launch programs. sweet.

## rainbow

This makes colour codes showup as that colour itself in progmode buffers, and also the colours of matching delimiters which makes lisp and stuff way easier.

## hungry-delete

This package makes me MAD. I don't webdev, but I do a lot of machine vision in Python lately, Python, relies entirely on spaces and tabs for its indentation. This deletes all whitespace behind it when you press entire twice. I have it disables but you could enable it if you want.

## helpful

This essentially improves the built in emacs help commands and I quite like it, I never really liked the built in help, and this drastically improves it. I replaced the default emacs keybinds with this

## swiper

This makes searching way better, it opens up a minibuffer with all the different places you can hop too. I have replaced the default search command `C-s` with this

## mark-multiple

I forget what this does aswell, `C-c q` to activate whatever it is

## switch-window

This is cool, I usually have at max 3 windows in Emacs open at a time, but spamming `C-x o` is a massive pita, so this way you can switch between windows by pressing a key on the homerow when you have more than 2 windows open that corresponds to the window. It's much simpler than my explanation in practice

## Auto Completion

I'm not a big IDE guy, I really dislike the bloat and lack of my nice Emacs keybinds. Sometimes though, I like auto completion. I actually fell in love with auto-completion when I was writing essays in google docs, the dumb autocompletion they implemented really sped up writing essays, so why not add that to my code?

### company

This is the main leader of auto completion, everything else kinda piggybacks off of this. Its ok. Right now I have C, CPP and Arduino auto completion working but I want to add more

### company-irony

company plugin that adds support to Irony, which is the CPP and C backend for auto complete that uses CLANG

### irony

Irony, see above.

### company-arduino

Supposedly auto-completes some arduino functions and the like with company. This is nice as I love the arduino platform

### Company jedi

I do not understand python VENV and that is integral to getting this bloody thing to work

### anaconda-mode

This is in the hopes that I one day get python auto complete to work, one day...

### company-anaconda

adds anaconda support to company

## MAGIT

Supposedly the "killer app" for Emacs. It's very good, but you require a strong working knowledge of GIT to get the most out of it. I, do not have that, so it's a bit complicated for me

## Window splitting functions

`C-x 2` to split the current window horizontally, and `C-x 3` to split it vertically. It creates a new window with the currently open buffer.

## convenient functions

#### kill-whole-word
`C-c w w` kills the, whole word that you are in

#### copy-whole-line
`C-c w l` copies the entire line into the ring

#### indent block of text
`C->` indents selected text by one tabspace. Great for python when you mess up

## config edit/reload

#### edit
`C-c e` opens up the config file

#### reload
`C-c r` reloads the config file

## macros

I have no macros so far.



