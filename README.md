# Static Lite

Static Lite is a template for generating static sites, powered entirely by NPM scripts.

## The Argument

Static Lite is a traditionalist approach to a static site compiler.  This setup is powered entirely by NPM Scripts, whose usage is analogous to the more traditional Makefile.

There are many Javascript build systems out there that attempt to streamline build processes.  Most of these are quite complicated and configuration can get out of control very quickly.  Others are far too opionated and make it very complicated to make your own.  Generating static sites is actually not all too complicated of a process, and all of the tools that are needed to generate one provide more than sufficient CLIs.

If we take a few steps back in time to Makefiles, we find that it is quite the perfect tool for the job.  With a minimal amount of code ([take a peek](https://github.com/BrandonRomano/static-lite/blob/master/package.json#L36-L48)), we are able to have a complete static site build system, with absolutely no framework needed.

The best part about this setup is that you don't have to dig very deep to understand what is going on.  There is no magic, and everything is exposed to you in NPM Scripts.  If you don't like a specific part of this build process, change it; it will probably only be a single line of code.  Nothing about this setup mandates that you take it as is; switch out stylus for PostCSS, switch out Pug for that old version of Jade your company still uses.

Makefiles are still as viable as ever, this is purely a concrete example to illustrate that point.

## Getting Started

Run the following, and watch the magic happen:

```
git clone https://github.com/BrandonRomano/static-lite.git
cd static-lite
npm i
npm run watch
```
