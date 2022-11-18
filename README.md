# GitHub Action Add Students <img src="https://i.imgur.com/m6EYre1.png" width="50px">

GitHub Action for the Organisation to automate the process of adding new students to the organisation.

## GitHub Action Features 💡

This GitHub Actions will:
- Update the specified file with the new student's name and GitHub profile link.
  
## Quickstart

To create a GitHub Action
1. In the folder `.github/workflows/`
2. Create a file `add-students.yaml` (or another name you prefer)
3. Add the Action config


```yaml
  add-student:
    if: github.event.label.name == 'approved-invite'
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: GEC-Jhalawar/gh-action-community/src/add-student@main
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }} # Use Personal Access Token to trigger other actions
          file-path: 'utils/StudentList.json'
```

Here is a complete example https://github.com/GEC-Jhalawar/Support/blob/main/.github/workflows/invite.yml
