# forge-viewer-samples

Collection of [Autodesk Forge](https://forge.autodesk.com) viewer samples,
automatically deployed to Heroku application https://forge-viewer-samples.herokuapp.com.
Just navigate to any of the html files in  the [public](./public) subfolder, for example:

- https://forge-viewer-samples.herokuapp.com/aec-mapping-2d-to-3d.html

## Running locally

1. Get your Forge app client ID and client secret (see how to [create an app](https://forge.autodesk.com/en/docs/oauth/v2/tutorials/create-app))
2. Clone this repository, and navigate to the project's folder in your terminal
3. Install npm dependencies
    - `yarn install`
4. Specify env. variables `FORGE_CLIENT_ID`, `FORGE_CLIENT_SECRET`, and `PORT`
    - `export FORGE_CLIENT_ID=<your client id>`
    - `export FORGE_CLIENT_SECRET=<your client secret>`
    - `export PORT=3000`
5. Run the app
    - `yarn start`

If you're using [Visual Studio Code](https://code.visualstudio.com), skip the steps 4 and 5,
and instead create a _.vscode/launch.json_ in the project's folder with the following JSON:

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "skipFiles": [
                "<node_internals>/**"
            ],
            "program": "${workspaceFolder}/server.js",
            "env": {
                "FORGE_CLIENT_ID": "<your client id>",
                "FORGE_CLIENT_SECRET": "<your client secret>",
                "PORT": 3000
            }
        }
    ]
}
```

Then you can run _and debug_ the application with `F5`, or by going to `Run` > `Start Debugging`.