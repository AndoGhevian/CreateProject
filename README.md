# CreateProject
This is simple CLI Tool to create projects from Templates **scoped** to specific user or organsization.

## Usage
There is two ways to use **create-project**:
1. By Installing it globaly
2. Via npx

### Global Install
Steps for first case(global install)
1. First lets install it globaly, `npm i -g @ando_ghevian/create-project`
2. Set **scope** from which you want to download templates **(Templates start with cpj-template[-templatename])**, `create-project scope set @ando_ghevian`
3. Check that everything went smoothly, and **scope** is accepted `create-project scope get`
4. Create Project From: `create-project --template npm-package npm-project-boilerplate`

You can also use another scope when creating project:
- `create-project scope use @elseScope --template temp prj`
- Or `create-project use @elseScope --template temp prj`

### NPX
Steps For npx:
- `npx @ando_ghevian/create-project use @Scope --template tmp prj`

## How to create Templates
It's similar to [create-react-app Custom Templates](https://create-react-app.dev/docs/custom-templates/#building-a-template). Just few differences:
1. Templates must be scoped to **organization** or **user** and fit the format **cpj-template[-templatename]**, where **cpj-template** will be used as default if **--template(-t)** is specified without value.
1. Default Key/Value Pairs of created projects **package.json** file, come from `npm init -y` command, and anything you specify in **template.json** in **/package** property, will replace default ones.
1. You **MUST NOT** specify **package.json**, **package-lock.json** and **node_modules/** in template folder.
1. And Currently We will replace all **{{ProjectName}}** occurrences in README.md with your project name.