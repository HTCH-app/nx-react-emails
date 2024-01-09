# Nx + React-Emails

Early experiments by the HTCH team

## Set up

This is a default NX project with Nextjs.

Next, I followed the [Manual Setup from React Emails](https://react.email/docs/getting-started/manual-setup)

Then, I added a new React lib, removed the files and moved all files added during the React Emails installation.

Finally, I modified [project.json](./libs/emails/project.json) to add the custom nx target.

## Issues


### Paths

React Emails has a `-d` arg to set the directory for all the emails.

I thought that I could use [the `cwd` command option](https://nx.dev/nx-api/nx/executors/run-commands) and set the `-d` flag, but it doesn't work. For some reason `react-emails` can't find the directory for emails. For now, I've used the -d flag to set a deep path from the root to the emails director – ignoring the cwd. 

### Static files

React Emails expects a directory in the root of the project: `/static`. This is used during the `dev` command. You can see what it builds in the `/.react-emails` directory. If the static directory is placed anywhere else, the images will 404 when you run the dev server
