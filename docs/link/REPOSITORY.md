# Adding repository links

In this guide, we'll talk about how to add repository links to components. This lets you quickly open them in your browser, e.g in GitHub, and skim through the source code of your components as you use them. Currently it's only possible to add GitHub links but we're working on GitLab and Bitbucket as we speak.

Note that if you have the repository locally available, you can also use the “Open in” button in Zeplin to view the source code in your favorite IDE/text editor.

☝️ _If you haven't created a Connected Components configuration file yet, check out our [getting started guides](../../README.md#getting-started)._

In this example, we'll add GitHub links all the components in our configuration file. Here's the sample configuration file we'll use, with two components:

```json
{
    "plugins": [
        {
            "name": "@zeplin/cli-connect-react-plugin"
        }
    ],
    "projects": [],
    "styleguides": [
        "5cd486b18a64c1414be004fb"
    ],
    "components": [
        {
            "path": "src/components/Button/Button.jsx",
            "zeplinNames": [
                "Controls / Button / Primary"
            ]
        },
        {
            "path": "src/components/TextField/TextField.jsx",
            "zeplinNames": [
                "Controls / Text field / Primary"
            ]
        }
    ]
}
```

## Adding GitHub configuration

Firstly, in our configuration file, we'll add a property called `github`. Within this property, we'll define our repository name like so:

```json
{
    …
    "components": [
        …
    ],
    "github": [
        {
            "repository": "example/react-components"
        }
    ]
}
```

`repository` is the only property you need to add GitHub links. For example, if your repository URL is `https://github.com/example/react-components`, the `repository` property would be `example/react-components`.

In addition, if you want your GitHub links to point to a specific branch of the repository, you can set the `branch` property like so:

```json
{
    …
    "components": [
        …
    ],
    "github": [
        {
            "repository": "example/react-components",
            "branch": "develop"
        }
    ]
}
```

This is it! Now when we run `zeplin connect`, we should start seeing the “Open in GitHub” button in Zeplin:

<img src="../../img/zeplinCustomLink.png" alt="Connected component in Zeplin" width="314" /> _<TODO: Update screenshot.>_

For further details on how to customize your GitHub link, e.g. URL for GitHub Enterprise, path for monorepos, check out the [Configuration file documentation](CONFIGURATION_FILE.md#githubconfig).

Hope this quick guide on custom links was helpful, reach out to us at [support@zeplin.io](mailto:support@zeplin.io) if you have questions or feedback.