# [VAPOR] Journey
The journey language

# Features
## Non goals
### Low level

  By giving up low level control, journey can be runned parallely without any hassle

### Extreme performance

  To squeeze the last bit of your performance, you have to use a low level language. Since low-level is non-goal, we can't guarantee you can squeeze the last bit of performance

### Compile time

  I decide to implement both a compiler and a interpreter(with JIT) for Journey, there would be no need to optimize on compile time.

### Extreme optimization

  So with so many feature in my mind, it's actually impossible to optimize the last bit out. e.g. you have to keep a symbol table in memory when using common lisp other wise how can you rewrite the function in runtime?

## Goals
### Extensibility
  The biggest goal here is to design a language suitable for prototyping, or so-called "explorative programming". 
  I expect the follow to be possible with Journey
  - send code between machine to execute the code
  - modify the software itself when it's running

### Robustness 
  As we learn from history, one of the reason Perl/TCL/Bash is dying out/hated is that they are not suitable for writing robust softwares. They are super extensible, though. The problems lies in the fact that achieving both robustness and robustness is hard, so we definitely need to find a way to alleviate that pain. 

### Responsive
  One of the main reason I designed this language is I want to write tool for "hackers"(by which I don't mean crackers), this language should be a perfect tool to write softwares like vim, emacs. Think of journey language as a equivalence of (c + lua) without hassle to design any interface in this aspect

### Start up time
  One of the reason I don't like Clojure&Emacs is the start up time. So I definitely want to fix that.

# Implemention details

## Why zig?
 Compiler should better be implemented in low level so that we have good enough performance. Zig is easy to cross platform, and extremely easy to use C libraries. Apart from them, zig have cool comptime feature to help me keep the code clean. I think that's enough reason for me to use Zig.
