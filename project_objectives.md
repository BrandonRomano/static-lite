# Static Lite: Project Objectives

In this document I will outline the objectives of Static Lite, which will ultimately shed light onto why I've built this, but also why you should use it too.

In short, Static Lite:

- [Is easy to understand](#easy-to-understand)
- [Is easy to use](#easy-to-use)
- [Is language agnostic](#language-agnostic)
- [Makes it easy to swap out components](#easy-to-swap-out-components)
- [Gives you full control of the build process](#full-control-of-build-process)
- [Has no middleman dependencies](#no-middleman-dependencies)

## Easy to Understand

My initial reason for starting this project was actually for this reason alone.

My brother was interested in getting into static web development, so I set him up with an all-in-one static site compiler.  I very quickly realized how frequently he was getting tripped up in the hidden nuances of the tool, and it was too large of a task to ask him to dig into the source code to understand it.

Because of this, I set a goal so that if someone spent an hour looking at the source code, they would fully understand every single line of it.

I truly recommend anyone who decides to seriously use this tool to follow the NPM Scripts to see exactly what is happening, it shouldn't take long and you'll have a greater ability to make changes if you should run into the need.  If there is anything that doesn't make sense, file an issue and I will gladly help you understand!

## Easy to Use

In addition to wanting this framework to be easy to understand, I want the end-user of Static Lite (the frontend developer) to have an easy time.

While I strongly recommend fully understanding Static Lite, you actually don't have to understand it to use it.  A user could never peek outside of the `src` directory and build a fully functioning site.

Static Lite should _just work_ and all errors are to be handled by respective tools / compilers.

## Language Agnostic

Static Lite is language agnostic.  The master branch is set up with specific languages so you can clone the project and immediately start running with it, but you are not forced into using any of the languages I have set in the master branch.

There is no need to use Pug, es6, or Stylus.  You can easily swap out your preferred compiler.  There is also no language mandated for the [data](https://github.com/BrandonRomano/static-lite/blob/master/src/data) and [templates](https://github.com/BrandonRomano/static-lite/blob/master/src/templates) file; use any language that works for you.

## Easy to Swap Out Components

I wanted Static Lite to be opionated enough to get started easily, but still flexible enough to work with any use case.  I wanted a tool that will outlive the flavor-of-the-month transpiler everyone is using.

I've built out a [Recipes](https://github.com/BrandonRomano/static-lite#recipes) section to illustrate how easy it is to swap in your favorite tools.

## Full Control of Build Process

The full build process is [right here](https://github.com/BrandonRomano/static-lite/blob/master/package.json#L41-L55).  Change it as you please.

## No Middleman Dependencies

Static Lite is not a dependency, it is a base template.  I didn't want to set up a CLI for Static Lite, because then your errors could come from two places now instead of one.  Because Static Lite calls the compilers directly, the compilers are responsible for outputting any errors.

If there is an error thrown, you can be confident it is coming directly from your tool.
