Este proyecto es un test de un workflow, para crear una rama con el nombre de un usuario que se le pase como parametro, y luego invita a este usuario a colaborar en el mismo repositorio. La creacion de la rama se realiza con Git CLI (git) y la invitación al usuario se realiza con GitHub CLI (gh).

#### Pasos para la creacion del TOKEN:

1. Crear un PAT(personal access token) classic. En tu cuenta de Github.
   - MiCuenta / Settings / Developer settings / Personal access tokens / Tokens (classic)
2. Establecer los permisos de "repo" (Para nuestro caso).
3. Guardar el PAT como “secret” en tu repositorio:
   - MiRepositorio / Settings / Secrets and variables / Actions / Repository secrets / New repository secret
4. Añadir el "secret" en el workflow: GH_TOKEN: ${{ secrets.MY_SECRET_TOKEN }}

Nota: Para usar GitHub CLI, se debe establecer la variable de entorno GH_TOKEN (exactamente con ese nombre), ver [documentación](https://docs.github.com/es/actions/writing-workflows/choosing-what-your-workflow-does/using-github-cli-in-workflows).

#### Referencias:

- [ERROR: Create new branch using CLI?](https://github.com/cli/cli/discussions/2863)
- [GitHub CLI api: Add a repository collaborator](https://docs.github.com/en/rest/collaborators/collaborators?apiVersion=2022-11-28#add-a-repository-collaborator)
- [Permissions in workflows](https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions#permissions)
- [ERROR: Github POST](https://stackoverflow.com/questions/70435286/resource-not-accessible-by-integration-on-github-post-repos-owner-repo-ac)
