# setting up your computer

I thought when I looked at this a few days ago, in addition to requiring node it said postgres was required. Today it only says node. I decided to install postgres first. straightforward easy download from postgres site.

seemed to hang when i first installed. might have been an intermittent internet connection problem but I have pretty good internet so who knows. must be a pretty big download with all the dependencies that we have built in. either way, I just nuked the whole folder and tried again. worked this time.

# set up your database

run blitz db migrate asked for 'name of migration'. it didn't say it would say this, so I just gave it a name of "firstBlitzApp" and it seemed to work fine

I had the server still running in another terminal when I did this and this command made it error and exit. I simply ran blitz start again and it started right up no problem.

# Scaffold out all the files your basic CRUD actions

kept the server running again for "blitz generate all project" and it didn't crash it this time. however, going to /project did return and error. I was about to go copy it but I just went back and I guess it hot reloaded or something and now it is just a blank screen. Ok, now the server terminal is showing errors which I'll copy below. Right now, when I go to /projects, it shows a 'failed to compile' error and then after 30 seconds or so (I didn't time it) it reloads and shows a blank screen. The home screen is still loading fine. Here's the error in the terminal.

````
$ blitz start
You are using alpha software - if you have any problems, please open an issue here:
https://github.com/blitz-js/blitz/issues/new/choose

- Preparing for launch
  √ Prepped for launch
  [ wait ] starting the development server ...
  [ info ] waiting on http://localhost:3000 ...
  Warning: You have enabled experimental feature(s).
  Experimental features are not covered by semver, and may cause unexpected or broken application behavior. Use them at your own risk.

> Using "webpackDevMiddleware" config function defined in default.
> [ info ] bundled successfully, waiting for typecheck results...
> [ wait ] compiling ...
> [ info ] bundled successfully, waiting for typecheck results...
> [ ready ] compiled successfully - ready on http://localhost:3000 > [ event ] build page: /projects
> [ wait ] compiling ...
> [ error ] C:/Users/Laptop/development/myFirstBlitzApp/node_modules/@prisma/client/runtime/index.js
> Module not found: Can't resolve 'child_process' in 'C:\Users\Laptop\development\myFirstBlitzApp\node_modules\@prisma\client\runtime'
> Could not find files for /projects in .next/build-manifest.json
> ModuleNotFoundError: Module not found: Error: Can't resolve 'child_process' in 'C:\Users\Laptop\development\myFirstBlitzApp\node_modules\@prisma\client\runtime'

    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\Compilation.js:925:10
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\NormalModuleFactory.js:401:22
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\NormalModuleFactory.js:130:21
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\NormalModuleFactory.js:224:22
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\neo-async\async.js:2830:7
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\neo-async\async.js:6877:13
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\NormalModuleFactory.js:214:25
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\Resolver.js:213:14
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\Resolver.js:285:5
    at eval (eval at create (C:\Users\Laptop\development\myFirstBlitzApp\node_modules\tapable\lib\HookCodeFactory.js:33:10), <anonymous>:13:1)
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\UnsafeCachePlugin.js:44:7
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\Resolver.js:285:5
    at eval (eval at create (C:\Users\Laptop\development\myFirstBlitzApp\node_modules\tapable\lib\HookCodeFactory.js:33:10), <anonymous>:13:1)
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\Resolver.js:285:5
    at eval (eval at create (C:\Users\Laptop\development\myFirstBlitzApp\node_modules\tapable\lib\HookCodeFactory.js:33:10), <anonymous>:25:1)
    at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\DescriptionFilePlugin.js:67:43

ModuleNotFoundError: Module not found: Error: Can't resolve 'child_process' in 'C:\Users\Laptop\development\myFirstBlitzApp\node_modules\@prisma\client\runtime'
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\Compilation.js:925:10
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\NormalModuleFactory.js:401:22
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\NormalModuleFactory.js:130:21
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\NormalModuleFactory.js:224:22
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\neo-async\async.js:2830:7
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\neo-async\async.js:6877:13
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\webpack\lib\NormalModuleFactory.js:214:25
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\Resolver.js:213:14
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\Resolver.js:285:5
at eval (eval at create (C:\Users\Laptop\development\myFirstBlitzApp\node_modules\tapable\lib\HookCodeFactory.js:33:10), <anonymous>:13:1)
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\UnsafeCachePlugin.js:44:7
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\Resolver.js:285:5
at eval (eval at create (C:\Users\Laptop\development\myFirstBlitzApp\node_modules\tapable\lib\HookCodeFactory.js:33:10), <anonymous>:13:1)
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\Resolver.js:285:5
at eval (eval at create (C:\Users\Laptop\development\myFirstBlitzApp\node_modules\tapable\lib\HookCodeFactory.js:33:10), <anonymous>:25:1)
at C:\Users\Laptop\development\myFirstBlitzApp\node_modules\enhanced-resolve\lib\DescriptionFilePlugin.js:67:43
[ info ] bundled successfully, waiting for typecheck results...
[ ready ] compiled successfully - ready on http://localhost:3000```
````

# Second try

So I couldn't figure out what to do at this point so I'm just going to try again from scratch. This time I got ```added 1273 packages from 559 contributors and audited 20501 packages in 107.519s

67 packages are looking for funding
run `npm fund` for details

found 0 vulnerabilities

Dependencies successfully installed.
Error: Failed running prettier
at AppGenerator.<anonymous> (C:/Users/Laptop/AppData/Roaming/npm/node_modules/blitz/node_modules/@blitzjs/cli/lib/src/generators/app.js:68:23)
at Generator.next (<anonymous>)
at fulfilled (C:/Users/Laptop/AppData/Roaming/npm/node_modules/blitz/node_modules/tslib/tslib.js:110:62)```

When I tried blitz start it opened up ok despite that error. This time I'll try shutting down the terminal before doing the next steps. Maybe something couldn't run correctly while blitz was already running?

Added the prisma schema file and ran the migrate. This time when it asked for a name of the migration I just clicked enter without entering anything. So far so good.

blitz generate all project - seems to have worked ok. However, navigating to /projects still gives the same error as the first time through.

```

```
