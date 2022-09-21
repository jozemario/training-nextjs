# Training NextJS
NextJS Design Patterns and Module Federation


<details><summary>Tech Stack </summary>
<p>

#### Ecosystem:
```
host-app: Next.js 12
remote-app: React 17 + Webpack 5
```
</p></details>

<details><summary>Development</summary>
<p>

#### Setup repository
```
github clone git@github.com:jozemario/training-nextjs.git
cd training-nextjs/
git checkout develop
```
#### Setup project
```
# Install all the dependencies to run the apps in parallel.
run yarn 
# Install all the required dependencies on both host-app and remote-app
run npm run install:apps 
# Start both host-app and remote-app
run npm run start 

host-app on localhost:3000
remote-app on localhost:3001
Navigate to localhost:3000 
# Two Button Component should be visible, one from remote and another from host app
```
</p>
</details>

<details><summary>Project Structure</summary>
<p>

```
The remote-app
Within this application, we are exposing a Button component that utilizes a CSS-in-JS design solution.
If you'll notice the shared config, you can see that the version of react and react-dom have been set to 0.
When consuming the remote app within a Next.js environment, we need to make sure that webpack always selects the host's copy of these modules.
By combining the version: '0' syntax with singleton: true we can guarantee that this will be the case.
NOTE: If version: '0' is omitted, you'll encounter an issue where a copy of react will be downloaded from the remoteEntry.

NOTE: Another issue you may run into is an invalid hook call if you are federating a component that uses react hooks. This is directly related to multiple copies of react running at the same time. The above resolves this.

The host-app
Within this application, we've configured the remotes object inside of the NextFederationPlugin.
```
</p>
</details>
